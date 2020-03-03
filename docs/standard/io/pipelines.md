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
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627556"
---
# <a name="systemiopipelines-in-net"></a><span data-ttu-id="f0e0e-103">System.IO.Pipelines в .NET</span><span class="sxs-lookup"><span data-stu-id="f0e0e-103">System.IO.Pipelines in .NET</span></span>

<span data-ttu-id="f0e0e-104"><xref:System.IO.Pipelines> — это новая библиотека, предназначенная для упрощения высокопроизводительных операций ввода-вывода в .NET.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-104"><xref:System.IO.Pipelines> is a new library that is designed to make it easier to do high-performance I/O in .NET.</span></span> <span data-ttu-id="f0e0e-105">Это библиотека, предназначенная для .NET Standard, которая работает во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-105">It’s a library targeting .NET Standard that works on all .NET implementations.</span></span>

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a><span data-ttu-id="f0e0e-106">Какие задачи решает System.IO.Pipelines</span><span class="sxs-lookup"><span data-stu-id="f0e0e-106">What problem does System.IO.Pipelines solve</span></span>

<!-- corner case doesn't MT (machine translate)   -->
<span data-ttu-id="f0e0e-107">Приложения, которые анализируют потоковые данные, состоят из стандартного кода, имеющего множество специализированных и необычных потоков кода.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-107">Apps that parse streaming data are composed of boilerplate code having many specialized and unusual code flows.</span></span> <span data-ttu-id="f0e0e-108">Стандартный и специальный код сложен, и его трудно поддерживать.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-108">The boilerplate and special case code is complex and difficult to maintain.</span></span>

<span data-ttu-id="f0e0e-109">Возможности `System.IO.Pipelines`:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-109">`System.IO.Pipelines` was architected to:</span></span>

* <span data-ttu-id="f0e0e-110">Высокопроизводительный анализ потоковых данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-110">Have high performance parsing streaming data.</span></span>
* <span data-ttu-id="f0e0e-111">Упрощение кода.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-111">Reduce code complexity.</span></span>

<span data-ttu-id="f0e0e-112">Следующий код является типичным для TCP-сервера, который получает сообщения с разделенными строками (разделитель — `'\n'`) от клиента:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-112">The following code is typical for a TCP server that receives line-delimited messages (delimited by `'\n'`) from a client:</span></span>

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

<span data-ttu-id="f0e0e-113">В предыдущем коде несколько проблем:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-113">The preceding code has several problems:</span></span>

* <span data-ttu-id="f0e0e-114">Не все сообщение (конец строки) может быть получено в одном вызове `ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-114">The entire message (end of line) might not be received in a single call to `ReadAsync`.</span></span>
* <span data-ttu-id="f0e0e-115">Игнорируется результат `stream.ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-115">It's ignoring the result of `stream.ReadAsync`.</span></span> <span data-ttu-id="f0e0e-116">`stream.ReadAsync` возвращает объем считанных данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-116">`stream.ReadAsync` returns how much data was read.</span></span>
* <span data-ttu-id="f0e0e-117">Он не обрабатывает случай, когда несколько строк считываются в одном вызове `ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-117">It doesn't handle the case where multiple lines are read in a single `ReadAsync` call.</span></span>
* <span data-ttu-id="f0e0e-118">Он выделяет массив `byte` при каждом чтении.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-118">It allocates a `byte` array with each read.</span></span>

<span data-ttu-id="f0e0e-119">Чтобы устранить предыдущие проблемы, необходимо внести следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-119">To fix the preceding problems, the following changes are required:</span></span>

* <span data-ttu-id="f0e0e-120">Помещение входящих данных в буфер до тех пор, пока не будет найдена новая строка.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-120">Buffer the incoming data until a new line is found.</span></span>
* <span data-ttu-id="f0e0e-121">Синтаксический анализ всех строк, возвращенных в буфер.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-121">Parse all the lines returned in the buffer.</span></span>
* <span data-ttu-id="f0e0e-122">Возможно, длина строки превышает 1 КБ (1024 байт).</span><span class="sxs-lookup"><span data-stu-id="f0e0e-122">It's possible that the line is bigger than 1 KB (1024 bytes).</span></span> <span data-ttu-id="f0e0e-123">Код должен изменять размер входного буфера до тех пор, пока не будет найден разделитель, чтобы вместить всю строку в буфере.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-123">The code needs to resize the input buffer until the delimiter is found in order to fit the complete line inside the buffer.</span></span>

  * <span data-ttu-id="f0e0e-124">Если размер буфера изменить, создаются дополнительные буферные копии, так как во входных данных отображаются более длинные строки.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-124">If the buffer is resized, more buffer copies are made as longer lines appear in the input.</span></span>
  * <span data-ttu-id="f0e0e-125">Чтобы уменьшить объем неиспользуемого пространства, необходимо сжать буфер, используемый для чтения строк.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-125">To reduce wasted space, compact the buffer used for reading lines.</span></span>

* <span data-ttu-id="f0e0e-126">Рекомендуется использовать буферные пулы, чтобы избежать повторного выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-126">Consider using buffer pooling to avoid allocating memory repeatedly.</span></span>
* <span data-ttu-id="f0e0e-127">В следующем коде решаются некоторые из этих проблем:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-127">The following code addresses some of these problems:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs?name=snippet)]

<span data-ttu-id="f0e0e-128">Предыдущий код является сложным и не предназначен для устранения всех обнаруженных проблем.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-128">The previous code is complex and doesn't address all the problems identified.</span></span> <span data-ttu-id="f0e0e-129">Высокая производительность сети обычно означает написание очень сложного кода для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-129">High-performance networking usually means writing very complex code to maximize performance.</span></span> <span data-ttu-id="f0e0e-130">`System.IO.Pipelines` был разработан для упрощения написания этого типа кода.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-130">`System.IO.Pipelines` was designed to make writing this type of code easier.</span></span>

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a><span data-ttu-id="f0e0e-131">Pipe</span><span class="sxs-lookup"><span data-stu-id="f0e0e-131">Pipe</span></span>

<span data-ttu-id="f0e0e-132">Класс <xref:System.IO.Pipelines.Pipe> можно использовать для создания пары `PipeWriter/PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-132">The <xref:System.IO.Pipelines.Pipe> class can be used to create a `PipeWriter/PipeReader` pair.</span></span> <span data-ttu-id="f0e0e-133">Все данные, записанные в `PipeWriter`, доступны в `PipeReader`:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-133">All data written into the `PipeWriter` is available in the `PipeReader`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet2)]

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a><span data-ttu-id="f0e0e-134">Основное использование канала</span><span class="sxs-lookup"><span data-stu-id="f0e0e-134">Pipe basic usage</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet)]

