---
title: "Использование метода Async для доступа к файлам (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 85f5fe17a012402c406eed972debd1f5889dd393
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="using-async-for-file-access-visual-basic"></a><span data-ttu-id="7f889-102">Использование метода Async для доступа к файлам (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f889-102">Using Async for File Access (Visual Basic)</span></span>
<span data-ttu-id="7f889-103">Функция Async для доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="7f889-103">You can use the Async feature to access files.</span></span> <span data-ttu-id="7f889-104">С помощью функции Async можно вызывать асинхронные методы, не прибегая к использованию обратных вызовов или разделению кода между несколькими методами или лямбда-выражениями.</span><span class="sxs-lookup"><span data-stu-id="7f889-104">By using the Async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="7f889-105">Чтобы сделать синхронный код асинхронным, просто вызвать асинхронный метод вместо синхронного и добавить в код несколько ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="7f889-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="7f889-106">Может потребоваться для добавления асинхронность для вызовов для доступа к следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="7f889-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
-   <span data-ttu-id="7f889-107">Асинхронность пользовательского интерфейса приложений делает отклика, так как поток пользовательского интерфейса, который запускает операцию может выполнять другую работу.</span><span class="sxs-lookup"><span data-stu-id="7f889-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="7f889-108">Если поток пользовательского интерфейса должен выполняться код, занимает много времени (например, более чем 50 миллисекунд), пользовательский Интерфейс может ожидать завершения ввода-вывода и потока пользовательского интерфейса можно снова обработки клавиатуры и мыши ввода и другие события.</span><span class="sxs-lookup"><span data-stu-id="7f889-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
-   <span data-ttu-id="7f889-109">Асинхронность повышает масштабируемость ASP.NET и других серверных приложений, сокращая потребность в потоки.</span><span class="sxs-lookup"><span data-stu-id="7f889-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="7f889-110">Если приложение использует выделенный поток отклика на тысячи запросов одновременно обрабатывается, необходимы тысячи потоков.</span><span class="sxs-lookup"><span data-stu-id="7f889-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="7f889-111">Асинхронных операций часто не требуется использовать поток во время ожидания.</span><span class="sxs-lookup"><span data-stu-id="7f889-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="7f889-112">Они короткое время использовать существующий поток завершения ввода-вывода в конце.</span><span class="sxs-lookup"><span data-stu-id="7f889-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
-   <span data-ttu-id="7f889-113">Задержка операцию доступа к файлу может быть очень низким при текущих условиях, но задержка может значительно повысить в будущем.</span><span class="sxs-lookup"><span data-stu-id="7f889-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="7f889-114">Например файл можно переместить на сервер, по всему миру.</span><span class="sxs-lookup"><span data-stu-id="7f889-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
-   <span data-ttu-id="7f889-115">Добавленный дополнительную нагрузку, связанную с помощью функции Async мал.</span><span class="sxs-lookup"><span data-stu-id="7f889-115">The added overhead of using the Async feature is small.</span></span>  
  
-   <span data-ttu-id="7f889-116">Асинхронные задачи можно легко запускать параллельно.</span><span class="sxs-lookup"><span data-stu-id="7f889-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="7f889-117">Выполнение примеров</span><span class="sxs-lookup"><span data-stu-id="7f889-117">Running the Examples</span></span>  
 <span data-ttu-id="7f889-118">Чтобы выполнить примеры в этом разделе, можно создать **приложение WPF** или **приложение Windows Forms** и добавьте **кнопку**.</span><span class="sxs-lookup"><span data-stu-id="7f889-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="7f889-119">Для кнопки `Click` события, добавьте вызов первого метода в каждом примере.</span><span class="sxs-lookup"><span data-stu-id="7f889-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="7f889-120">В следующих примерах, включают следующие `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7f889-120">In the following examples, include the following `Imports` statements.</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="7f889-121">Использование класса FileStream</span><span class="sxs-lookup"><span data-stu-id="7f889-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="7f889-122">Примеры в этом разделе используют <xref:System.IO.FileStream>класс, который имеет параметр, который вызывает асинхронный ввод-вывод на уровне операционной системы.</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="7f889-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="7f889-123">При использовании этого параметра может блокировать поток из пула потоков во многих случаях.</span><span class="sxs-lookup"><span data-stu-id="7f889-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="7f889-124">Чтобы включить этот параметр, необходимо указать `useAsync=true` или `options=FileOptions.Asynchronous` аргумента в вызове конструктора.</span><span class="sxs-lookup"><span data-stu-id="7f889-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="7f889-125">Этот параметр нельзя использовать с <xref:System.IO.StreamReader>и <xref:System.IO.StreamWriter>при их открытии непосредственно, путем указания пути файла.</xref:System.IO.StreamWriter> </xref:System.IO.StreamReader></span><span class="sxs-lookup"><span data-stu-id="7f889-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="7f889-126">Тем не менее, можно использовать этот параметр, если вы предоставили эту <xref:System.IO.Stream>, <xref:System.IO.FileStream>класс открыт.</xref:System.IO.FileStream> </xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="7f889-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="7f889-127">Обратите внимание, что асинхронные вызовы быстрее в приложениях с интерфейсом пользователя даже если поток из пула потоков будет заблокирована, так как поток пользовательского интерфейса не блокируются во время ожидания.</span><span class="sxs-lookup"><span data-stu-id="7f889-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="7f889-128">Запись текста</span><span class="sxs-lookup"><span data-stu-id="7f889-128">Writing Text</span></span>  
 <span data-ttu-id="7f889-129">Следующий пример записывает текст в файл.</span><span class="sxs-lookup"><span data-stu-id="7f889-129">The following example writes text to a file.</span></span> <span data-ttu-id="7f889-130">В каждом await инструкции, метод немедленно завершает работу.</span><span class="sxs-lookup"><span data-stu-id="7f889-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="7f889-131">По завершении файлового ввода-вывода метод возобновляется с оператора, следующего за оператором await.</span><span class="sxs-lookup"><span data-stu-id="7f889-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="7f889-132">Обратите внимание, что в определении методов, использующих оператор await модификатор async.</span><span class="sxs-lookup"><span data-stu-id="7f889-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 <span data-ttu-id="7f889-133">Исходный пример состоит из инструкции `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, который является сокращенной формой записи двух следующих операторов:</span><span class="sxs-lookup"><span data-stu-id="7f889-133">The original example has the statement `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, which is a contraction of the following two statements:</span></span>  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 <span data-ttu-id="7f889-134">Первая инструкция возвращает задачу и приводит к обработке файла для запуска.</span><span class="sxs-lookup"><span data-stu-id="7f889-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="7f889-135">Второй инструкции с оператором await вызывает метод немедленно выхода и возвращает другую задачу.</span><span class="sxs-lookup"><span data-stu-id="7f889-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="7f889-136">После завершения обработки позже файлов, выполнение передается оператору, следующему за оператором await.</span><span class="sxs-lookup"><span data-stu-id="7f889-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="7f889-137">Дополнительные сведения см. в разделе [поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="7f889-137">For more information, see  [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="7f889-138">Чтение текста</span><span class="sxs-lookup"><span data-stu-id="7f889-138">Reading Text</span></span>  
 <span data-ttu-id="7f889-139">Следующий пример выполняет чтение текста из файла.</span><span class="sxs-lookup"><span data-stu-id="7f889-139">The following example reads text from a file.</span></span> <span data-ttu-id="7f889-140">Текст в буфер и, таким образом, помещается в <xref:System.Text.StringBuilder>.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="7f889-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="7f889-141">В отличие от предыдущего примера вычисление await создает значение.</span><span class="sxs-lookup"><span data-stu-id="7f889-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="7f889-142"><xref:System.IO.Stream.ReadAsync%2A>Возвращает <xref:System.Threading.Tasks.Task> \< <xref:System.Int32>настроек, поэтому вычисление await выводятся `Int32` значение (`numRead`) после завершения операции.</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="7f889-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="7f889-143">Дополнительные сведения см. в разделе [возвращают типы Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f889-143">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="7f889-144">Параллельных асинхронных операций ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="7f889-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="7f889-145">Ниже приведен пример параллельной обработки, написав 10 текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="7f889-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="7f889-146">Для каждого файла <xref:System.IO.Stream.WriteAsync%2A>метод возвращает задачу, которая затем добавляется в список задач.</xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="7f889-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="7f889-147">`Await Task.WhenAll(tasks)` Инструкция завершает данный метод и резюме в методе при обработке файла завершения для всех задач.</span><span class="sxs-lookup"><span data-stu-id="7f889-147">The `Await Task.WhenAll(tasks)` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="7f889-148">В примере закрывается, все <xref:System.IO.FileStream>экземпляров в `Finally` блокируется после выполнения задач.</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="7f889-148">The example closes all <xref:System.IO.FileStream> instances in a `Finally` block after the tasks are complete.</span></span> <span data-ttu-id="7f889-149">Если каждый `FileStream` вместо этого была создана в `Imports` инструкции, `FileStream` может быть удален до завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="7f889-149">If each `FileStream` was instead created in a `Imports` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="7f889-150">Обратите внимание, что любой повысить производительность почти полностью от параллельной обработки и не асинхронной обработки.</span><span class="sxs-lookup"><span data-stu-id="7f889-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="7f889-151">Преимущества асинхронность, что она не блокирует несколько потоков, и что она не блокирует поток пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7f889-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 <span data-ttu-id="7f889-152">При использовании <xref:System.IO.Stream.WriteAsync%2A>и <xref:System.IO.Stream.ReadAsync%2A>методов, можно указать <xref:System.Threading.CancellationToken>, который можно использовать для отмены операции ходу.</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="7f889-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="7f889-153">Дополнительные сведения см. в разделе [Fine-Tuning асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) и [Отмена в управляемых потоках](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).</span><span class="sxs-lookup"><span data-stu-id="7f889-153">For more information, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f889-154">См. также</span><span class="sxs-lookup"><span data-stu-id="7f889-154">See Also</span></span>  
 <span data-ttu-id="7f889-155">[Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f889-155">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="7f889-156"> [Асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="7f889-156"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="7f889-157"> [Поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span><span class="sxs-lookup"><span data-stu-id="7f889-157"> [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span></span>
