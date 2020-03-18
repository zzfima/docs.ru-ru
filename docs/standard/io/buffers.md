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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160122"
---
# <a name="work-with-buffers-in-net"></a><span data-ttu-id="ce306-102">Работа с буферами в .NET</span><span class="sxs-lookup"><span data-stu-id="ce306-102">Work with Buffers in .NET</span></span>

<span data-ttu-id="ce306-103">В этой статье описаны типы, которые помогают выполнять чтение данных, проходящих через несколько буферов.</span><span class="sxs-lookup"><span data-stu-id="ce306-103">This article provides an overview of types that help read data that runs across multiple buffers.</span></span> <span data-ttu-id="ce306-104">В основном они используются для поддержки объектов <xref:System.IO.Pipelines.PipeReader>.</span><span class="sxs-lookup"><span data-stu-id="ce306-104">They're primarily used to support <xref:System.IO.Pipelines.PipeReader> objects.</span></span>

## <a name="ibufferwritert"></a><span data-ttu-id="ce306-105">IBufferWriter\<T\></span><span class="sxs-lookup"><span data-stu-id="ce306-105">IBufferWriter\<T\></span></span>

<span data-ttu-id="ce306-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> — это контракт для синхронной записи в буфер.</span><span class="sxs-lookup"><span data-stu-id="ce306-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> is a contract for synchronous buffered writing.</span></span> <span data-ttu-id="ce306-107">Интерфейс обладает такими базовыми характеристиками:</span><span class="sxs-lookup"><span data-stu-id="ce306-107">At the lowest level, the interface:</span></span>

- <span data-ttu-id="ce306-108">он простой и его легко использовать;</span><span class="sxs-lookup"><span data-stu-id="ce306-108">Is basic and not difficult to use.</span></span>
- <span data-ttu-id="ce306-109">он обеспечивает доступ к <xref:System.Memory%601> или <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="ce306-109">Allows access to a <xref:System.Memory%601> or <xref:System.Span%601>.</span></span> <span data-ttu-id="ce306-110">`Memory<T>` или `Span<T>` поддерживают функцию записи, и вы можете узнать, сколько элементов `T` было записано.</span><span class="sxs-lookup"><span data-stu-id="ce306-110">The `Memory<T>` or `Span<T>` can be written to and you can determine how many `T` items were written.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

<span data-ttu-id="ce306-111">Предыдущий метод выполняет такие действия:</span><span class="sxs-lookup"><span data-stu-id="ce306-111">The preceding method:</span></span>

- <span data-ttu-id="ce306-112">Запрашивает буфер длиной не менее 5 байт у `IBufferWriter<byte>` с помощью `GetSpan(5)`.</span><span class="sxs-lookup"><span data-stu-id="ce306-112">Requests a buffer of at least 5 bytes from the `IBufferWriter<byte>` using `GetSpan(5)`.</span></span>
- <span data-ttu-id="ce306-113">Записывает байты для строки Hello (ASCII) при получении `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-113">Writes bytes for the ASCII string "Hello" to the returned `Span<byte>`.</span></span>
- <span data-ttu-id="ce306-114">Вызывает <xref:System.Buffers.IBufferWriter%601>, чтобы указать, сколько байтов было записано в буфер.</span><span class="sxs-lookup"><span data-stu-id="ce306-114">Calls  <xref:System.Buffers.IBufferWriter%601> to indicate how many bytes were written to the buffer.</span></span>

<span data-ttu-id="ce306-115">Этот метод записи использует буфер `Memory<T>`/`Span<T>`, предоставленный `IBufferWriter<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-115">This method of writing uses the `Memory<T>`/`Span<T>` buffer provided by the `IBufferWriter<T>`.</span></span> <span data-ttu-id="ce306-116">Можно также использовать метод расширения <xref:System.Buffers.BuffersExtensions.Write%2A> для копирования существующего буфера в `IBufferWriter<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-116">Alternatively, the <xref:System.Buffers.BuffersExtensions.Write%2A> extension method can be used to copy an existing buffer to the `IBufferWriter<T>`.</span></span> <span data-ttu-id="ce306-117">`Write` вызывает `GetSpan`/`Advance` соответствующим образом, поэтому нет необходимости вызывать `Advance` после записи.</span><span class="sxs-lookup"><span data-stu-id="ce306-117">`Write` does the work of calling `GetSpan`/`Advance` as appropriate, so there's no need to call `Advance` after writing:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<span data-ttu-id="ce306-118"><xref:System.Buffers.ArrayBufferWriter%601> является реализацией `IBufferWriter<T>`, чье резервное хранилище представляет собой единый смежный массив.</span><span class="sxs-lookup"><span data-stu-id="ce306-118"><xref:System.Buffers.ArrayBufferWriter%601> is an implementation of `IBufferWriter<T>` whose backing store is a single contiguous array.</span></span>