<span data-ttu-id="f0e0e-135">Существует два цикла:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-135">There are two loops:</span></span>

* <span data-ttu-id="f0e0e-136">`FillPipeAsync` считывает из `Socket` и выполняет запись в `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-136">`FillPipeAsync` reads from the `Socket` and writes to the `PipeWriter`.</span></span>
* <span data-ttu-id="f0e0e-137">`ReadPipeAsync` считывает из `PipeReader` и анализирует входящие строки.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-137">`ReadPipeAsync` reads from the `PipeReader` and parses incoming lines.</span></span>

<span data-ttu-id="f0e0e-138">Буферы явно не выделяются.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-138">There are no explicit buffers allocated.</span></span> <span data-ttu-id="f0e0e-139">Управление всеми буферами делегируется реализациям `PipeReader` и `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-139">All buffer management is delegated to the `PipeReader` and `PipeWriter` implementations.</span></span> <span data-ttu-id="f0e0e-140">Делегирование управления буфером упрощает использование кода, чтобы сосредоточиться только на бизнес-логике.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-140">Delegating buffer management makes it easier for consuming code to focus solely on the business logic.</span></span>

<span data-ttu-id="f0e0e-141">В первом цикле:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-141">In the first loop:</span></span>

* <span data-ttu-id="f0e0e-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> вызывается для получения памяти от базового модуля записи.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> is called to get memory from the underlying writer.</span></span>
* <span data-ttu-id="f0e0e-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> вызывается, чтобы сообщить `PipeWriter`, сколько данных было записано в буфер.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> is called to tell the `PipeWriter` how much data was written to the buffer.</span></span>
* <span data-ttu-id="f0e0e-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> вызывается, чтобы сделать данные доступными для `PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> is called to make the data available to the `PipeReader`.</span></span>

