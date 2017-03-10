---
title: "Оператор Await (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Await"
helpviewer_keywords: 
  - "Await [Visual Basic]"
  - "Await - оператор [Visual Basic]"
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Оператор Await (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Примените оператор `Await` к операнду в асинхронных метода или лямбда\-выражения для приостановки выполнения метода до тех пор, пока ожидается задача не будет завершено.  Задача представляет выполняющуюся работу.  
  
 Метод `Await`, в котором используется должен иметь модификатор [Async](../../../visual-basic/language-reference/modifiers/async.md).  Такой метод, определенный с помощью модификатора `Async` и обычно содержащий одно или несколько выражений `Await`, называется *асинхронным методом или методом async*.  
  
> [!NOTE]
>  Ключевые слова `Async` и `Await` были введены в Visual Studio 2012.  Введение в асинхронное программирование см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Как правило, задача, на которую применяется оператор `Await` возвращаемое значение из вызова метода, реализующего [Асинхронная модель на основе задач](http://go.microsoft.com/fwlink/?LinkId=204847), т е <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.  
  
 В следующем коде <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>, метод <xref:System.Net.Http.HttpClient> возвращает значение `getContentsTask`, `Task(Of Byte())`.  Для объявления является " обещанием " создать фактический массив байтов при завершении операции.  Оператор `Await` применяется к `getContentsTask`, чтобы приостановить выполнение в `SumPageSizesAsync` до тех пор, пока `getContentsTask` не будет завершен.  Тем временем, управление возвращается к вызывающему объекту `SumPageSizesAsync`.  После завершения метода `getContentsTask`, выражение `Await` оценивается как массив байтов.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Полный пример см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Можно загрузить пример со страницы [Примеры кода разработчика](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) на веб\-сайте Майкрософт.  Пример находится в проекте AsyncWalkthrough\_HttpClient.  
  
 Если атрибут `Await` применяется к результату вызова метода, который возвращает `Task(Of TResult)` тип выражения `Await` TResult.  Если атрибут `Await` применяется к результату вызова метода, который возвращает `Task`, выражение `Await` не возвращает значение.  В следующем примере показана разница.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Выражение или выписка `Await` не будет блокировать поток, в котором она выполняется.  Вместо этого она указывает компилятору зарегистрироваться остальную часть метода токена, после выражения `Await` как продолжение, предназначенную для задачи.  Управление затем возвращается вызывающему объекту асинхронного метода.  Если задача завершается, она вызывает его продолжение, а выполнение метода токена продолжится, где было остановлено.  
  
 Выражение `Await` может произойти только в теле немедленно внешнего метода или лямбда\-выражения, которое помечено модификатором `Async`.  Термин *ожидает* служит ключевое слово только в этом контексте.  В другом месте, оно интерпретируется как идентификатор.  В методе или лямбда\-выражения токена, выражение `Await` не может содержаться в выражении запроса, в блоке `catch` или `finally` выписки [Try… Catch… finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md), в выражении элемента управления цикла переменной цикла `For` или `For Each`, или в теле выписки [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
## Исключения  
 Большинство асинхронных методов возвращают значение <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.  Свойства возвращаемой задачи содержат сведения о ее состоянии и истории, такие как завершена ли задача, привел ли асинхронный метод к исключению или был отменен, а также каков конечный результат.  Оператор `Await` получает доступ к этим свойствам.  
  
 Если выполняется await для возвращающего метода async, который вызывает исключение, оператор `Await` повторно создает исключение.  
  
 Если предполагается, что задачи и возвратя метода, токена, отменяется, повторно создает оператора `Await`<xref:System.OperationCanceledException>.  
  
 Одна задача в состоянии ошибки может отражать несколько исключений.  Например, задача может быть результатом вызова <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  Когда ожидаете такой задачи, операция await повторно создает только одно из исключений.  Однако невозможно предугадать, какое из исключений повторно создается.  
  
 Примеры обработки ошибок в асинхронных методах см. [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Пример  
 В следующем примере Windows Forms показано использование токена `Await` в асинхронном методе `WaitAsynchronouslyAsync`.  Сравните поведение этого метода с поведением `WaitSynchronously`.  Без оператора `Await`, даже если `WaitSynchronously` выполняется одновременно использовать модификатор `Async` в определении и вызове <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> в своем теле.  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## См. также  
 [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Async](../../../visual-basic/language-reference/modifiers/async.md)