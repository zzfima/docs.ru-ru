---
title: Использование System.Buffers в .NET
ms.date: 12/05/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: f939164cd56b2fb2feeeb171236b0e1171327e19
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160122"
---
# <a name="work-with-buffers-in-net"></a>Работа с буферами в .NET

В этой статье описаны типы, которые помогают выполнять чтение данных, проходящих через несколько буферов. В основном они используются для поддержки объектов <xref:System.IO.Pipelines.PipeReader>.

## <a name="ibufferwritert"></a>IBufferWriter\<T\>

<xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> — это контракт для синхронной записи в буфер. Интерфейс обладает такими базовыми характеристиками:

- он простой и его легко использовать;
- он обеспечивает доступ к <xref:System.Memory%601> или <xref:System.Span%601>. `Memory<T>` или `Span<T>` поддерживают функцию записи, и вы можете узнать, сколько элементов `T` было записано.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

Предыдущий метод выполняет такие действия:

- Запрашивает буфер длиной не менее 5 байт у `IBufferWriter<byte>` с помощью `GetSpan(5)`.
- Записывает байты для строки Hello (ASCII) при получении `Span<byte>`.
- Вызывает <xref:System.Buffers.IBufferWriter%601>, чтобы указать, сколько байтов было записано в буфер.

Этот метод записи использует буфер `Memory<T>`/`Span<T>`, предоставленный `IBufferWriter<T>`. Можно также использовать метод расширения <xref:System.Buffers.BuffersExtensions.Write%2A> для копирования существующего буфера в `IBufferWriter<T>`. `Write` вызывает `GetSpan`/`Advance` соответствующим образом, поэтому нет необходимости вызывать `Advance` после записи.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<xref:System.Buffers.ArrayBufferWriter%601> является реализацией `IBufferWriter<T>`, чье резервное хранилище представляет собой единый смежный массив.

### <a name="ibufferwriter-common-problems"></a>Распространенные проблемы с IBufferWriter

- `GetSpan` и `GetMemory` возвращают буфер по крайней мере с запрошенным объемом памяти. Не рассчитывайте на точный размер буфера.
- Нет никакой гарантии, что последовательные вызовы будут возвращать один и тот же буфер или буфер того же размера.
- Чтобы продолжить запись дополнительных данных, необходимо запросить новый буфер после вызова `Advance`. Невозможно выполнить запись в ранее полученный буфер после вызова `Advance`.

## <a name="readonlysequencet"></a>ReadOnlySequence\<T\>

![ReadOnlySequence: показана область памяти в канале, а под ней показана позиция последовательности в памяти, доступной только для чтения](media/buffers/ro-sequence.png)

<xref:System.Buffers.ReadOnlySequence%601> — это структура, которая может представлять смежную или несмежную последовательность `T`. Она может состоять из следующих компонентов:

1. `T[]`;
1. `ReadOnlyMemory<T>`;
1. Пара узла связанного списка <xref:System.Buffers.ReadOnlySequenceSegment%601> и индекса, представляющая начальную и конечную позицию последовательности.

Третье представление является наиболее интересным, так как оно влияет на производительность различных операций с `ReadOnlySequence<T>`.

|Представление|Операция|Сложность|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

Из-за такого смешанного представления `ReadOnlySequence<T>` предоставляет индексы в виде `SequencePosition`, а не целого числа. Характеристики `SequencePosition`:

- Это скрытое значение, представляющее индекс в `ReadOnlySequence<T>`, где он был создан.
- Состоит из двух частей: целого числа и объекта. Представление этих двух значений связано с реализацией `ReadOnlySequence<T>`.

### <a name="access-data"></a>Доступ к данным

`ReadOnlySequence<T>` предоставляет данные в виде перечислимого типа `ReadOnlyMemory<T>`. Перечисление каждого сегмента можно выполнить с помощью простого цикла foreach:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

Описанный выше метод ищет все сегменты с определенным количеством байт. Для отслеживания значения `SequencePosition` каждого сегмента больше подойдет <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType>. В следующем примере мы изменили приведенный выше код, чтобы он возвращал `SequencePosition` вместо целого числа. При возврате значения `SequencePosition` вызывающий может пропустить вторую проверку для получения данных в определенном индексе.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

Сочетание `SequencePosition` и `TryGet` выполняет функции перечислителя. Поле позиции изменяется в начале каждой итерации для того, чтобы оно находилось в начале каждого сегмента в `ReadOnlySequence<T>`.

Предыдущий метод используется в качестве метода расширения в `ReadOnlySequence<T>`. Чтобы упростить предыдущий код, можно использовать <xref:System.Buffers.BuffersExtensions.PositionOf%2A>.

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a>Обработка ReadOnlySequence\<T\>

Обработка `ReadOnlySequence<T>` может оказаться сложной задачей, так как данные могут находиться в нескольких сегментах в последовательности. Для лучшей производительности разделите код на две задачи:

- более быстрая задача для операции с одним сегментом;
- более медленная задача для операций с данными, распределенными между несколькими сегментами.

Существует несколько способов обработки данных в последовательностях с несколькими сегментами:

