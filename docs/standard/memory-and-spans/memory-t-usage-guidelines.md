---
title: Рекомендации по использованию структур Memory<T> и Span<T>
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: 0a614f628faa98be778c627573e4dddc462c9107
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121960"
---
# <a name="memoryt-and-spant-usage-guidelines"></a>Рекомендации по использованию структур Memory\<T> и Span\<T>

В .NET Core есть несколько типов, представляющих произвольную непрерывную область памяти. В .NET Core 2.0 появились типы <xref:System.Span%601> и <xref:System.ReadOnlySpan%601>, которые являются упрощенными буферами памяти, поддерживаемыми управляемой или неуправляемой памятью. Так как эти типы могут храниться только в стеке, они непригодны для ряда сценариев, включая вызовы асинхронных методов. В .NET Core 2.1 был добавлен ряд дополнительных типов, включая <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> и <xref:System.Buffers.MemoryPool%601>. Как и <xref:System.Span%601>, <xref:System.Memory%601> и связанные с ним типы могут поддерживаться управляемой и неуправляемой памятью. В отличие от <xref:System.Span%601> <xref:System.Memory%601> может храниться в управляемой куче.

<xref:System.Span%601> и <xref:System.Memory%601> являются буферами структурированных данных, которые можно использовать в конвейерах. То есть они разработаны так, чтобы некоторые или все данные могли быть эффективно переданы компонентам в конвейере, который способен их обрабатывать и при необходимости изменять буфер. Так как <xref:System.Memory%601> и связанные с ним типы могут быть доступными нескольким компонентам или нескольким потокам, важно, чтобы разработчик следовал некоторым общим рекомендациям для создания надежного кода.

## <a name="owners-consumers-and-lifetime-management"></a>Владельцы, объекты-получатели и управление жизненным циклом

Так как буферы можно передавать от API к API, а доступ к буферам иногда может осуществляться из нескольких потоков, необходимо управлять временем их существования. Есть три важных момента:

- **Владение**. Владелец экземпляра буфера отвечает за управление его жизненным циклом, включая удаление буфера, который больше не используется. У буфера может быть только один владелец. Владельцем обычно является компонент, который создал буфер или получил его из фабрики. Право владения можно передавать. **Компонент А** может передать контроль над буфером **компоненту Б**, после чего **компонент А** больше не сможет использовать буфер, а **компонент Б** будет отвечать за удаление буфера, когда необходимость в нем исчезнет.

- **Использование**. Объект-получатель экземпляра буфера может выполнять чтение и запись в буфер. У буфера одновременно может быть только один объект-получатель, если не обеспечен какой-либо внешний механизм синхронизации. Обратите внимание, что объектом-получателя буфера не обязательно является владелец буфера.

- **Аренда**. Аренда — это срок, в течение которого определенный компонент может быть объектом-получателем буфера.

Следующий пример псевдокода иллюстрирует три этих понятия. Он содержит метод `Main`, который создает буфер <xref:System.Memory%601> типа <xref:System.Char>, вызывает метод `WriteInt32ToBuffer` для записи строкового представления целого числа в буфер, а затем вызывает метод `DisplayBufferToConsole` для отображения значения буфера.

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

Метод `Main` создает буфер (в этом случае экземпляр <xref:System.Span%601>), поэтому он является его владельцем. Таким образом, `Main` отвечает за удаление буфера, когда он больше не используется. Он выполняет это путем вызова метода буфера <xref:System.Span%601.Clear?displayProperty=nameWithType>. (Здесь метод <xref:System.Span%601.Clear> по сути очищает память буфера. У структуры <xref:System.Span%601> нет метода для удаления буфера.)

У буфера два объекта-получателя — `WriteInt32ToBuffer` и `DisplayBufferToConsole`. Одновременно у буфера может быть только один объект-получатель (сначала `WriteInt32ToBuffer`, а затем `DisplayBufferToConsole`), и ни один из них не является владельцем буфера. Обратите внимание, что объект-получатель здесь имеет не только возможность чтения из буфера. Объекты-получатели могут изменять содержимое буфера, как в случае `WriteInt32ToBuffer`, если предоставлены соответствующие права.

