---
title: Конвейеры ввода-вывода — .NET
description: Узнайте, как эффективно использовать конвейеры ввода-вывода в .NET и избежать проблем в коде.
ms.date: 10/01/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: b18b2bf31787fa58e614cd4f057fba9037fe8ad8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77627556"
---
# <a name="systemiopipelines-in-net"></a>System.IO.Pipelines в .NET

<xref:System.IO.Pipelines> — это новая библиотека, предназначенная для упрощения высокопроизводительных операций ввода-вывода в .NET. Это библиотека, предназначенная для .NET Standard, которая работает во всех реализациях .NET.

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a>Какие задачи решает System.IO.Pipelines

<!-- corner case doesn't MT (machine translate)   -->
Приложения, которые анализируют потоковые данные, состоят из стандартного кода, имеющего множество специализированных и необычных потоков кода. Стандартный и специальный код сложен, и его трудно поддерживать.

Возможности `System.IO.Pipelines`:

* Высокопроизводительный анализ потоковых данных.
* Упрощение кода.

Следующий код является типичным для TCP-сервера, который получает сообщения с разделенными строками (разделитель — `'\n'`) от клиента:

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

В предыдущем коде несколько проблем:

* Не все сообщение (конец строки) может быть получено в одном вызове `ReadAsync`.
* Игнорируется результат `stream.ReadAsync`. `stream.ReadAsync` возвращает объем считанных данных.
* Он не обрабатывает случай, когда несколько строк считываются в одном вызове `ReadAsync`.
* Он выделяет массив `byte` при каждом чтении.

Чтобы устранить предыдущие проблемы, необходимо внести следующие изменения:

* Помещение входящих данных в буфер до тех пор, пока не будет найдена новая строка.
* Синтаксический анализ всех строк, возвращенных в буфер.
* Возможно, длина строки превышает 1 КБ (1024 байт). Код должен изменять размер входного буфера до тех пор, пока не будет найден разделитель, чтобы вместить всю строку в буфере.

  * Если размер буфера изменить, создаются дополнительные буферные копии, так как во входных данных отображаются более длинные строки.
  * Чтобы уменьшить объем неиспользуемого пространства, необходимо сжать буфер, используемый для чтения строк.

* Рекомендуется использовать буферные пулы, чтобы избежать повторного выделения памяти.
* В следующем коде решаются некоторые из этих проблем:

[!code-csharp[](~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs?name=snippet)]

Предыдущий код является сложным и не предназначен для устранения всех обнаруженных проблем. Высокая производительность сети обычно означает написание очень сложного кода для повышения производительности. `System.IO.Pipelines` был разработан для упрощения написания этого типа кода.

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a>канал

Класс <xref:System.IO.Pipelines.Pipe> можно использовать для создания пары `PipeWriter/PipeReader`. Все данные, записанные в `PipeWriter`, доступны в `PipeReader`:

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet2)]

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a>Основное использование канала

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet)]

Существует два цикла:

* `FillPipeAsync` считывает из `Socket` и выполняет запись в `PipeWriter`.
* `ReadPipeAsync` считывает из `PipeReader` и анализирует входящие строки.

Буферы явно не выделяются. Управление всеми буферами делегируется реализациям `PipeReader` и `PipeWriter`. Делегирование управления буфером упрощает использование кода, чтобы сосредоточиться только на бизнес-логике.

В первом цикле:

* <xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> вызывается для получения памяти от базового модуля записи.
* <xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> вызывается, чтобы сообщить `PipeWriter`, сколько данных было записано в буфер.
* <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> вызывается, чтобы сделать данные доступными для `PipeReader`.

Во втором цикле `PipeReader` использует буферы, записанные `PipeWriter`. Буферы поступают из сокета. Вызов `PipeReader.ReadAsync`:

* Возвращает <xref:System.IO.Pipelines.ReadResult>, который содержит два важных элемента информации:

  * Данные, считанные в форме `ReadOnlySequence<byte>`.
  * Логическое значение `IsCompleted`, указывающее, достигнут ли конец данных (EOF).

После нахождения разделителя конца строки (EOL) и синтаксического анализа строки:

* Логика обрабатывает буфер, чтобы пропустить уже обработанные данные.
* `PipeReader.AdvanceTo` вызывается, чтобы сообщить `PipeReader`, сколько данных было обработано и проверено.

Циклы чтения и записи заканчиваются вызовом `Complete`. `Complete` позволяет базовому каналу освободить выделенную память.

### <a name="backpressure-and-flow-control"></a>Обратная реакция и управление потоком

