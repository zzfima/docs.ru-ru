---
title: Использование метода async для доступа к файлам
ms.date: 07/20/2015
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
ms.openlocfilehash: 803d182f5b0f3071feb7aae4945bc3c0a1fd82c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349111"
---
# <a name="using-async-for-file-access-visual-basic"></a>Использование метода Async для доступа к файлам (Visual Basic)
Для доступа к файлам можно использовать функцию Async. С помощью возможности Async можно вызывать асинхронные методы, не прибегая к использованию обратных вызовов или разделению кода между несколькими методами или лямбда-выражениями. Для выполнения последовательного кода асинхронно просто вызовите асинхронный метод вместо синхронного метода и добавьте несколько ключевых слов в код.  
  
 Можно рассмотреть следующие причины для добавления асинхронности для вызовов для доступа к файлам.  
  
- Асинхронность делает приложения пользовательского интерфейса более отзывчивыми, потому что поток пользовательского интерфейса, который запускает операцию, может продолжать выполнять и другую работу. Если поток пользовательского интерфейса должен выполнять код, который занимает много времени (например, более 50 миллисекунд), пользовательский интерфейс можно приостановить до тех пор, пока не будет завершен ввод-вывод, и затем пользовательский интерфейс сможет снова обрабатывать ввод с клавиатуры, мыши и другие события.  
  
- Асинхронность улучшает масштабируемость ASP.NET и других серверных приложений за счет уменьшения необходимости использования потоков. Если приложение использует выделенный поток на ответ и тысяча запросов приходит одновременно, тысяча потоков не потребуется. Асинхронные операции часто не нуждаются в пользовании потоком во время ожидания. Они пользуются существующим потоком завершения ввода-вывода короткое время в конце.  
  
- Задержка операции доступа к файлу может быть очень низкой при текущих условиях, но может значительно увеличиться в будущем. Например, файл может быть перемещен на сервер через Интернет.  
  
- Добавленные издержки при использовании функции Async являются малыми.  
  
- Асинхронные задачи могут легко выполняться параллельно.  
  
## <a name="running-the-examples"></a>Выполнение примеров  
 Чтобы выполнить примеры в этом разделе, вы можете создать **приложение WPF** или **приложение Windows Forms**, а затем добавить **кнопку**. В событии `Click` кнопки добавьте вызов к первому методу в каждом примере.  
  
 В следующие примеры добавьте указанные ниже операторы`Imports`.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>Использование класса FileStream  
 В приведенных в этой статье примерах используется класс <xref:System.IO.FileStream>, содержащий параметр, который вызывает асинхронный ввод-вывод на уровне операционной системы. С помощью этого параметра можно избежать блокирования пула потоков во многих случаях. Чтобы включить этот параметр, необходимо добавить в вызов конструктора аргумент `useAsync=true` или `options=FileOptions.Asynchronous`.  
  
 Этот параметр нельзя использовать с классами <xref:System.IO.StreamReader> и <xref:System.IO.StreamWriter>, если вы открываете их напрямую (указав путь к файлу). При этом параметр можно использовать, если им предоставлен <xref:System.IO.Stream>, открытый классом <xref:System.IO.FileStream>. Обратите внимание, что асинхронные вызовы выполняются быстрее в приложениях пользовательского интерфейса, даже если поток в пуле потоков блокирован, поскольку поток пользовательского интерфейса не блокирован во время ожидания.  
  
## <a name="writing-text"></a>Запись текста  
 Следующие примеры записывают текст в файл. На каждой точке await происходит немедленный выход из метода. После завершения файлового ввода-вывода метод возобновляет работу с пункта, следующего за await. Обратите внимание, что модификатор async в определении методов требует наличия await в теле метода.  
  
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
  
 Первоначальная строка с оператором `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)` является сокращенной формой записи двух следующих операторов:  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 Первый оператор возвращает задачу и вызывает запуск обработки файла. Вторая строка с await немедленно оставляет метод и возвращается в другую задачу. При окончании обработки файла выполнение возвращается в точку выполнения, которая следует за await. Дополнительные сведения см. [в разделе поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Чтение текста  
 Следующий пример считывает текст из файла. Текст добавляется в буфер обмена, а затем, в данном случае, помещается в <xref:System.Text.StringBuilder>. В отличие от предыдущего примера await выдаёт в результате значение. Метод <xref:System.IO.Stream.ReadAsync%2A> возвращает <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, поэтому по завершении операции оценка await выдает значение `Int32` (`numRead`). Дополнительные сведения см. в разделе [асинхронные типы возвращаемых данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
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
  
## <a name="parallel-asynchronous-io"></a>Параллельный асинхронный ввод-вывод  
 В следующем примере показана параллельная обработка при записи 10 текстовых файлов. Для каждого файла метод <xref:System.IO.Stream.WriteAsync%2A> возвращает задачу, которая затем добавляется в список задач. Оператор `Await Task.WhenAll(tasks)` существует и возобновляется в методе, как только завершается обработка файла для всех задач.  
  
 Пример закрывает все экземпляры <xref:System.IO.FileStream> в блоке `Finally` после завершения всех задач. Если бы вместо этого каждый `FileStream` был бы создан в операторе `Imports`, то `FileStream` можно было бы удалить до завершения задачи.  
  
 Обратите внимание, что любое увеличение производительности зависит почти полностью от параллельной, а не асинхронной обработки. Преимущества асинхронности в том, что она не привязана к количеству потоков и не связана с потоком пользовательского интерфейса.  
  
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
  
 При использовании методов <xref:System.IO.Stream.WriteAsync%2A> и <xref:System.IO.Stream.ReadAsync%2A> можно указать <xref:System.Threading.CancellationToken>, который позволяет отменить операцию в середине потока. Дополнительные сведения см. в разделе [Точная настройка асинхронного приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) и [Отмена в управляемых потоках](../../../../standard/threading/cancellation-in-managed-threads.md).  
  
## <a name="see-also"></a>См. также

- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) (Типы возвращаемых значений Async (Visual Basic))
- [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) (Поток управления в асинхронных программах (Visual Basic))