### <a name="ibufferwriter-common-problems"></a><span data-ttu-id="ce306-119">Распространенные проблемы с IBufferWriter</span><span class="sxs-lookup"><span data-stu-id="ce306-119">IBufferWriter common problems</span></span>

- <span data-ttu-id="ce306-120">`GetSpan` и `GetMemory` возвращают буфер по крайней мере с запрошенным объемом памяти.</span><span class="sxs-lookup"><span data-stu-id="ce306-120">`GetSpan` and `GetMemory` return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="ce306-121">Не рассчитывайте на точный размер буфера.</span><span class="sxs-lookup"><span data-stu-id="ce306-121">Don't assume exact buffer sizes.</span></span>
- <span data-ttu-id="ce306-122">Нет никакой гарантии, что последовательные вызовы будут возвращать один и тот же буфер или буфер того же размера.</span><span class="sxs-lookup"><span data-stu-id="ce306-122">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
- <span data-ttu-id="ce306-123">Чтобы продолжить запись дополнительных данных, необходимо запросить новый буфер после вызова `Advance`.</span><span class="sxs-lookup"><span data-stu-id="ce306-123">A new buffer must be requested after calling `Advance` to continue writing more data.</span></span> <span data-ttu-id="ce306-124">Невозможно выполнить запись в ранее полученный буфер после вызова `Advance`.</span><span class="sxs-lookup"><span data-stu-id="ce306-124">A previously acquired buffer cannot be written to after `Advance` has been called.</span></span>

## <a name="readonlysequencet"></a><span data-ttu-id="ce306-125">ReadOnlySequence\<T\></span><span class="sxs-lookup"><span data-stu-id="ce306-125">ReadOnlySequence\<T\></span></span>

![ReadOnlySequence: показана область памяти в канале, а под ней показана позиция последовательности в памяти, доступной только для чтения](media/buffers/ro-sequence.png)

<span data-ttu-id="ce306-127"><xref:System.Buffers.ReadOnlySequence%601> — это структура, которая может представлять смежную или несмежную последовательность `T`.</span><span class="sxs-lookup"><span data-stu-id="ce306-127"><xref:System.Buffers.ReadOnlySequence%601> is a struct that can represent a contiguous or noncontiguous sequence of `T`.</span></span> <span data-ttu-id="ce306-128">Она может состоять из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="ce306-128">It can be constructed from:</span></span>

1. <span data-ttu-id="ce306-129">`T[]`;</span><span class="sxs-lookup"><span data-stu-id="ce306-129">A `T[]`</span></span>
1. <span data-ttu-id="ce306-130">`ReadOnlyMemory<T>`;</span><span class="sxs-lookup"><span data-stu-id="ce306-130">A `ReadOnlyMemory<T>`</span></span>
1. <span data-ttu-id="ce306-131">Пара узла связанного списка <xref:System.Buffers.ReadOnlySequenceSegment%601> и индекса, представляющая начальную и конечную позицию последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce306-131">A pair of linked list node <xref:System.Buffers.ReadOnlySequenceSegment%601> and index to represent the start and end position of the sequence.</span></span>