В идеале чтение и анализ работают вместе:

* Поток записи потребляет данные из сети и помещает их в буферы.
* Поток анализа отвечает за построение соответствующих структур данных.

Обычно синтаксический анализ занимает больше времени, чем копирование блоков данных из сети:

* Поток чтения идет впереди потока синтаксического анализа.
* Поток чтения должен либо замедлить работу, либо выделить больше памяти для хранения данных для потока синтаксического анализа.

Для оптимальной производительности необходим баланс между частыми паузами и выделением большего объема памяти.

Чтобы устранить описанную выше проблему, `Pipe` имеет два параметра для управления потоком данных:

* <xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>. Определяет, сколько данных следует буферизовать, прежде чем вызовы к <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> будут приостановлены.
* <xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>. Определяет, сколько данных средство чтения должно пронаблюдать, прежде чем вызовы к `PipeWriter.FlushAsync` возобновятся.

![Схема с ResumeWriterThreshold и PauseWriterThreshold](./media/pipelines/resume-pause.png)

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>.

* Возвращает неполный `ValueTask<FlushResult>`, если объем данных в `Pipe` пересекает `PauseWriterThreshold`.
* Завершает `ValueTask<FlushResult>`, когда он становится меньше `ResumeWriterThreshold`.

Для предотвращения быстрого цикла, который может возникнуть при одном значении, используются два значения.

### <a name="examples"></a>Примеры

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a>PipeScheduler

Обычно при использовании `async` и `await` асинхронный код возобновляется в <xref:System.Threading.Tasks.TaskScheduler> либо в текущем <xref:System.Threading.SynchronizationContext>.

При выполнении операций ввода-вывода важно иметь точный контроль над местом выполнения операций ввода-вывода. Этот контроль позволяет эффективно использовать кэш ЦП. Эффективное кэширование является критически важным для высокопроизводительных приложений, таких как веб-серверы. <xref:System.IO.Pipelines.PipeScheduler> предоставляет контроль над тем, где выполняются асинхронные обратные вызовы. По умолчанию:

* используется текущий <xref:System.Threading.SynchronizationContext>.
* Если `SynchronizationContext` отсутствует, он использует пул потоков для выполнения обратных вызовов.

[!code-csharp[](~/samples/snippets/csharp/pipelines/Program.cs?name=snippet)]

[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) — это реализация <xref:System.IO.Pipelines.PipeScheduler>, которая позволяет поместить обратные вызовы в очередь пула потоков. `PipeScheduler.ThreadPool` является параметром по умолчанию и, как правило, лучшим выбором. [PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) может привести к непредвиденным последствиям, например к взаимоблокировкам.

### <a name="pipe-reset"></a>Сброс канала

Зачастую бывает эффективно повторно использовать объект `Pipe`. Чтобы сбросить канал, вызовите <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> при завершении `PipeReader` и `PipeWriter`.

## <a name="pipereader"></a>PipeReader

<xref:System.IO.Pipelines.PipeReader> управляет памятью от имени вызывающего объекта. **Всегда** вызывайте <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> после вызова <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>. Это позволяет `PipeReader` узнать, когда вызывающий объект закончил использовать память, чтобы его можно было отследить. `ReadOnlySequence<byte>`, возвращенный из `PipeReader.ReadAsync`, допустим только до вызова `PipeReader.AdvanceTo`. Использование `ReadOnlySequence<byte>` после вызова `PipeReader.AdvanceTo` недопустимо.

`PipeReader.AdvanceTo` принимает два аргумента <xref:System.SequencePosition>:

* Первый аргумент определяет объем используемой памяти.
* Второй аргумент определяет, какая часть буфера наблюдалась.

Если пометить данные как потребленные, канал сможет вернуть память в базовый буферный пул. Пометка данных как отмеченных управляет тем, что делает следующий вызов `PipeReader.ReadAsync`. Пометка всех элементов как отмеченных означает, что следующий вызов `PipeReader.ReadAsync` не вернется, пока в канал не будет записано больше данных. Любое другое значение заставит следующий вызов `PipeReader.ReadAsync` вернуться немедленно с отмеченными *и* неотмеченными, но уже потребленными данными.

### <a name="read-streaming-data-scenarios"></a>Сценарии чтения потоковых данных

Существует несколько типичных шаблонов, которые возникают при попытке чтения потоковых данных:

* При получении потока данных анализировать одно сообщение.
* При получении потока данных анализировать все доступные сообщения.

