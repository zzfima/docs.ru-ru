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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0e548989b1d2c32b9faf5ce0dd90ae371dfc028
ms.lasthandoff: 03/13/2017

---
# <a name="using-async-for-file-access-visual-basic"></a>Использование метода Async для доступа к файлам (Visual Basic)
Функция Async для доступа к файлам. С помощью функции Async можно вызывать асинхронные методы, не прибегая к использованию обратных вызовов или разделению кода между несколькими методами или лямбда-выражениями. Чтобы сделать синхронный код асинхронным, просто вызвать асинхронный метод вместо синхронного и добавить в код несколько ключевых слов.  
  
 Может потребоваться для добавления асинхронность для вызовов для доступа к следующим причинам:  
  
-   Асинхронность пользовательского интерфейса приложений делает отклика, так как поток пользовательского интерфейса, который запускает операцию может выполнять другую работу. Если поток пользовательского интерфейса должен выполняться код, занимает много времени (например, более чем 50 миллисекунд), пользовательский Интерфейс может ожидать завершения ввода-вывода и потока пользовательского интерфейса можно снова обработки клавиатуры и мыши ввода и другие события.  
  
-   Асинхронность повышает масштабируемость ASP.NET и других серверных приложений, сокращая потребность в потоки. Если приложение использует выделенный поток отклика на тысячи запросов одновременно обрабатывается, необходимы тысячи потоков. Асинхронных операций часто не требуется использовать поток во время ожидания. Они короткое время использовать существующий поток завершения ввода-вывода в конце.  
  
-   Задержка операцию доступа к файлу может быть очень низким при текущих условиях, но задержка может значительно повысить в будущем. Например файл можно переместить на сервер, по всему миру.  
  
-   Добавленный дополнительную нагрузку, связанную с помощью функции Async мал.  
  
-   Асинхронные задачи можно легко запускать параллельно.  
  
## <a name="running-the-examples"></a>Выполнение примеров  
 Чтобы выполнить примеры в этом разделе, можно создать **приложение WPF** или **приложение Windows Forms** и добавьте **кнопку**. Для кнопки `Click` события, добавьте вызов первого метода в каждом примере.  
  
 В следующих примерах, включают следующие `Imports` инструкции.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>Использование класса FileStream  
 Примеры в этом разделе используют <xref:System.IO.FileStream>класс, который имеет параметр, который вызывает асинхронный ввод-вывод на уровне операционной системы.</xref:System.IO.FileStream> При использовании этого параметра может блокировать поток из пула потоков во многих случаях. Чтобы включить этот параметр, необходимо указать `useAsync=true` или `options=FileOptions.Asynchronous` аргумента в вызове конструктора.  
  
 Этот параметр нельзя использовать с <xref:System.IO.StreamReader>и <xref:System.IO.StreamWriter>при их открытии непосредственно, путем указания пути файла.</xref:System.IO.StreamWriter> </xref:System.IO.StreamReader> Тем не менее, можно использовать этот параметр, если вы предоставили эту <xref:System.IO.Stream>, <xref:System.IO.FileStream>класс открыт.</xref:System.IO.FileStream> </xref:System.IO.Stream> Обратите внимание, что асинхронные вызовы быстрее в приложениях с интерфейсом пользователя даже если поток из пула потоков будет заблокирована, так как поток пользовательского интерфейса не блокируются во время ожидания.  
  
## <a name="writing-text"></a>Запись текста  
 Следующий пример записывает текст в файл. В каждом await инструкции, метод немедленно завершает работу. По завершении файлового ввода-вывода метод возобновляется с оператора, следующего за оператором await. Обратите внимание, что в определении методов, использующих оператор await модификатор async.  
  
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
  
 Исходный пример состоит из инструкции `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, который является сокращенной формой записи двух следующих операторов:  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 Первая инструкция возвращает задачу и приводит к обработке файла для запуска. Второй инструкции с оператором await вызывает метод немедленно выхода и возвращает другую задачу. После завершения обработки позже файлов, выполнение передается оператору, следующему за оператором await. Дополнительные сведения см. в разделе [поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Чтение текста  
 Следующий пример выполняет чтение текста из файла. Текст в буфер и, таким образом, помещается в <xref:System.Text.StringBuilder>.</xref:System.Text.StringBuilder> В отличие от предыдущего примера вычисление await создает значение. <xref:System.IO.Stream.ReadAsync%2A>Возвращает <xref:System.Threading.Tasks.Task> \< <xref:System.Int32>настроек, поэтому вычисление await выводятся `Int32` значение (`numRead`) после завершения операции.</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A> Дополнительные сведения см. в разделе [возвращают типы Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
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
  
## <a name="parallel-asynchronous-io"></a>Параллельных асинхронных операций ввода-вывода  
 Ниже приведен пример параллельной обработки, написав 10 текстовых файлов. Для каждого файла <xref:System.IO.Stream.WriteAsync%2A>метод возвращает задачу, которая затем добавляется в список задач.</xref:System.IO.Stream.WriteAsync%2A> `Await Task.WhenAll(tasks)` Инструкция завершает данный метод и резюме в методе при обработке файла завершения для всех задач.  
  
 В примере закрывается, все <xref:System.IO.FileStream>экземпляров в `Finally` блокируется после выполнения задач.</xref:System.IO.FileStream> Если каждый `FileStream` вместо этого была создана в `Imports` инструкции, `FileStream` может быть удален до завершения задачи.  
  
 Обратите внимание, что любой повысить производительность почти полностью от параллельной обработки и не асинхронной обработки. Преимущества асинхронность, что она не блокирует несколько потоков, и что она не блокирует поток пользовательского интерфейса.  
  
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
  
 При использовании <xref:System.IO.Stream.WriteAsync%2A>и <xref:System.IO.Stream.ReadAsync%2A>методов, можно указать <xref:System.Threading.CancellationToken>, который можно использовать для отмены операции ходу.</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A> Дополнительные сведения см. в разделе [Fine-Tuning асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) и [Отмена в управляемых потоках](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).  
  
## <a name="see-also"></a>См. также  
 [Асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Асинхронные типы возвращаемых значений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [Поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)