<span data-ttu-id="ce306-132">Третье представление является наиболее интересным, так как оно влияет на производительность различных операций с `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-132">The third representation is the most interesting one as it has performance implications on various operations on the `ReadOnlySequence<T>`:</span></span>

|<span data-ttu-id="ce306-133">Представление</span><span class="sxs-lookup"><span data-stu-id="ce306-133">Representation</span></span>|<span data-ttu-id="ce306-134">Операция</span><span class="sxs-lookup"><span data-stu-id="ce306-134">Operation</span></span>|<span data-ttu-id="ce306-135">Сложность</span><span class="sxs-lookup"><span data-stu-id="ce306-135">Complexity</span></span>|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

<span data-ttu-id="ce306-136">Из-за такого смешанного представления `ReadOnlySequence<T>` предоставляет индексы в виде `SequencePosition`, а не целого числа.</span><span class="sxs-lookup"><span data-stu-id="ce306-136">Because of this mixed representation, the `ReadOnlySequence<T>` exposes indexes as `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="ce306-137">Характеристики `SequencePosition`:</span><span class="sxs-lookup"><span data-stu-id="ce306-137">A `SequencePosition`:</span></span>

- <span data-ttu-id="ce306-138">Это скрытое значение, представляющее индекс в `ReadOnlySequence<T>`, где он был создан.</span><span class="sxs-lookup"><span data-stu-id="ce306-138">Is an opaque value that represents an index into the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="ce306-139">Состоит из двух частей: целого числа и объекта.</span><span class="sxs-lookup"><span data-stu-id="ce306-139">Consists of two parts, an integer and an object.</span></span> <span data-ttu-id="ce306-140">Представление этих двух значений связано с реализацией `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-140">What these two values represent are tied to the implementation of `ReadOnlySequence<T>`.</span></span>

### <a name="access-data"></a><span data-ttu-id="ce306-141">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="ce306-141">Access data</span></span>

<span data-ttu-id="ce306-142">`ReadOnlySequence<T>` предоставляет данные в виде перечислимого типа `ReadOnlyMemory<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-142">The `ReadOnlySequence<T>` exposes data as an enumerable of `ReadOnlyMemory<T>`.</span></span> <span data-ttu-id="ce306-143">Перечисление каждого сегмента можно выполнить с помощью простого цикла foreach:</span><span class="sxs-lookup"><span data-stu-id="ce306-143">Enumerating each of the segments can be done using a basic foreach:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

<span data-ttu-id="ce306-144">Описанный выше метод ищет все сегменты с определенным количеством байт.</span><span class="sxs-lookup"><span data-stu-id="ce306-144">The preceding method searches each segment for a specific byte.</span></span> <span data-ttu-id="ce306-145">Для отслеживания значения `SequencePosition` каждого сегмента больше подойдет <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce306-145">If you need to keep track of each segment's `SequencePosition`, <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> is more appropriate.</span></span> <span data-ttu-id="ce306-146">В следующем примере мы изменили приведенный выше код, чтобы он возвращал `SequencePosition` вместо целого числа.</span><span class="sxs-lookup"><span data-stu-id="ce306-146">The next sample changes the preceding code to return a `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="ce306-147">При возврате значения `SequencePosition` вызывающий может пропустить вторую проверку для получения данных в определенном индексе.</span><span class="sxs-lookup"><span data-stu-id="ce306-147">Returning a `SequencePosition` has the benefit of allowing the caller to avoid a second scan to get the data at a specific index.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

<span data-ttu-id="ce306-148">Сочетание `SequencePosition` и `TryGet` выполняет функции перечислителя.</span><span class="sxs-lookup"><span data-stu-id="ce306-148">The combination of `SequencePosition` and `TryGet` acts like an enumerator.</span></span> <span data-ttu-id="ce306-149">Поле позиции изменяется в начале каждой итерации для того, чтобы оно находилось в начале каждого сегмента в `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-149">The position field is modified at the start of each iteration to be start of each segment within the `ReadOnlySequence<T>`.</span></span>

<span data-ttu-id="ce306-150">Предыдущий метод используется в качестве метода расширения в `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-150">The preceding method exists as an extension method on `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="ce306-151">Чтобы упростить предыдущий код, можно использовать <xref:System.Buffers.BuffersExtensions.PositionOf%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce306-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A> can be used to simplify the preceding code:</span></span>

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a><span data-ttu-id="ce306-152">Обработка ReadOnlySequence\<T\></span><span class="sxs-lookup"><span data-stu-id="ce306-152">Process a ReadOnlySequence\<T\></span></span>

<span data-ttu-id="ce306-153">Обработка `ReadOnlySequence<T>` может оказаться сложной задачей, так как данные могут находиться в нескольких сегментах в последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce306-153">Processing a `ReadOnlySequence<T>` can be challenging since data may be split across multiple segments within the sequence.</span></span> <span data-ttu-id="ce306-154">Для лучшей производительности разделите код на две задачи:</span><span class="sxs-lookup"><span data-stu-id="ce306-154">For the best performance, split code into two paths:</span></span>