Метод `WriteInt32ToBuffer` арендует буфер (может быть его объектом-получателем), начиная с вызова метода и до момента его возвращения. Аналогичным образом `DisplayBufferToConsole` арендует буфер на время своего выполнения, и аренда заканчивается, когда выполнение завершается. (Не существует API для управления арендой, так как аренда — концептуальное понятие.)

## <a name="memoryt-and-the-ownerconsumer-model"></a>Memory\<T> и модель "владелец — объект-получатель"

Как уже сообщалось в разделе [Владельцы, объекты-получатели и управление жизненным циклом](#owners-consumers-and-lifetime-management), у буфера всегда есть владелец. В .NET Core поддерживаются две модели владения:

- Модель с единственным владельцем. У буфера есть только один владелец в течение всего его времени существования.

- Модель, позволяющая передавать право владения. Право владения буфером может передаваться от его первоначального владельца (его создателя) другому компоненту, после чего последний отвечает за управление временем существования буфера. Новый владелец может, в свою очередь, передать право владения другому компоненту и так далее.

С помощью интерфейса <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> можно явно управлять правом владения буфером. <xref:System.Buffers.IMemoryOwner%601> поддерживает обе модели владения. Владельцем буфера является компонент, на который ссылается <xref:System.Buffers.IMemoryOwner%601>. В следующем примере используется экземпляр <xref:System.Buffers.IMemoryOwner%601?> для указания владельца буфера <xref:System.Memory%601>.

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

Этот пример можно также написать, используя [`using`](../../csharp/language-reference/keywords/using-statement.md).

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

В этом коде:

- Экземпляр <xref:System.Buffers.IMemoryOwner%601> ссылается на метод `Main`, поэтому метод `Main` является владельцем буфера.

- Методы `WriteInt32ToBuffer` и `DisplayBufferToConsole` принимают <xref:System.Memory%601> как общедоступный API-интерфейс. Таким образом, они являются объектами-получателями буфера, выступая в этой роли поочередно.

При этом метод `WriteInt32ToBuffer` позволяет выполнить запись значения в буфер, а метод `DisplayBufferToConsole` — нет. Чтобы отобразить этот факт, последний мог бы принять аргумент типа <xref:System.ReadOnlyMemory%601>. Дополнительную информацию о <xref:System.ReadOnlyMemory%601> см. в разделе [Правило 2. Используйте ReadOnlySpan\<T> или ReadOnlyMemory\<T>, если буфер должен быть доступен только для чтения](#rule-2).

### <a name="ownerless-memoryt-instances"></a>Экземпляры Memory\<T> без владельца

Можно создать экземпляр <xref:System.Memory%601>, не используя <xref:System.Buffers.IMemoryOwner%601>. В этом случае владелец буфера указывается неявно, поэтому поддерживается только модель с единственным владельцем. Выполнить это можно следующим образом:

- Вызвав один из конструкторов <xref:System.Memory%601> и передав `T[]`, как показано в следующем примере.

- Вызвав метод расширения [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) для создания экземпляра `ReadOnlyMemory<char>`.

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

Метод, который первоначально создает экземпляр <xref:System.Memory%601>, является неявным владельцем буфера. Право владения нельзя передать другому компоненту, так как отсутствует экземпляр <xref:System.Buffers.IMemoryOwner%601>, позволяющий такую передачу. (Как вариант, можете представить, что владельцем буфера является сборщик мусора среды выполнения, а все методы — это просто объекты-получатели буфера.)

## <a name="usage-guidelines"></a>Рекомендации по использованию

Так как блок памяти имеет владельца, но предназначен для передачи нескольким компонентам, некоторые из которых могут одновременно работать с блоком памяти, необходимо следовать рекомендациям по использованию <xref:System.Memory%601> и <xref:System.Span%601>.  Причины такого поведения следующие:

- Компонент может сохранить ссылку на блок памяти после того, как владелец буфера ее передал.

- Компоненты могут одновременно работать с буфером, что приведет к повреждению данных в буфере.

- Хотя хранимая в стеке структура <xref:System.Span%601> оптимизирует производительность, что делает <xref:System.Span%601> предпочтительным типом для работы с блоком памяти, структура <xref:System.Span%601> также подвержена ряду важных ограничений. Важно понимать, когда следует использовать <xref:System.Span%601>, а когда — <xref:System.Memory%601>.

Ниже приведены наши рекомендации для успешного использования <xref:System.Memory%601> и связанных типов. Обратите внимание, что рекомендации по использованию <xref:System.Memory%601> и <xref:System.Span%601> также касаются <xref:System.ReadOnlyMemory%601> и <xref:System.ReadOnlySpan%601>, если прямо не заявлено об обратном.

**Правило 1. Для синхронных API по возможности используйте Span\<T> вместо Memory\<T> в качестве параметра**

Структура <xref:System.Span%601> более эффективна, чем <xref:System.Memory%601>, и обеспечивает больше возможностей по работе со смежными буферами памяти. <xref:System.Span%601> также обеспечивает лучшую производительность, чем <xref:System.Memory%601>. Наконец, вы можете использовать свойство <xref:System.Memory%601.Span?displayProperty=nameWithType> для преобразования экземпляра <xref:System.Memory%601> в <xref:System.Span%601>, тогда как нельзя преобразовать Span\<T > в Memory\<T>. Поэтому, если у вызывающих объектов есть экземпляр <xref:System.Memory%601>, они в любом случае смогут вызвать методы с помощью параметров <xref:System.Span%601>.

Использование параметра типа <xref:System.Span%601> вместо типа <xref:System.Memory%601> также помогает выполнить правильную реализацию метода использования. Вам нужно обеспечить автоматические проверки времени компиляции, гарантирующие, что доступ к буферу осуществляется только в период его аренды методом (подробнее об этом далее).

В некоторых случаях вам придется использовать параметр <xref:System.Memory%601> вместо параметра <xref:System.Span%601> даже в случае полной синхронизации. Может оказаться так, что API, от которого вы зависите, принимает только аргументы <xref:System.Memory%601>. Это нормально, но следует учитывать компромиссы, связанные с синхронным использованием <xref:System.Memory%601>.

<a name="rule-2" />

**Правило 2. Используйте ReadOnlySpan\<T> или ReadOnlyMemory\<T>, если буфер должен быть доступен только для чтения**

В предыдущих примерах метод `DisplayBufferToConsole` только считывает данные из буфера, не изменяя его содержимое. Сигнатуру метода следует изменить следующим образом.

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

На самом деле, если мы объединим это правило с правилом 1, то сможем добиться лучшего результата и переписать сигнатуру метода следующим образом.

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

Метод `DisplayBufferToConsole` теперь работает с практически всеми возможными типами буфера: `T[]`, блоком памяти, выделяемым с помощью ключевого слова [stackalloc](../../csharp/language-reference/operators/stackalloc.md) и т. д. Ему даже можно непосредственно передать <xref:System.String>!

**Правило 3. Если метод принимает Memory\<T> и возвращает `void`, вам не следует использовать экземпляр Memory\<T> после возврата метода**

Это относится к упомянутой ранее концепции аренды. Аренда возвращающего слово void метода в экземпляре <xref:System.Memory%601> начинается с началом выполнения метода и заканчивается, когда он завершает работу. Рассмотрим следующий пример, в котором вызывается `Log` в цикле на основе входных данных из консоли.

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

Если `Log` — это полностью синхронный метод, этот код будет работать ожидаемо, так как в любой момент времени у экземпляра памяти есть только один объект-получатель.
Но представьте себе, если реализация `Log` будет такой.

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

В этом случае метод `Log` нарушает свою аренду, так как он пытается использовать экземпляр <xref:System.Memory%601> в фоновом режиме после возврата первоначального метода. Метод `Main` может изменять буфер, когда `Log` пытается выполнить чтение из него, что может привести к повреждению данных.

Есть несколько способов устранить эту проблему.

- Метод `Log` может возвращать <xref:System.Threading.Tasks.Task> вместо `void`, как это сделано в следующей реализации метода `Log`.

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- `Log` можно реализовать следующим образом.

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

**Правило 4. Если метод принимает Memory\<T> и возвращает Task, не следует использовать экземпляр Memory\<T> после перехода Task в конечное состояние**

Это попросту асинхронный вариант правила 3. Метод `Log` из предыдущего примера можно записать следующим образом в соответствии с этим правилом.

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

Здесь "конечное состояние" означает, что выполнение Task завершается успешно или сбоем, или же отменяется. Другими словами "конечное состояния" означает "отсутствие чего-либо, связанного с ожиданием возврата или продолжением выполнения".

Эти рекомендации относятся к методам, которые возвращают <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> или любой аналогичный тип.

**Правило 5. Если конструктор принимает Memory\<T> в качестве параметра, предполагается, что методы экземпляра созданного объекта являются объектами-получателями экземпляра Memory\<T>**

Рассмотрим следующий пример.

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

Здесь конструктор `OddValueExtractor` принимает `ReadOnlyMemory<int>` в качестве параметра конструктора, поэтому сам конструктор является объектом-получателем экземпляра `ReadOnlyMemory<int>`, а все методы экземпляра возвращаемого значения также являются объектами-получателями исходного экземпляра `ReadOnlyMemory<int>`. Это означает, что `TryReadNextOddValue` — это объект-получатель экземпляра `ReadOnlyMemory<int>`, хотя экземпляр не передается непосредственно в метод `TryReadNextOddValue`.

**Правило 6. Если у вашего типа есть настраиваемое Memory\<T>-типизированное свойство (или эквивалентный метод экземпляра), предполагается, что методы экземпляра для этого объекта являются объектами-получателями экземпляра Memory\<T>**

Это всего лишь разновидность правила 5. Это правило существует, так как предполагается, что методы задания свойств или эквивалентные методы записывают и сохраняют свои входные данные, чтобы методы экземпляра того же объекта могли использовать записанное состояние.

Это правило иллюстрирует следующий пример.

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

**Правило 7. Если в IMemoryOwner\<T> присутствует ссылка, необходимо в определенный момент исключить ее или передать ее право владения (но не одновременно).**

Так как экземпляр <xref:System.Memory%601> может обслуживаться управляемой или неуправляемой памятью, владелец должен вызвать <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>, когда завершится работа с экземпляром <xref:System.Memory%601>. Кроме того, владелец может передать право владения экземпляром <xref:System.Buffers.IMemoryOwner%601> другому компоненту, после чего этот компонент будет отвечать за вызов <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> в соответствующее время (подробнее об этом далее).

Сбой при вызове метода <xref:System.Buffers.MemoryPool%601.Dispose%2A> может привести к утечкам неуправляемой памяти или другому снижению производительности.

Это правило также применяется к коду, который вызывает фабричные методы, такие как <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>. Вызывающий объект становится владельцем возвращаемого <xref:System.Buffers.IMemoryOwner%601> и отвечает за удаление экземпляра после завершения.

**Правило 8. Если в рабочей области API у вас присутствует параметр IMemoryOwner\<T>, вы принимаете право владения этим экземпляром**

Прием экземпляра этого типа означает, что ваш компонент собирается стать владельцем этого экземпляра. Компонент будет отвечать за правильное удаление экземпляра в соответствии с правилом 7.

Любой компонент, который передает право владения экземпляром <xref:System.Buffers.IMemoryOwner%601> другому компоненту, больше не должен использовать этот экземпляр после завершения вызова метода.

> [!IMPORTANT]
> Если ваш конструктор принимает <xref:System.Buffers.IMemoryOwner%601> в качестве параметра, его тип должен реализовывать <xref:System.IDisposable>, а ваш метод <xref:System.IDisposable.Dispose%2A> вызывать <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.

**Правило 9. Если вы создаете оболочку для синхронного метода p/invoke, API должен принимать Span\<T> в качестве параметра.**

В соответствии с правилом 1, <xref:System.Span%601> — это тот тип, который обычно следует использовать для синхронных API. Вы можете закрепить экземпляры <xref:System.Span%601> с помощью ключевого слова [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md), как показано в следующем примере.

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

В предыдущем примере `pbData` может принимать значение NULL, например, если входной диапазон пуст. Если экспортированный метод категорически требует, чтобы параметр `pbData` не мог возвращать значение NULL, даже если `cbData` равно 0, метод может быть реализован следующим образом.

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

**Правило 10. Если вы создаете оболочку для асинхронного метода p/invoke, API должен принимать Memory\<T> в качестве параметра**

Так как ключевое слово [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) нельзя использовать для асинхронных операций, используйте метод <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType>, чтобы закрепить экземпляры <xref:System.Memory%601>, независимо от вида непрерывной памяти, представленной экземпляром. В следующем примере показано, как использовать этот API, чтобы выполнить вызов асинхронного метода p/invoke.

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)state;
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a>См. также

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