<span data-ttu-id="f0e0e-145">Во втором цикле `PipeReader` использует буферы, записанные `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-145">In the second loop, the `PipeReader` consumes the buffers written by `PipeWriter`.</span></span> <span data-ttu-id="f0e0e-146">Буферы поступают из сокета.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-146">The buffers come from the socket.</span></span> <span data-ttu-id="f0e0e-147">Вызов `PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-147">The call to `PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="f0e0e-148">Возвращает <xref:System.IO.Pipelines.ReadResult>, который содержит два важных элемента информации:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-148">Returns a <xref:System.IO.Pipelines.ReadResult> that contains two important pieces of information:</span></span>

  * <span data-ttu-id="f0e0e-149">Данные, считанные в форме `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-149">The data that was read in the form of `ReadOnlySequence<byte>`.</span></span>
  * <span data-ttu-id="f0e0e-150">Логическое значение `IsCompleted`, указывающее, достигнут ли конец данных (EOF).</span><span class="sxs-lookup"><span data-stu-id="f0e0e-150">A boolean `IsCompleted` that indicates if the end of data (EOF) has been reached.</span></span>

<span data-ttu-id="f0e0e-151">После нахождения разделителя конца строки (EOL) и синтаксического анализа строки:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-151">After finding the end of line (EOL) delimiter and parsing the line:</span></span>

* <span data-ttu-id="f0e0e-152">Логика обрабатывает буфер, чтобы пропустить уже обработанные данные.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-152">The logic processes the buffer to skip what's already processed.</span></span>
* <span data-ttu-id="f0e0e-153">`PipeReader.AdvanceTo` вызывается, чтобы сообщить `PipeReader`, сколько данных было обработано и проверено.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-153">`PipeReader.AdvanceTo` is called to tell the `PipeReader` how much data has been consumed and examined.</span></span>

<span data-ttu-id="f0e0e-154">Циклы чтения и записи заканчиваются вызовом `Complete`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-154">The reader and writer loops end by calling `Complete`.</span></span> <span data-ttu-id="f0e0e-155">`Complete` позволяет базовому каналу освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-155">`Complete` lets the underlying Pipe release the memory it allocated.</span></span>

### <a name="backpressure-and-flow-control"></a><span data-ttu-id="f0e0e-156">Обратная реакция и управление потоком</span><span class="sxs-lookup"><span data-stu-id="f0e0e-156">Backpressure and flow control</span></span>

<span data-ttu-id="f0e0e-157">В идеале чтение и анализ работают вместе:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-157">Ideally, reading and parsing work together:</span></span>

* <span data-ttu-id="f0e0e-158">Поток записи потребляет данные из сети и помещает их в буферы.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-158">The writing thread consumes data from the network and puts it in buffers.</span></span>
* <span data-ttu-id="f0e0e-159">Поток анализа отвечает за построение соответствующих структур данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-159">The parsing thread is responsible for constructing the appropriate data structures.</span></span>

<span data-ttu-id="f0e0e-160">Обычно синтаксический анализ занимает больше времени, чем копирование блоков данных из сети:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-160">Typically, parsing takes more time than just copying blocks of data from the network:</span></span>

* <span data-ttu-id="f0e0e-161">Поток чтения идет впереди потока синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-161">The reading thread gets ahead of the parsing thread.</span></span>
* <span data-ttu-id="f0e0e-162">Поток чтения должен либо замедлить работу, либо выделить больше памяти для хранения данных для потока синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-162">The reading thread has to either slow down or allocate more memory to store the data for the parsing thread.</span></span>

<span data-ttu-id="f0e0e-163">Для оптимальной производительности необходим баланс между частыми паузами и выделением большего объема памяти.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-163">For optimal performance, there's a balance between frequent pauses and allocating more memory.</span></span>

<span data-ttu-id="f0e0e-164">Чтобы устранить описанную выше проблему, `Pipe` имеет два параметра для управления потоком данных:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-164">To solve the preceding problem, the `Pipe` has two settings to control the flow of data:</span></span>

* <span data-ttu-id="f0e0e-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Определяет, сколько данных следует буферизовать, прежде чем вызовы к <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> будут приостановлены.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determines how much data should be buffered before calls to <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pause.</span></span>
* <span data-ttu-id="f0e0e-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Определяет, сколько данных средство чтения должно пронаблюдать, прежде чем вызовы к `PipeWriter.FlushAsync` возобновятся.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determines how much data the reader has to observe before calls to `PipeWriter.FlushAsync` resume.</span></span>

![Схема с ResumeWriterThreshold и PauseWriterThreshold](./media/pipelines/resume-pause.png)

<span data-ttu-id="f0e0e-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="f0e0e-169">Возвращает неполный `ValueTask<FlushResult>`, если объем данных в `Pipe` пересекает `PauseWriterThreshold`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-169">Returns an incomplete `ValueTask<FlushResult>` when the amount of data in the `Pipe` crosses `PauseWriterThreshold`.</span></span>
* <span data-ttu-id="f0e0e-170">Завершает `ValueTask<FlushResult>`, когда он становится меньше `ResumeWriterThreshold`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-170">Completes `ValueTask<FlushResult>` when it becomes lower than `ResumeWriterThreshold`.</span></span>

<span data-ttu-id="f0e0e-171">Для предотвращения быстрого цикла, который может возникнуть при одном значении, используются два значения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-171">Two values are used to prevent rapid cycling, which can occur if one value is used.</span></span>

### <a name="examples"></a><span data-ttu-id="f0e0e-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0e0e-172">Examples</span></span>

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a><span data-ttu-id="f0e0e-173">PipeScheduler</span><span class="sxs-lookup"><span data-stu-id="f0e0e-173">PipeScheduler</span></span>

<span data-ttu-id="f0e0e-174">Обычно при использовании `async` и `await` асинхронный код возобновляется в <xref:System.Threading.Tasks.TaskScheduler> либо в текущем <xref:System.Threading.SynchronizationContext>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-174">Typically when using `async` and `await`, asynchronous code resumes on either on a <xref:System.Threading.Tasks.TaskScheduler> or on the current  <xref:System.Threading.SynchronizationContext>.</span></span>

<span data-ttu-id="f0e0e-175">При выполнении операций ввода-вывода важно иметь точный контроль над местом выполнения операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-175">When doing I/O, it's important to have fine-grained control over where the I/O is performed.</span></span> <span data-ttu-id="f0e0e-176">Этот контроль позволяет эффективно использовать кэш ЦП.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-176">This control allows taking advantage of CPU caches effectively.</span></span> <span data-ttu-id="f0e0e-177">Эффективное кэширование является критически важным для высокопроизводительных приложений, таких как веб-серверы.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-177">Efficient caching is critical for high-performance apps like web servers.</span></span> <span data-ttu-id="f0e0e-178"><xref:System.IO.Pipelines.PipeScheduler> предоставляет контроль над тем, где выполняются асинхронные обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-178"><xref:System.IO.Pipelines.PipeScheduler> provides control over where asynchronous callbacks run.</span></span> <span data-ttu-id="f0e0e-179">По умолчанию:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-179">By default:</span></span>

* <span data-ttu-id="f0e0e-180">используется текущий <xref:System.Threading.SynchronizationContext>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-180">The current <xref:System.Threading.SynchronizationContext> is used.</span></span>
* <span data-ttu-id="f0e0e-181">Если `SynchronizationContext` отсутствует, он использует пул потоков для выполнения обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-181">If there's no `SynchronizationContext`, it uses the thread pool to run callbacks.</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Program.cs?name=snippet)]

<span data-ttu-id="f0e0e-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) — это реализация <xref:System.IO.Pipelines.PipeScheduler>, которая позволяет поместить обратные вызовы в очередь пула потоков.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) is the <xref:System.IO.Pipelines.PipeScheduler> implementation that queues callbacks to the thread pool.</span></span> <span data-ttu-id="f0e0e-183">`PipeScheduler.ThreadPool` является параметром по умолчанию и, как правило, лучшим выбором.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-183">`PipeScheduler.ThreadPool` is the default and generally the best choice.</span></span> <span data-ttu-id="f0e0e-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) может привести к непредвиденным последствиям, например к взаимоблокировкам.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) can cause unintended consequences such as deadlocks.</span></span>

### <a name="pipe-reset"></a><span data-ttu-id="f0e0e-185">Сброс канала</span><span class="sxs-lookup"><span data-stu-id="f0e0e-185">Pipe reset</span></span>

<span data-ttu-id="f0e0e-186">Зачастую бывает эффективно повторно использовать объект `Pipe`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-186">It's frequently efficient to reuse the `Pipe` object.</span></span> <span data-ttu-id="f0e0e-187">Чтобы сбросить канал, вызовите <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> при завершении `PipeReader` и `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-187">To reset the pipe, call <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> when both the `PipeReader` and `PipeWriter` are complete.</span></span>