- <span data-ttu-id="ce306-155">более быстрая задача для операции с одним сегментом;</span><span class="sxs-lookup"><span data-stu-id="ce306-155">A fast path that deals with the single segment case.</span></span>
- <span data-ttu-id="ce306-156">более медленная задача для операций с данными, распределенными между несколькими сегментами.</span><span class="sxs-lookup"><span data-stu-id="ce306-156">A slow path that deals with the data split across segments.</span></span>

<span data-ttu-id="ce306-157">Существует несколько способов обработки данных в последовательностях с несколькими сегментами:</span><span class="sxs-lookup"><span data-stu-id="ce306-157">There are a few approaches that can be used to process data in multi-segmented sequences:</span></span>

- <span data-ttu-id="ce306-158">Используйте [`SequenceReader<T>`](#sequencereadert).</span><span class="sxs-lookup"><span data-stu-id="ce306-158">Use the [`SequenceReader<T>`](#sequencereadert).</span></span>
- <span data-ttu-id="ce306-159">Анализируйте данные по сегментам. При этом следите за значением `SequencePosition` и индексом в проанализированном сегменте.</span><span class="sxs-lookup"><span data-stu-id="ce306-159">Parse data segment by segment, keeping track of the `SequencePosition` and index within the segment parsed.</span></span> <span data-ttu-id="ce306-160">Это позволяет избежать ненужного распределения. Но такой способ может оказаться неэффективным, особенно для небольших буферов.</span><span class="sxs-lookup"><span data-stu-id="ce306-160">This avoids unnecessary allocations but may be inefficient, especially for small buffers.</span></span>
- <span data-ttu-id="ce306-161">Скопируйте `ReadOnlySequence<T>` в смежный массив и работайте с ним как с отдельным буфером.</span><span class="sxs-lookup"><span data-stu-id="ce306-161">Copy the `ReadOnlySequence<T>` to a contiguous array and treat it like a single buffer:</span></span>
  - <span data-ttu-id="ce306-162">Если размер `ReadOnlySequence<T>` небольшой, возможно, лучше будет скопировать данные в буфер, размещенный в стеке, с помощью оператора [stackalloc](../../csharp/language-reference/operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="ce306-162">If the size of the `ReadOnlySequence<T>` is small, it may be reasonable to copy the data into a stack-allocated buffer using the [stackalloc](../../csharp/language-reference/operators/stackalloc.md) operator.</span></span>
  - <span data-ttu-id="ce306-163">Скопируйте `ReadOnlySequence<T>` в массив в пуле с помощью <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce306-163">Copy the `ReadOnlySequence<T>` into a pooled array using <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="ce306-164">Используйте [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span><span class="sxs-lookup"><span data-stu-id="ce306-164">Use [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span></span> <span data-ttu-id="ce306-165">Не рекомендуется использовать в критических путях, так как выделяется новый экземпляр `T[]` в куче.</span><span class="sxs-lookup"><span data-stu-id="ce306-165">This isn't recommended in hot paths as it allocates a new `T[]` on the heap.</span></span>

<span data-ttu-id="ce306-166">В следующих примерах показаны некоторые распространенные сценарии обработки `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-166">The following examples demonstrate some common cases for processing `ReadOnlySequence<byte>`:</span></span>

##### <a name="process-binary-data"></a><span data-ttu-id="ce306-167">Обработка двоичных данных</span><span class="sxs-lookup"><span data-stu-id="ce306-167">Process binary data</span></span>

<span data-ttu-id="ce306-168">В следующем примере обрабатывается целое число (длиной 4 байта) с обратным порядком байтов с начала `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-168">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a><span data-ttu-id="ce306-169">Обработка текстовых данных</span><span class="sxs-lookup"><span data-stu-id="ce306-169">Process text data</span></span>

<span data-ttu-id="ce306-170">В следующем примере происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="ce306-170">The following example:</span></span>

- <span data-ttu-id="ce306-171">Выполняется поиск первого символа новой строки (`\r\n`) в `ReadOnlySequence<byte>`, которое возвращается через выходной параметр line.</span><span class="sxs-lookup"><span data-stu-id="ce306-171">Finds the first newline (`\r\n`) in the `ReadOnlySequence<byte>` and returns it via the out 'line' parameter.</span></span>
- <span data-ttu-id="ce306-172">Затем эта строка обрезается, исключая `\r\n` из входного буфера.</span><span class="sxs-lookup"><span data-stu-id="ce306-172">Trims that line, excluding the `\r\n` from the input buffer.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a><span data-ttu-id="ce306-173">Пустые сегменты</span><span class="sxs-lookup"><span data-stu-id="ce306-173">Empty segments</span></span>

<span data-ttu-id="ce306-174">Допускается хранение пустых сегментов в `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-174">It's valid to store empty segments inside of a `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="ce306-175">Пустые сегменты могут возникать при явном перечислении сегментов.</span><span class="sxs-lookup"><span data-stu-id="ce306-175">Empty segments may occur while enumerating segments explicitly:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

<span data-ttu-id="ce306-176">В предыдущем примере кода создается `ReadOnlySequence<byte>` с пустыми сегментами и показано, как эти пустые сегменты влияют на разные API:</span><span class="sxs-lookup"><span data-stu-id="ce306-176">The preceding code creates a `ReadOnlySequence<byte>` with empty segments and shows how those empty segments affect the various APIs:</span></span>

- <span data-ttu-id="ce306-177">Сочетание `ReadOnlySequence<T>.Slice` со структурой `SequencePosition`, указывающей на пустой сегмент, сохраняет такой сегмент.</span><span class="sxs-lookup"><span data-stu-id="ce306-177">`ReadOnlySequence<T>.Slice` with a `SequencePosition` pointing to an empty segment preserves that segment.</span></span>
- <span data-ttu-id="ce306-178">`ReadOnlySequence<T>.Slice` с int позволяет пропустить пустой сегмент.</span><span class="sxs-lookup"><span data-stu-id="ce306-178">`ReadOnlySequence<T>.Slice` with an int skips over the empty segments.</span></span>
- <span data-ttu-id="ce306-179">При перечислении `ReadOnlySequence<T>` перечисляются пустые сегменты.</span><span class="sxs-lookup"><span data-stu-id="ce306-179">Enumerating the `ReadOnlySequence<T>` enumerates the empty segments.</span></span>

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a><span data-ttu-id="ce306-180">Возможные проблемы с ReadOnlySequence\<T> и SequencePosition</span><span class="sxs-lookup"><span data-stu-id="ce306-180">Potential problems with ReadOnlySequence\<T> and SequencePosition</span></span>

<span data-ttu-id="ce306-181">При использовании `ReadOnlySequence<T>`/`SequencePosition` вместо обычной структуры `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int` могут возникнуть нетипичные результаты:</span><span class="sxs-lookup"><span data-stu-id="ce306-181">There are several unusual outcomes when dealing with a `ReadOnlySequence<T>`/`SequencePosition` vs. a normal `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`:</span></span>

- <span data-ttu-id="ce306-182">`SequencePosition` — это метка позиции определенного объекта `ReadOnlySequence<T>`, а не абсолютная позиция.</span><span class="sxs-lookup"><span data-stu-id="ce306-182">`SequencePosition` is a position marker for a specific `ReadOnlySequence<T>`, not an absolute position.</span></span> <span data-ttu-id="ce306-183">Так как эта метка связана с определенным типом `ReadOnlySequence<T>`, нет смысла ее использовать за пределами `ReadOnlySequence<T>`, где она была создана.</span><span class="sxs-lookup"><span data-stu-id="ce306-183">Because it's relative to a specific `ReadOnlySequence<T>`, it doesn't have meaning if used outside of the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="ce306-184">Арифметические операции с `SequencePosition` нельзя выполнять без `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-184">Arithmetic can't be performed on `SequencePosition` without the `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="ce306-185">Это означает, что при выполнении простых операций, например `position++`, записывается `ReadOnlySequence<T>.GetPosition(position, 1)`.</span><span class="sxs-lookup"><span data-stu-id="ce306-185">That means doing basic things like `position++` is written `ReadOnlySequence<T>.GetPosition(position, 1)`.</span></span>
- <span data-ttu-id="ce306-186">`GetPosition(long)`**не** поддерживает отрицательные индексы.</span><span class="sxs-lookup"><span data-stu-id="ce306-186">`GetPosition(long)` does **not** support negative indexes.</span></span> <span data-ttu-id="ce306-187">Таким образом, чтобы получить предпоследний символ, необходимо пройти все сегменты.</span><span class="sxs-lookup"><span data-stu-id="ce306-187">That means it's impossible to get the second to last character without walking all segments.</span></span>
- <span data-ttu-id="ce306-188">Нельзя сравнить два объекта `SequencePosition`, что затрудняет выполнение следующих задач:</span><span class="sxs-lookup"><span data-stu-id="ce306-188">Two `SequencePosition` can't be compared, making it difficult to:</span></span>
  - <span data-ttu-id="ce306-189">Определение того, является ли значение позиции больше или меньше по отношению к другой позиции.</span><span class="sxs-lookup"><span data-stu-id="ce306-189">Know if one position is greater than or less than another position.</span></span>
  - <span data-ttu-id="ce306-190">Написание некоторых алгоритмов анализа.</span><span class="sxs-lookup"><span data-stu-id="ce306-190">Write some parsing algorithms.</span></span>
- <span data-ttu-id="ce306-191">Размер последовательности `ReadOnlySequence<T>` больше чем у ссылки на объект, поэтому по возможности последовательность следует передавать с помощью [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) или [ref](../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="ce306-191">`ReadOnlySequence<T>` is bigger than an object reference and should be passed by [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../csharp/language-reference/keywords/ref.md) where possible.</span></span> <span data-ttu-id="ce306-192">Передача `ReadOnlySequence<T>` посредством `in` или `ref` позволяет сократить количество копирований [структуры](../../csharp/language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="ce306-192">Passing `ReadOnlySequence<T>` by `in` or `ref` reduces copies of the [struct](../../csharp/language-reference/builtin-types/struct.md).</span></span>
- <span data-ttu-id="ce306-193">Пустые сегменты:</span><span class="sxs-lookup"><span data-stu-id="ce306-193">Empty segments:</span></span>
  - <span data-ttu-id="ce306-194">Допускаются в `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-194">Are valid within a `ReadOnlySequence<T>`.</span></span>
  - <span data-ttu-id="ce306-195">Могут появиться при итерации с помощью метода `ReadOnlySequence<T>.TryGet`.</span><span class="sxs-lookup"><span data-stu-id="ce306-195">Can appear when iterating using the `ReadOnlySequence<T>.TryGet` method.</span></span>
  - <span data-ttu-id="ce306-196">Могут появиться при разбиении последовательности с помощью метода `ReadOnlySequence<T>.Slice()` с объектами `SequencePosition`.</span><span class="sxs-lookup"><span data-stu-id="ce306-196">Can appear slicing the sequence using the `ReadOnlySequence<T>.Slice()` method with `SequencePosition` objects.</span></span>

## <a name="sequencereadert"></a><span data-ttu-id="ce306-197">SequenceReader\<T\></span><span class="sxs-lookup"><span data-stu-id="ce306-197">SequenceReader\<T\></span></span>

<span data-ttu-id="ce306-198"><xref:System.Buffers.SequenceReader%601>:</span><span class="sxs-lookup"><span data-stu-id="ce306-198"><xref:System.Buffers.SequenceReader%601>:</span></span>

- <span data-ttu-id="ce306-199">Новый тип, который появился в .NET Core 3.0. Он позволяет упростить обработку `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-199">Is a new type that was introduced in .NET Core 3.0 to simplify the processing of a `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="ce306-200">Обобщает различия между `ReadOnlySequence<T>` с одним сегментом и `ReadOnlySequence<T>` с несколькими сегментами.</span><span class="sxs-lookup"><span data-stu-id="ce306-200">Unifies the differences between a single segment `ReadOnlySequence<T>` and multi-segment `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="ce306-201">Предоставляет вспомогательные методы для чтения двоичных и текстовых данных (`byte` и `char`), которые можно разбивать на сегменты.</span><span class="sxs-lookup"><span data-stu-id="ce306-201">Provides helpers for reading binary and text data (`byte` and `char`) that may or may not be split across segments.</span></span>

<span data-ttu-id="ce306-202">Существуют встроенные методы обработки двоичных данных и данных с разделителями.</span><span class="sxs-lookup"><span data-stu-id="ce306-202">There are built-in methods for dealing with processing both binary and delimited data.</span></span> <span data-ttu-id="ce306-203">В следующем разделе показано, как выглядят те же методы при использовании с `SequenceReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-203">The following section demonstrates what those same methods look like with the `SequenceReader<T>`:</span></span>

### <a name="access-data"></a><span data-ttu-id="ce306-204">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="ce306-204">Access data</span></span>

<span data-ttu-id="ce306-205">`SequenceReader<T>` содержит методы для перечисления данных непосредственно в `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-205">`SequenceReader<T>` has methods for enumerating data inside of the `ReadOnlySequence<T>` directly.</span></span> <span data-ttu-id="ce306-206">В следующем коде приведен пример обработки `ReadOnlySequence<byte>` (`byte`) за один раз.</span><span class="sxs-lookup"><span data-stu-id="ce306-206">The following code is an example of processing a `ReadOnlySequence<byte>` a `byte` at a time:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

<span data-ttu-id="ce306-207">`CurrentSpan` предоставляет `Span` текущего сегмента, что аналогично операциям в методе, которые выполнялись вручную.</span><span class="sxs-lookup"><span data-stu-id="ce306-207">The `CurrentSpan` exposes the current segment's `Span`, which is similar to what was done in the method manually.</span></span>

### <a name="use-position"></a><span data-ttu-id="ce306-208">Использование позиции</span><span class="sxs-lookup"><span data-stu-id="ce306-208">Use position</span></span>

<span data-ttu-id="ce306-209">В следующем коде приведен пример реализации `FindIndexOf` с использованием `SequenceReader<T>`:</span><span class="sxs-lookup"><span data-stu-id="ce306-209">The following code is an example implementation of `FindIndexOf` using the `SequenceReader<T>`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a><span data-ttu-id="ce306-210">Обработка двоичных данных</span><span class="sxs-lookup"><span data-stu-id="ce306-210">Process binary data</span></span>

<span data-ttu-id="ce306-211">В следующем примере обрабатывается целое число (длиной 4 байта) с обратным порядком байтов с начала `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="ce306-211">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a><span data-ttu-id="ce306-212">Обработка текстовых данных</span><span class="sxs-lookup"><span data-stu-id="ce306-212">Process text data</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a><span data-ttu-id="ce306-213">Распространенные проблемы c SequenceReader\<T\></span><span class="sxs-lookup"><span data-stu-id="ce306-213">SequenceReader\<T\> common problems</span></span>

- <span data-ttu-id="ce306-214">`SequenceReader<T>` представляет собой изменяемую структуру, которую всегда нужно передавать с помощью [ссылки](../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="ce306-214">Because `SequenceReader<T>` is a mutable struct, it should always be passed by [reference](../../csharp/language-reference/keywords/ref.md).</span></span>
- <span data-ttu-id="ce306-215">`SequenceReader<T>` — это [ссылочная структура](../../csharp/language-reference/keywords/ref.md#ref-struct-types), которую можно использовать только в синхронных методах и нельзя хранить в полях.</span><span class="sxs-lookup"><span data-stu-id="ce306-215">`SequenceReader<T>` is a [ref struct](../../csharp/language-reference/keywords/ref.md#ref-struct-types) so it can only be used in synchronous methods and can't be stored in fields.</span></span> <span data-ttu-id="ce306-216">Дополнительные сведения см. в статье [Написание безопасного и эффективного кода C#](../../csharp/write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="ce306-216">For more information, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>
- <span data-ttu-id="ce306-217">Структура `SequenceReader<T>` оптимизирована для использования в качестве средства чтения с последовательным доступом.</span><span class="sxs-lookup"><span data-stu-id="ce306-217">`SequenceReader<T>` is optimized for use as a forward-only reader.</span></span> <span data-ttu-id="ce306-218">`Rewind` предназначается для небольших резервных копий, к которым нельзя обращаться с использованием других API `Read`, `Peek` и `IsNext`.</span><span class="sxs-lookup"><span data-stu-id="ce306-218">`Rewind` is intended for small backups that can't be addressed utilizing other `Read`, `Peek`, and `IsNext` APIs.</span></span>
