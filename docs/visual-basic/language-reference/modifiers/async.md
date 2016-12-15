---
title: "Async (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Async"
helpviewer_keywords: 
  - "Async [Visual Basic]"
  - "Async -ключевое слово [Visual Basic]"
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
caps.latest.revision: 37
caps.handback.revision: 37
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Async (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модификатор `Async` указывает, что метод [лямбда\-выражение](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md), или изменяет асинхронными.  Эти методы называются *Методы async*.  
  
 Асинхронный метод предоставляет удобный способ для выполнения работы, потенциально способной занять длительное время, без блокировки потока вызывающего объекта.  Вызывающая сторона метода токена может возобновить свою работу, не дожидаясь метод токена для выполнения.  
  
> [!NOTE]
>  Ключевые слова `Async` и `Await` были введены в Visual Studio 2012.  Введение в асинхронное программирование см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 В следующем примере показана структура метода токена.  В соответствии с соглашением имена методов токена заканчиваются словом «Async».  
  
```vb  
  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 Обычно метод измененный ключевым словом `Async` содержит по крайней мере одно выражение или оператора [Рекомендуется](../../../visual-basic/language-reference/modifiers/async.md).  Метод выполняется одновременно до тех пор, пока не будет достигнут первое значение `Await`, в котором он точка приостанавливается до тех пор, пока ожидается задача не будет завершено.  В то же время, элемент управления возвращается вызывающему объекту метода.  Если метод не содержит выражение или оператора `Await`, не приостановлен и не выполняет метод как синхронного метода.  Компилятор выводит предупреждения обо всех асинхронных методах, не содержащих ключевого слова `Await`, поскольку такая ситуация может указывать на ошибку.  Дополнительные сведения см. в разделе [ошибка компилятора](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).  
  
 Ключевое слово `Async` безоговорочное ключевое слово.  Ключевое слово, когда изменяется метод или лямбда\-выражение.  Во всех других контекстах, оно интерпретируется как идентификатор.  
  
## Типы возвращаемых значений  
 Метод токена или процедуры [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md), или процедуры [Функция](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md), имеет возвращаемый тип <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.  Метод не может объявить все параметры [ByRef](../../../visual-basic/language-reference/modifiers/byref.md).  
  
 Указать `Task(Of TResult)` для возвращаемого типа метода токена, если выписка [Return](../../../visual-basic/language-reference/statements/return-statement.md) метода имеет операнд типа TResult.  Класс `Task` используется при отсутствии информативное значение не возвращается, когда метод завершения.  То есть вызов метода `Task` возвращает `Task`, но при завершении любая выписка `Await` ожидает, `Task` не предоставляет значение.  
  
 Подпрограммы Async используются в основном для определения обработчики событий, процедура `Sub` не требуется.  Вызывающий объект подпрограммы токена не может ожидать его и не может перехватывать исключения, метод создает исключение.  
  
 Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Пример  
 В следующих примерах демонстрируется обработчик событий токена, лямбда\-выражение токена и метод токена.  Полный пример использования этих элементов см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Можно загрузить код пошагового руководства из [Примеры кода разработчика](http://go.microsoft.com/fwlink/?LinkId=255191).  
  
```vb  
  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("http://msdn.com")  
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
    ' The downloaded resource ends up in the variable named content.  
    Dim content = New MemoryStream()  
  
    ' Initialize an HttpWebRequest for the current URL.  
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
    ' Send the request to the Internet resource and wait for  
    ' the response.  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
        ' Get the data stream that is associated with the specified URL.  
        Using responseStream As Stream = response.GetResponseStream()  
            ' Read the bytes in responseStream and copy them to content.    
            ' CopyToAsync returns a Task, not a Task<T>.  
            Await responseStream.CopyToAsync(content)  
        End Using  
    End Using  
  
    ' Return the result as a byte array.  
    Return content.ToArray()  
End Function  
  
```  
  
## См. также  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [Оператор Await](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)