## <a name="pipereader"></a><span data-ttu-id="f0e0e-188">PipeReader</span><span class="sxs-lookup"><span data-stu-id="f0e0e-188">PipeReader</span></span>

<span data-ttu-id="f0e0e-189"><xref:System.IO.Pipelines.PipeReader> управляет памятью от имени вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-189"><xref:System.IO.Pipelines.PipeReader> manages memory on the caller's behalf.</span></span> <span data-ttu-id="f0e0e-190">**Всегда** вызывайте <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> после вызова <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-190">**Always** call <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> after calling <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f0e0e-191">Это позволяет `PipeReader` узнать, когда вызывающий объект закончил использовать память, чтобы его можно было отследить.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-191">This lets the `PipeReader` know when the caller is done with the memory so that it can be tracked.</span></span> <span data-ttu-id="f0e0e-192">`ReadOnlySequence<byte>`, возвращенный из `PipeReader.ReadAsync`, допустим только до вызова `PipeReader.AdvanceTo`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-192">The `ReadOnlySequence<byte>` returned from `PipeReader.ReadAsync` is only valid until the call the `PipeReader.AdvanceTo`.</span></span> <span data-ttu-id="f0e0e-193">Использование `ReadOnlySequence<byte>` после вызова `PipeReader.AdvanceTo` недопустимо.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-193">It's illegal to use `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo`.</span></span>

<span data-ttu-id="f0e0e-194">`PipeReader.AdvanceTo` принимает два аргумента <xref:System.SequencePosition>:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-194">`PipeReader.AdvanceTo` takes two <xref:System.SequencePosition> arguments:</span></span>

* <span data-ttu-id="f0e0e-195">Первый аргумент определяет объем используемой памяти.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-195">The first argument determines how much memory was consumed.</span></span>
* <span data-ttu-id="f0e0e-196">Второй аргумент определяет, какая часть буфера наблюдалась.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-196">The second argument determines how much of the buffer was observed.</span></span>

<span data-ttu-id="f0e0e-197">Если пометить данные как потребленные, канал сможет вернуть память в базовый буферный пул.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-197">Marking data as consumed means that the pipe can return the memory to the underlying buffer pool.</span></span> <span data-ttu-id="f0e0e-198">Пометка данных как отмеченных управляет тем, что делает следующий вызов `PipeReader.ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-198">Marking data as observed controls what the next call to `PipeReader.ReadAsync` does.</span></span> <span data-ttu-id="f0e0e-199">Пометка всех элементов как отмеченных означает, что следующий вызов `PipeReader.ReadAsync` не вернется, пока в канал не будет записано больше данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-199">Marking everything as observed means that the next call to `PipeReader.ReadAsync` won't return until there's more data written to the pipe.</span></span> <span data-ttu-id="f0e0e-200">Любое другое значение заставит следующий вызов `PipeReader.ReadAsync` вернуться немедленно с отмеченными *и* неотмеченными, но уже потребленными данными.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-200">Any other value will make the next call to `PipeReader.ReadAsync` return immediately with the observed *and* unobserved data, but data that has already been consumed.</span></span>

### <a name="read-streaming-data-scenarios"></a><span data-ttu-id="f0e0e-201">Сценарии чтения потоковых данных</span><span class="sxs-lookup"><span data-stu-id="f0e0e-201">Read streaming data scenarios</span></span>

<span data-ttu-id="f0e0e-202">Существует несколько типичных шаблонов, которые возникают при попытке чтения потоковых данных:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-202">There are a couple of typical patterns that emerge when trying to read streaming data:</span></span>

* <span data-ttu-id="f0e0e-203">При получении потока данных анализировать одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-203">Given a stream of data, parse a single message.</span></span>
* <span data-ttu-id="f0e0e-204">При получении потока данных анализировать все доступные сообщения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-204">Given a stream of data, parse all available messages.</span></span>