- Используйте [`SequenceReader<T>`](#sequencereadert).
- Анализируйте данные по сегментам. При этом следите за значением `SequencePosition` и индексом в проанализированном сегменте. Это позволяет избежать ненужного распределения. Но такой способ может оказаться неэффективным, особенно для небольших буферов.
- Скопируйте `ReadOnlySequence<T>` в смежный массив и работайте с ним как с отдельным буфером.
  - Если размер `ReadOnlySequence<T>` небольшой, возможно, лучше будет скопировать данные в буфер, размещенный в стеке, с помощью оператора [stackalloc](../../csharp/language-reference/operators/stackalloc.md).
  - Скопируйте `ReadOnlySequence<T>` в массив в пуле с помощью <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.
  - Используйте [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A). Не рекомендуется использовать в критических путях, так как выделяется новый экземпляр `T[]` в куче.

В следующих примерах показаны некоторые распространенные сценарии обработки `ReadOnlySequence<byte>`.

##### <a name="process-binary-data"></a>Обработка двоичных данных

В следующем примере обрабатывается целое число (длиной 4 байта) с обратным порядком байтов с начала `ReadOnlySequence<byte>`.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a>Обработка текстовых данных

Следующий пример:

- Выполняется поиск первого символа новой строки (`\r\n`) в `ReadOnlySequence<byte>`, которое возвращается через выходной параметр line.
- Затем эта строка обрезается, исключая `\r\n` из входного буфера.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a>Пустые сегменты

Допускается хранение пустых сегментов в `ReadOnlySequence<T>`. Пустые сегменты могут возникать при явном перечислении сегментов.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

В предыдущем примере кода создается `ReadOnlySequence<byte>` с пустыми сегментами и показано, как эти пустые сегменты влияют на разные API:

- Сочетание `ReadOnlySequence<T>.Slice` со структурой `SequencePosition`, указывающей на пустой сегмент, сохраняет такой сегмент.
- `ReadOnlySequence<T>.Slice` с int позволяет пропустить пустой сегмент.
- При перечислении `ReadOnlySequence<T>` перечисляются пустые сегменты.

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a>Возможные проблемы с ReadOnlySequence\<T> и SequencePosition

При использовании `ReadOnlySequence<T>`/`SequencePosition` вместо обычной структуры `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int` могут возникнуть нетипичные результаты:

- `SequencePosition` — это метка позиции определенного объекта `ReadOnlySequence<T>`, а не абсолютная позиция. Так как эта метка связана с определенным типом `ReadOnlySequence<T>`, нет смысла ее использовать за пределами `ReadOnlySequence<T>`, где она была создана.
- Арифметические операции с `SequencePosition` нельзя выполнять без `ReadOnlySequence<T>`. Это означает, что при выполнении простых операций, например `position++`, записывается `ReadOnlySequence<T>.GetPosition(position, 1)`.
- `GetPosition(long)`**не** поддерживает отрицательные индексы. Таким образом, чтобы получить предпоследний символ, необходимо пройти все сегменты.
- Нельзя сравнить два объекта `SequencePosition`, что затрудняет выполнение следующих задач:
  - Определение того, является ли значение позиции больше или меньше по отношению к другой позиции.
  - Написание некоторых алгоритмов анализа.
- Размер последовательности `ReadOnlySequence<T>` больше чем у ссылки на объект, поэтому по возможности последовательность следует передавать с помощью [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) или [ref](../../csharp/language-reference/keywords/ref.md). Передача `ReadOnlySequence<T>` посредством `in` или `ref` позволяет сократить количество копирований [структуры](../../csharp/language-reference/builtin-types/struct.md).
- Пустые сегменты:
  - Допускаются в `ReadOnlySequence<T>`.
  - Могут появиться при итерации с помощью метода `ReadOnlySequence<T>.TryGet`.
  - Могут появиться при разбиении последовательности с помощью метода `ReadOnlySequence<T>.Slice()` с объектами `SequencePosition`.

## <a name="sequencereadert"></a>SequenceReader\<T\>

<xref:System.Buffers.SequenceReader%601>:

- Новый тип, который появился в .NET Core 3.0. Он позволяет упростить обработку `ReadOnlySequence<T>`.
- Обобщает различия между `ReadOnlySequence<T>` с одним сегментом и `ReadOnlySequence<T>` с несколькими сегментами.
- Предоставляет вспомогательные методы для чтения двоичных и текстовых данных (`byte` и `char`), которые можно разбивать на сегменты.

Существуют встроенные методы обработки двоичных данных и данных с разделителями. В следующем разделе показано, как выглядят те же методы при использовании с `SequenceReader<T>`.

### <a name="access-data"></a>Доступ к данным

`SequenceReader<T>` содержит методы для перечисления данных непосредственно в `ReadOnlySequence<T>`. В следующем коде приведен пример обработки `ReadOnlySequence<byte>` (`byte`) за один раз.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

`CurrentSpan` предоставляет `Span` текущего сегмента, что аналогично операциям в методе, которые выполнялись вручную.

### <a name="use-position"></a>Использование позиции

В следующем коде приведен пример реализации `FindIndexOf` с использованием `SequenceReader<T>`:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a>Обработка двоичных данных

В следующем примере обрабатывается целое число (длиной 4 байта) с обратным порядком байтов с начала `ReadOnlySequence<byte>`.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a>Обработка текстовых данных

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a>Распространенные проблемы c SequenceReader\<T\>

- `SequenceReader<T>` представляет собой изменяемую структуру, которую всегда нужно передавать с помощью [ссылки](../../csharp/language-reference/keywords/ref.md).
- `SequenceReader<T>` — это [ссылочная структура](../../csharp/language-reference/keywords/ref.md#ref-struct-types), которую можно использовать только в синхронных методах и нельзя хранить в полях. Дополнительные сведения см. в статье [Написание безопасного и эффективного кода C#](../../csharp/write-safe-efficient-code.md).
- Структура `SequenceReader<T>` оптимизирована для использования в качестве средства чтения с последовательным доступом. `Rewind` предназначается для небольших резервных копий, к которым нельзя обращаться с использованием других API `Read`, `Peek` и `IsNext`.
