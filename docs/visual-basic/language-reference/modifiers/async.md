---
title: Async (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: ad6d671a45cee7d534347d23963bb5035ecc8dac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834595"
---
# <a name="async-visual-basic"></a>Async (Visual Basic)
`Async` Модификатор указывает, что метод или [лямбда-выражение](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) она изменяет является асинхронным. Такие методы называются *асинхронные методы*.  
  
 Асинхронный метод представляет собой удобный способ для выполнения работы, которая может занять длительное время, без блокировки потока вызывающего объекта. Вызывающий объект асинхронного метода может возобновить свою работу, не дожидаясь завершения асинхронного метода.  
  
> [!NOTE]
>  Ключевые слова `Async` и `Await` появились в Visual Studio 2012. Введение в асинхронное программирование, см. в разделе [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 В следующем примере показана структура асинхронного метода. По соглашению имена асинхронных методов заканчиваться на «Async».  
  
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
  
 Как правило, метод модификаторами `Async` ключевое слово содержит по крайней мере [Await](../../../visual-basic/language-reference/modifiers/async.md) выражения или оператора. Метод выполняется синхронно, пока не будет достигнут первый `Await`, после чего он приостанавливает до завершения выполнения ожидающей задачи. В то же время управление возвращается вызывающему объекту метода. Если метод не содержит `Await` выражения или оператора, метод не приостановлено и выполняется как синхронный метод. Компилятор выводит предупреждения обо всех асинхронных методах, которые не содержат `Await` поскольку такая ситуация может указывать на ошибку. Дополнительные сведения см. в разделе [Ошибка компилятора](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).  
  
 `Async` Ключевое слово — это незарезервированных ключевое слово. Это ключевое слово, если она изменяет, метод или лямбда-выражения. В других контекстах он интерпретируется как идентификатор.  
  
## <a name="return-types"></a>Типы возвращаемых значений  
 Асинхронный метод является либо [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) процедуры, или [функция](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) процедуру, которая имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Метод не может объявлять [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.  
  
 Указать `Task(Of TResult)` для возвращаемого типа асинхронного метода Если [возвращают](../../../visual-basic/language-reference/statements/return-statement.md) инструкция метода содержит операнд типа TResult. Класс `Task` используется при отсутствии содержательного значения, возвращаемого методом при его завершении. То есть вызов метода возвращает `Task`, однако когда `Task` завершения любой `Await` инструкцию, которая ожидает `Task` не производят результирующее значение.  
  
 Подпрограммы Async используются преимущественно для определения обработчиков событий где `Sub` процедура. Объект, вызывающий подпрограмму async не может ожидать его и не может перехватывать исключения, создаваемые методом исключения.  
  
 Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Пример  
 В следующих примерах асинхронный обработчик событий, асинхронное лямбда-выражение и асинхронного метода. Полный пример, в котором используются эти элементы, см. в разделе [Пошаговое руководство: Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Код пошагового руководства можно скачать в разделе [Примеры кода от разработчиков](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [Оператор Await](../../../visual-basic/language-reference/operators/await-operator.md)
- [Асинхронное программирование с использованием ключевых слов Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md)
- [Пошаговое руководство: Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