<span data-ttu-id="f0e0e-205">В следующих примерах используется метод `TryParseMessage` для синтаксического анализа сообщений из `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-205">The following examples use the `TryParseMessage` method for parsing messages from a `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="f0e0e-206">`TryParseMessage` анализирует одно сообщение и обновляет входной буфер, чтобы обрезать проанализированное сообщение из буфера.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-206">`TryParseMessage` parses a single message and update the input buffer to trim the parsed message from the buffer.</span></span> <span data-ttu-id="f0e0e-207">`TryParseMessage` не является частью .NET, это написанный пользователем метод, который используется в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-207">`TryParseMessage` is not part of .NET, it's a user written method used in the following sections.</span></span>

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a><span data-ttu-id="f0e0e-208">Чтение одного сообщения</span><span class="sxs-lookup"><span data-stu-id="f0e0e-208">Read a single message</span></span>

<span data-ttu-id="f0e0e-209">Следующий код считывает одно сообщение из `PipeReader` и возвращает его вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-209">The following code reads a single message from a `PipeReader` and returns it to the caller.</span></span>

[!code-csharp[ReadSingleMsg](~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs?name=snippet)]

<span data-ttu-id="f0e0e-210">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-210">The preceding code:</span></span>

* <span data-ttu-id="f0e0e-211">анализирует одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-211">Parses a single message.</span></span>
* <span data-ttu-id="f0e0e-212">Обновляет потребленный `SequencePosition` и изученный `SequencePosition`, чтобы указать на начало обрезанного входного буфера.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-212">Updates the consumed `SequencePosition` and examined `SequencePosition` to point to the start of the trimmed input buffer.</span></span>

<span data-ttu-id="f0e0e-213">Два аргумента `SequencePosition` обновляются, так как `TryParseMessage` удаляет проанализированное сообщение из входного буфера.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-213">The two `SequencePosition` arguments are updated because `TryParseMessage` removes the parsed message from the input buffer.</span></span> <span data-ttu-id="f0e0e-214">Как правило, при синтаксическом анализе одного сообщения из буфера изученное расположение должно быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-214">Generally, when parsing a single message from the buffer, the examined position should be one of the following:</span></span>

* <span data-ttu-id="f0e0e-215">Конец сообщения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-215">The end of the message.</span></span>
* <span data-ttu-id="f0e0e-216">Конец полученного буфера, если сообщение не найдено.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-216">The end of the received buffer if no message was found.</span></span>