В следующих примерах используется метод `TryParseMessage` для синтаксического анализа сообщений из `ReadOnlySequence<byte>`. `TryParseMessage` анализирует одно сообщение и обновляет входной буфер, чтобы обрезать проанализированное сообщение из буфера. `TryParseMessage` не является частью .NET, это написанный пользователем метод, который используется в следующих разделах.

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a>Чтение одного сообщения

Следующий код считывает одно сообщение из `PipeReader` и возвращает его вызывающему объекту.

[!code-csharp[ReadSingleMsg](~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs?name=snippet)]

Предыдущий код:

* анализирует одно сообщение.
* Обновляет потребленный `SequencePosition` и изученный `SequencePosition`, чтобы указать на начало обрезанного входного буфера.

Два аргумента `SequencePosition` обновляются, так как `TryParseMessage` удаляет проанализированное сообщение из входного буфера. Как правило, при синтаксическом анализе одного сообщения из буфера изученное расположение должно быть одним из следующих:

* Конец сообщения.
* Конец полученного буфера, если сообщение не найдено.

В случае с одним сообщением риск ошибок наиболее велик. Передача неверных значений в *изученное* может привести к исключению нехватки памяти или бесконечному циклу. Дополнительные сведения см. в разделе [Распространенные проблемы PipeReader](#gotchas) в этой статье.

### <a name="reading-multiple-messages"></a>Чтение нескольких сообщений

Следующий код считывает все сообщения из `PipeReader` и вызывает `ProcessMessageAsync` для каждого из них.

[!code-csharp[MyConnection1](~/samples/snippets/csharp/pipelines/MyConnection1.cs?name=snippet)]

### <a name="cancellation"></a>Отмена

`PipeReader.ReadAsync`.

* Поддерживает передачу <xref:System.Threading.CancellationToken>.
* Создает исключение <xref:System.OperationCanceledException>, если `CancellationToken` отменяется при ожидании чтения.
* Поддерживает способ отмены текущей операции чтения с помощью <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, что позволяет избежать исключения. Вызов `PipeReader.CancelPendingRead` приводит к тому, что текущий или следующий вызов `PipeReader.ReadAsync` возвращает <xref:System.IO.Pipelines.ReadResult> с `IsCanceled` со значением `true`. Это может быть полезно для остановки существующего цикла чтения без сбоев и исключений.

[!code-csharp[MyConnection](~/samples/snippets/csharp/pipelines/MyConnection.cs?name=snippet)]

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a>Распространенные проблемы PipeReader

* Передача неверных значений в `consumed` или `examined` может привести к считыванию уже считанных данных.
* Передача `buffer.End` как изученного может привести к следующему:

  * Остановленные данные
  * Может возникать исключение нехватки памяти, если данные не потребляются. Например, `PipeReader.AdvanceTo(position, buffer.End)` при обработке одного сообщения за раз из буфера.

* Передача неверных значений в `consumed` или `examined` может привести к бесконечному циклу. Например, `PipeReader.AdvanceTo(buffer.Start)`, если `buffer.Start` не изменился, приведет к тому, что следующий вызов `PipeReader.ReadAsync` вернется немедленно перед поступлением новых данных.
* Передача неверных значений в `consumed` или `examined` может привести к бесконечной буферизации (и нехватке памяти в конечном итоге).
* Использование `ReadOnlySequence<byte>` после вызова `PipeReader.AdvanceTo` может привести к повреждению памяти (используйте после освобождения).
* Отсутствие вызова `PipeReader.Complete/CompleteAsync` может привести к утечке памяти.
* Проверка <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> и выход из логики чтения до обработки буфера приводит к потере данных. Условие выхода цикла должно основываться на `ReadResult.Buffer.IsEmpty` и `ReadResult.IsCompleted`. Неправильное выполнение этого действия может привести к бесконечному циклу.

#### <a name="problematic-code"></a>Проблемный код

❌ **Потеря данных**

`ReadResult` может возвращать окончательный сегмент данных, если `IsCompleted` имеет значение `true`. Если не считать эти данные до выхода из цикла чтения, данные будут утеряны.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#1](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Бесконечный цикл**

Следующая логика может привести к бесконечному циклу, если `Result.IsCompleted` равно `true`, но в буфере никогда нет полного сообщения.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#2](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet2)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

Вот еще один фрагмент кода с такой же проблемой. Проверяется наличие непустого буфера перед проверкой `ReadResult.IsCompleted`. Так как он находится в `else if`, цикл будет повторяться бесконечно, если в буфере никогда не будет полного сообщения.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#3](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet3)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Непредвиденное зависание**

Безусловный вызов `PipeReader.AdvanceTo` с `buffer.End` в положении `examined` может привести к зависанию при анализе одного сообщения. Следующий вызов `PipeReader.AdvanceTo` вернет значение только в следующих условиях:

* В канал записано больше данных.
* Новые данные не были проверены ранее.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#4](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet4)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Нехватка памяти**

В следующих случаях приведенный ниже код сохраняет буферизацию до тех пор, пока не произойдет <xref:System.OutOfMemoryException>:

* Максимальный размер сообщения не указан.
* Данные, возвращенные из `PipeReader`, не составляют полное сообщение. Например, они не составляют полное сообщение, поскольку другая сторона записывает большое сообщение (например, сообщение размером 4 ГБ).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#5](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet5)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Повреждение памяти**

При написании вспомогательных методов, считывающих буфер, все возвращенные полезные данные должны быть скопированы перед вызовом `Advance`. В следующем примере возвращается память, которая была удалена `Pipe` и может использоваться повторно для следующей операции (чтение или запись).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#Message](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippetMessage)]

[!code-csharp[DoNotUse#6](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet6)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a>PipeWriter

<xref:System.IO.Pipelines.PipeWriter> управляет буферами для записи от имени вызывающего объекта. `PipeWriter` реализует [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601). `IBufferWriter<byte>` позволяет получить доступ к буферам для выполнения операций записи без дополнительных буферных копий.

[!code-csharp[MyPipeWriter](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet)]

Предыдущий код:

* Запрашивает буфер длиной не менее 5 байт у `PipeWriter` с помощью <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.
* Записывает байты для строки ASCII `"Hello"` в возвращенный `Memory<byte>`.
* Вызывает <xref:System.IO.Pipelines.PipeWriter.Advance%2A>, чтобы указать, сколько байтов было записано в буфер.
* Очищает `PipeWriter`, который отправляет байты на базовое устройство.

Предыдущий метод записи использует буферы, предоставленные `PipeWriter`. В противном случае <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:

* Копирует существующий буфер в `PipeWriter`.
* Вызывает `GetSpan`, выполняет `Advance` надлежащим образом и вызывает <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.

[!code-csharp[MyPipeWriter#2](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet2)]

### <a name="cancellation"></a>Отмена

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> поддерживает передачу <xref:System.Threading.CancellationToken>. Передача `CancellationToken` приводит к исключению `OperationCanceledException`, если маркер отменяется в ожидании освобождения. `PipeWriter.FlushAsync` поддерживает способ отмены текущей операции освобождения с помощью <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType>, не вызывая исключение. Вызов `PipeWriter.CancelPendingFlush` приводит к тому, что текущий или следующий вызов `PipeWriter.FlushAsync` или `PipeWriter.WriteAsync` возвращает <xref:System.IO.Pipelines.FlushResult> с `IsCanceled` со значением `true`. Это может быть полезно для остановки освобождения без сбоев и исключений.

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a>Распространенные проблемы PipeWriter

* <xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> и <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> возвращают буфер по крайней мере с запрошенным объемом памяти. **Не** рассчитывайте на точный размер буфера.
* Нет никакой гарантии, что последовательные вызовы будут возвращать один и тот же буфер или буфер того же размера.
* Чтобы продолжить запись дополнительных данных, необходимо запросить новый буфер после вызова <xref:System.IO.Pipelines.PipeWriter.Advance%2A>. Запись в ранее полученный буфер невозможна.
* Вызов `GetMemory` или `GetSpan` при наличии незавершенного вызова `FlushAsync` не является надежным.
* Вызов `Complete` или `CompleteAsync` при наличии неосвобожденных данных может привести к повреждению памяти.

## <a name="iduplexpipe"></a>IDuplexPipe

<xref:System.IO.Pipelines.IDuplexPipe> является контрактом для типов, поддерживающих чтение и запись. Например, сетевое подключение будет представлено `IDuplexPipe`.

 В отличие от `Pipe`, который содержит `PipeReader` и `PipeWriter`, `IDuplexPipe` представляет собой одну сторону полного дуплексного подключения. Это означает, что запись в `PipeWriter` не будет считываться из `PipeReader`.

## <a name="streams"></a>Потоки

При чтении или записи потоковых данных данные обычно считываются с помощью десериализатора и записываются с помощью сериализатора. Большая часть API потока чтения и записи имеет параметр `Stream`. Чтобы упростить интеграцию с существующими API, `PipeReader` и `PipeWriter` предоставляют <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.  <xref:System.IO.Pipelines.PipeWriter.AsStream%2A> возвращает реализацию `Stream` на основе `PipeReader` или `PipeWriter`.