<span data-ttu-id="f0e0e-217">В случае с одним сообщением риск ошибок наиболее велик.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-217">The single message case has the most potential for errors.</span></span> <span data-ttu-id="f0e0e-218">Передача неверных значений в *изученное* может привести к исключению нехватки памяти или бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-218">Passing the wrong values to *examined* can result in an out of memory exception or an infinite loop.</span></span> <span data-ttu-id="f0e0e-219">Дополнительные сведения см. в разделе [Распространенные проблемы PipeReader](#gotchas) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-219">For more information, see the [PipeReader common problems](#gotchas) section in this article.</span></span>

### <a name="reading-multiple-messages"></a><span data-ttu-id="f0e0e-220">Чтение нескольких сообщений</span><span class="sxs-lookup"><span data-stu-id="f0e0e-220">Reading multiple messages</span></span>

<span data-ttu-id="f0e0e-221">Следующий код считывает все сообщения из `PipeReader` и вызывает `ProcessMessageAsync` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-221">The following code reads all messages from a `PipeReader` and calls `ProcessMessageAsync` on each.</span></span>

[!code-csharp[MyConnection1](~/samples/snippets/csharp/pipelines/MyConnection1.cs?name=snippet)]

### <a name="cancellation"></a><span data-ttu-id="f0e0e-222">Отмена</span><span class="sxs-lookup"><span data-stu-id="f0e0e-222">Cancellation</span></span>

<span data-ttu-id="f0e0e-223">`PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-223">`PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="f0e0e-224">Поддерживает передачу <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-224">Supports passing a <xref:System.Threading.CancellationToken>.</span></span>
* <span data-ttu-id="f0e0e-225">Создает исключение <xref:System.OperationCanceledException>, если `CancellationToken` отменяется при ожидании чтения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-225">Throws an <xref:System.OperationCanceledException> if the `CancellationToken` is canceled while there's a read pending.</span></span>
* <span data-ttu-id="f0e0e-226">Поддерживает способ отмены текущей операции чтения с помощью <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, что позволяет избежать исключения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-226">Supports a way to cancel the current read operation via <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, which avoids raising an exception.</span></span> <span data-ttu-id="f0e0e-227">Вызов `PipeReader.CancelPendingRead` приводит к тому, что текущий или следующий вызов `PipeReader.ReadAsync` возвращает <xref:System.IO.Pipelines.ReadResult> с `IsCanceled` со значением `true`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-227">Calling `PipeReader.CancelPendingRead` causes the current or next call to `PipeReader.ReadAsync` to return a <xref:System.IO.Pipelines.ReadResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="f0e0e-228">Это может быть полезно для остановки существующего цикла чтения без сбоев и исключений.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-228">This can be useful for halting the existing read loop in a non-destructive and non-exceptional way.</span></span>

[!code-csharp[MyConnection](~/samples/snippets/csharp/pipelines/MyConnection.cs?name=snippet)]

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a><span data-ttu-id="f0e0e-229">Распространенные проблемы PipeReader</span><span class="sxs-lookup"><span data-stu-id="f0e0e-229">PipeReader common problems</span></span>

* <span data-ttu-id="f0e0e-230">Передача неверных значений в `consumed` или `examined` может привести к считыванию уже считанных данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-230">Passing the wrong values to `consumed` or `examined` may result in reading already read data.</span></span>
* <span data-ttu-id="f0e0e-231">Передача `buffer.End` как изученного может привести к следующему:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-231">Passing `buffer.End` as examined may result in:</span></span>

  * <span data-ttu-id="f0e0e-232">Остановленные данные</span><span class="sxs-lookup"><span data-stu-id="f0e0e-232">Stalled data</span></span>
  * <span data-ttu-id="f0e0e-233">Может возникать исключение нехватки памяти, если данные не потребляются.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-233">Possibly an eventual Out of Memory (OOM) exception if data isn't consumed.</span></span> <span data-ttu-id="f0e0e-234">Например, `PipeReader.AdvanceTo(position, buffer.End)` при обработке одного сообщения за раз из буфера.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-234">For example, `PipeReader.AdvanceTo(position, buffer.End)` when processing a single message at a time from the buffer.</span></span>

* <span data-ttu-id="f0e0e-235">Передача неверных значений в `consumed` или `examined` может привести к бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-235">Passing the wrong values to `consumed` or `examined` may result in an infinite loop.</span></span> <span data-ttu-id="f0e0e-236">Например, `PipeReader.AdvanceTo(buffer.Start)`, если `buffer.Start` не изменился, приведет к тому, что следующий вызов `PipeReader.ReadAsync` вернется немедленно перед поступлением новых данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-236">For example, `PipeReader.AdvanceTo(buffer.Start)` if `buffer.Start` hasn't changed will cause the next call to `PipeReader.ReadAsync` to return immediately before new data arrives.</span></span>
* <span data-ttu-id="f0e0e-237">Передача неверных значений в `consumed` или `examined` может привести к бесконечной буферизации (и нехватке памяти в конечном итоге).</span><span class="sxs-lookup"><span data-stu-id="f0e0e-237">Passing the wrong values to `consumed` or `examined` may result in infinite buffering (eventual OOM).</span></span>
* <span data-ttu-id="f0e0e-238">Использование `ReadOnlySequence<byte>` после вызова `PipeReader.AdvanceTo` может привести к повреждению памяти (используйте после освобождения).</span><span class="sxs-lookup"><span data-stu-id="f0e0e-238">Using the `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo` may result in memory corruption (use after free).</span></span>
* <span data-ttu-id="f0e0e-239">Отсутствие вызова `PipeReader.Complete/CompleteAsync` может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-239">Failing to call `PipeReader.Complete/CompleteAsync` may result in a memory leak.</span></span>
* <span data-ttu-id="f0e0e-240">Проверка <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> и выход из логики чтения до обработки буфера приводит к потере данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-240">Checking <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> and exiting the reading logic before processing the buffer results in data loss.</span></span> <span data-ttu-id="f0e0e-241">Условие выхода цикла должно основываться на `ReadResult.Buffer.IsEmpty` и `ReadResult.IsCompleted`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-241">The loop exit condition should be based on `ReadResult.Buffer.IsEmpty` and `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="f0e0e-242">Неправильное выполнение этого действия может привести к бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-242">Doing this incorrectly could result in an infinite loop.</span></span>

#### <a name="problematic-code"></a><span data-ttu-id="f0e0e-243">Проблемный код</span><span class="sxs-lookup"><span data-stu-id="f0e0e-243">Problematic code</span></span>

<span data-ttu-id="f0e0e-244">❌ **Потеря данных**</span><span class="sxs-lookup"><span data-stu-id="f0e0e-244">❌ **Data loss**</span></span>

<span data-ttu-id="f0e0e-245">`ReadResult` может возвращать окончательный сегмент данных, если `IsCompleted` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-245">The `ReadResult` can return the final segment of data when `IsCompleted` is set to `true`.</span></span> <span data-ttu-id="f0e0e-246">Если не считать эти данные до выхода из цикла чтения, данные будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-246">Not reading that data before exiting the read loop will result in data loss.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#1](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="f0e0e-247">❌ **Бесконечный цикл**</span><span class="sxs-lookup"><span data-stu-id="f0e0e-247">❌ **Infinite loop**</span></span>

<span data-ttu-id="f0e0e-248">Следующая логика может привести к бесконечному циклу, если `Result.IsCompleted` равно `true`, но в буфере никогда нет полного сообщения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-248">The following logic may result in an infinite loop if the `Result.IsCompleted` is `true` but there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#2](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet2)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="f0e0e-249">Вот еще один фрагмент кода с такой же проблемой.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-249">Here's another piece of code with the same problem.</span></span> <span data-ttu-id="f0e0e-250">Проверяется наличие непустого буфера перед проверкой `ReadResult.IsCompleted`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-250">It's checking for a non-empty buffer before checking `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="f0e0e-251">Так как он находится в `else if`, цикл будет повторяться бесконечно, если в буфере никогда не будет полного сообщения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-251">Because it's in an `else if`, it will loop forever if there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#3](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet3)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="f0e0e-252">❌ **Непредвиденное зависание**</span><span class="sxs-lookup"><span data-stu-id="f0e0e-252">❌ **Unexpected Hang**</span></span>

<span data-ttu-id="f0e0e-253">Безусловный вызов `PipeReader.AdvanceTo` с `buffer.End` в положении `examined` может привести к зависанию при анализе одного сообщения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-253">Unconditionally calling `PipeReader.AdvanceTo` with `buffer.End` in the `examined` position may result in hangs when parsing a single message.</span></span> <span data-ttu-id="f0e0e-254">Следующий вызов `PipeReader.AdvanceTo` вернет значение только в следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-254">The next call to `PipeReader.AdvanceTo` won't return until:</span></span>

* <span data-ttu-id="f0e0e-255">В канал записано больше данных.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-255">There's more data written to the pipe.</span></span>
* <span data-ttu-id="f0e0e-256">Новые данные не были проверены ранее.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-256">And the new data wasn't previously examined.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#4](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet4)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="f0e0e-257">❌ **Нехватка памяти**</span><span class="sxs-lookup"><span data-stu-id="f0e0e-257">❌ **Out of Memory (OOM)**</span></span>

<span data-ttu-id="f0e0e-258">В следующих случаях приведенный ниже код сохраняет буферизацию до тех пор, пока не произойдет <xref:System.OutOfMemoryException>:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-258">With the following conditions, the following code keeps buffering until an <xref:System.OutOfMemoryException> occurs:</span></span>

* <span data-ttu-id="f0e0e-259">Максимальный размер сообщения не указан.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-259">There's no maximum message size.</span></span>
* <span data-ttu-id="f0e0e-260">Данные, возвращенные из `PipeReader`, не составляют полное сообщение.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-260">The data returned from the `PipeReader` doesn't make a complete message.</span></span> <span data-ttu-id="f0e0e-261">Например, они не составляют полное сообщение, поскольку другая сторона записывает большое сообщение (например, сообщение размером 4 ГБ).</span><span class="sxs-lookup"><span data-stu-id="f0e0e-261">For example, it doesn't make a complete message because the other side is writing a large message (For example, a 4-GB message).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#5](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet5)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="f0e0e-262">❌ **Повреждение памяти**</span><span class="sxs-lookup"><span data-stu-id="f0e0e-262">❌ **Memory Corruption**</span></span>

<span data-ttu-id="f0e0e-263">При написании вспомогательных методов, считывающих буфер, все возвращенные полезные данные должны быть скопированы перед вызовом `Advance`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-263">When writing helpers that read the buffer, any returned payload should be copied before calling `Advance`.</span></span> <span data-ttu-id="f0e0e-264">В следующем примере возвращается память, которая была удалена `Pipe` и может использоваться повторно для следующей операции (чтение или запись).</span><span class="sxs-lookup"><span data-stu-id="f0e0e-264">The following example will return memory that the `Pipe` has discarded and may reuse it for the next operation (read/write).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#Message](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippetMessage)]

[!code-csharp[DoNotUse#6](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet6)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a><span data-ttu-id="f0e0e-265">PipeWriter</span><span class="sxs-lookup"><span data-stu-id="f0e0e-265">PipeWriter</span></span>

<span data-ttu-id="f0e0e-266"><xref:System.IO.Pipelines.PipeWriter> управляет буферами для записи от имени вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-266">The <xref:System.IO.Pipelines.PipeWriter> manages buffers for writing on the caller's behalf.</span></span> <span data-ttu-id="f0e0e-267">`PipeWriter` реализует [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span><span class="sxs-lookup"><span data-stu-id="f0e0e-267">`PipeWriter` implements [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span></span> <span data-ttu-id="f0e0e-268">`IBufferWriter<byte>` позволяет получить доступ к буферам для выполнения операций записи без дополнительных буферных копий.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-268">`IBufferWriter<byte>` makes it possible to get access to buffers to perform writes without additional buffer copies.</span></span>

[!code-csharp[MyPipeWriter](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet)]

<span data-ttu-id="f0e0e-269">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-269">The previous code:</span></span>

* <span data-ttu-id="f0e0e-270">Запрашивает буфер длиной не менее 5 байт у `PipeWriter` с помощью <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-270">Requests a buffer of at least 5 bytes from the `PipeWriter` using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span></span>
* <span data-ttu-id="f0e0e-271">Записывает байты для строки ASCII `"Hello"` в возвращенный `Memory<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-271">Writes bytes for the ASCII string `"Hello"` to the returned `Memory<byte>`.</span></span>
* <span data-ttu-id="f0e0e-272">Вызывает <xref:System.IO.Pipelines.PipeWriter.Advance%2A>, чтобы указать, сколько байтов было записано в буфер.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-272">Calls <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to indicate how many bytes were written to the buffer.</span></span>
* <span data-ttu-id="f0e0e-273">Очищает `PipeWriter`, который отправляет байты на базовое устройство.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-273">Flushes the `PipeWriter`, which sends the bytes to the underlying device.</span></span>

<span data-ttu-id="f0e0e-274">Предыдущий метод записи использует буферы, предоставленные `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-274">The previous method of writing uses the buffers provided by the `PipeWriter`.</span></span> <span data-ttu-id="f0e0e-275">В противном случае <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f0e0e-275">Alternatively, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="f0e0e-276">Копирует существующий буфер в `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-276">Copies the existing buffer to the `PipeWriter`.</span></span>
* <span data-ttu-id="f0e0e-277">Вызывает `GetSpan`, выполняет `Advance` надлежащим образом и вызывает <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-277">Calls `GetSpan`, `Advance` as appropriate and calls <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span></span>

[!code-csharp[MyPipeWriter#2](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet2)]

### <a name="cancellation"></a><span data-ttu-id="f0e0e-278">Отмена</span><span class="sxs-lookup"><span data-stu-id="f0e0e-278">Cancellation</span></span>

<span data-ttu-id="f0e0e-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> поддерживает передачу <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supports passing a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="f0e0e-280">Передача `CancellationToken` приводит к исключению `OperationCanceledException`, если маркер отменяется в ожидании освобождения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-280">Passing a `CancellationToken` results in an `OperationCanceledException` if the token is canceled while there's a flush pending.</span></span> <span data-ttu-id="f0e0e-281">`PipeWriter.FlushAsync` поддерживает способ отмены текущей операции освобождения с помощью <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType>, не вызывая исключение.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-281">`PipeWriter.FlushAsync` supports a way to cancel the current flush operation via <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> without raising an exception.</span></span> <span data-ttu-id="f0e0e-282">Вызов `PipeWriter.CancelPendingFlush` приводит к тому, что текущий или следующий вызов `PipeWriter.FlushAsync` или `PipeWriter.WriteAsync` возвращает <xref:System.IO.Pipelines.FlushResult> с `IsCanceled` со значением `true`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-282">Calling `PipeWriter.CancelPendingFlush` causes the current or next call to `PipeWriter.FlushAsync` or `PipeWriter.WriteAsync` to return a <xref:System.IO.Pipelines.FlushResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="f0e0e-283">Это может быть полезно для остановки освобождения без сбоев и исключений.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-283">This can be useful for halting the yielding flush in a non-destructive and non-exceptional way.</span></span>

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a><span data-ttu-id="f0e0e-284">Распространенные проблемы PipeWriter</span><span class="sxs-lookup"><span data-stu-id="f0e0e-284">PipeWriter common problems</span></span>

* <span data-ttu-id="f0e0e-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> и <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> возвращают буфер по крайней мере с запрошенным объемом памяти.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> and <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="f0e0e-286">**Не** рассчитывайте на точный размер буфера.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-286">**Don't** assume exact buffer sizes.</span></span>
* <span data-ttu-id="f0e0e-287">Нет никакой гарантии, что последовательные вызовы будут возвращать один и тот же буфер или буфер того же размера.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-287">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
* <span data-ttu-id="f0e0e-288">Чтобы продолжить запись дополнительных данных, необходимо запросить новый буфер после вызова <xref:System.IO.Pipelines.PipeWriter.Advance%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-288">A new buffer must be requested after calling <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to continue writing more data.</span></span> <span data-ttu-id="f0e0e-289">Запись в ранее полученный буфер невозможна.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-289">The previously acquired buffer can't be written to.</span></span>
* <span data-ttu-id="f0e0e-290">Вызов `GetMemory` или `GetSpan` при наличии незавершенного вызова `FlushAsync` не является надежным.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-290">Calling `GetMemory` or `GetSpan` while there's an incomplete call to `FlushAsync` isn't safe.</span></span>
* <span data-ttu-id="f0e0e-291">Вызов `Complete` или `CompleteAsync` при наличии неосвобожденных данных может привести к повреждению памяти.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-291">Calling `Complete` or `CompleteAsync` while there's unflushed data can result in memory corruption.</span></span>

## <a name="iduplexpipe"></a><span data-ttu-id="f0e0e-292">IDuplexPipe</span><span class="sxs-lookup"><span data-stu-id="f0e0e-292">IDuplexPipe</span></span>

<span data-ttu-id="f0e0e-293"><xref:System.IO.Pipelines.IDuplexPipe> является контрактом для типов, поддерживающих чтение и запись.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-293">The <xref:System.IO.Pipelines.IDuplexPipe> is a contract for types that support both reading and writing.</span></span> <span data-ttu-id="f0e0e-294">Например, сетевое подключение будет представлено `IDuplexPipe`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-294">For example, a network connection would be represented by an `IDuplexPipe`.</span></span>

 <span data-ttu-id="f0e0e-295">В отличие от `Pipe`, который содержит `PipeReader` и `PipeWriter`, `IDuplexPipe` представляет собой одну сторону полного дуплексного подключения.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-295">Unlike `Pipe` which contains a `PipeReader` and a `PipeWriter`, `IDuplexPipe` represents a single side of a full duplex connection.</span></span> <span data-ttu-id="f0e0e-296">Это означает, что запись в `PipeWriter` не будет считываться из `PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-296">That means what is written to the `PipeWriter` will not be read from the `PipeReader`.</span></span>

## <a name="streams"></a><span data-ttu-id="f0e0e-297">Потоки</span><span class="sxs-lookup"><span data-stu-id="f0e0e-297">Streams</span></span>

<span data-ttu-id="f0e0e-298">При чтении или записи потоковых данных данные обычно считываются с помощью десериализатора и записываются с помощью сериализатора.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-298">When reading or writing stream data, you typically read data using a de-serializer and write data using a serializer.</span></span> <span data-ttu-id="f0e0e-299">Большая часть API потока чтения и записи имеет параметр `Stream`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-299">Most of these read and write stream APIs have a `Stream` parameter.</span></span> <span data-ttu-id="f0e0e-300">Чтобы упростить интеграцию с существующими API, `PipeReader` и `PipeWriter` предоставляют <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-300">To make it easier to integrate with these existing APIs, `PipeReader` and `PipeWriter` expose an <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.</span></span>  <span data-ttu-id="f0e0e-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> возвращает реализацию `Stream` на основе `PipeReader` или `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="f0e0e-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> returns a `Stream` implementation around the `PipeReader` or `PipeWriter`.</span></span>
