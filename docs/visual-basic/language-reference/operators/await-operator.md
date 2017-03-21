---
title: "Оператор await (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b50b9c7283ddd4d3f8484854bdffff3d76181c9f
ms.lasthandoff: 03/13/2017

---
# <a name="await-operator-visual-basic"></a>Оператор Await (Visual Basic)
Можно применить `Await` оператор операндом в асинхронный метод или лямбда-выражения для приостановки выполнения метода завершения ожидаемая задача. Задача представляет выполняющуюся работу.  
  
 Метод, в котором `Await` используется должен иметь [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор. Такой метод, определенный с помощью `Async` модификатор и обычно содержит один или несколько `Await` выражения, называется *асинхронный метод*.  
  
> [!NOTE]
>  Ключевые слова `Async` и `Await` появились в Visual Studio 2012. Введение в асинхронном программировании см. в разделе [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Как правило, задача, к которому применяется `Await` оператор является возвращаемым значением из вызова метода, реализующего [асинхронная модель на основе задач](http://go.microsoft.com/fwlink/?LinkId=204847), то есть, <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 В следующем коде <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>возвращает `getContentsTask`, `Task(Of Byte())`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> </xref:System.Net.Http.HttpClient> Задача является обещание создать фактическое байтового массива, при завершении операции. Оператор `Await` применяется к `getContentsTask` для приостановки выполнения в `SumPageSizesAsync` до завершения `getContentsTask`. В то же время управление возвращается вызывающему объекту `SumPageSizesAsync`. Когда `getContentsTask` завершается, результатом выражения `Await` является массив байтов.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Полный пример см. в разделе [Пошаговое руководство: доступ к Интернету с помощью Async и Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Можно загрузить образец из [примеров кода для разработчиков](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) на веб-сайте Майкрософт. Этот пример представлен в проекте AsyncWalkthrough_HttpClient.  
  
 Если `Await` применяется к результату вызова метода, который возвращает `Task(Of TResult)`, тип `Await` выражение является TResult. Если `Await` применяется к результату вызова метода, который возвращает `Task`, `Await` выражение не возвращает значение. В следующем примере демонстрируется это различие.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 `Await` Выражения или оператора не блокирует поток, на котором он выполняется. Вместо этого он предписывает компилятору входа остальную часть асинхронного метода после `Await` выражение как продолжение на ожидаемая задача. Затем управление возвращается в объект, вызывающий асинхронный метод. Когда задача завершается, она вызывает свое продолжение и выполнение асинхронного метода возобновляется с того момента, где оно было остановлено.  
  
 `Await` Выражение может возникать только в теле немедленно включающего метода или лямбда-выражение, помеченного атрибутом `Async` модификатор. Термин *Await* служит ключевое слово только в этом контексте. В другом месте он интерпретируется как идентификатор. В асинхронный метод или лямбда-выражения `Await` выражение не может появляться в выражении запроса в `catch` или `finally` блока [Try... CATCH... Наконец](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) инструкции в цикле управления переменной выражении `For` или `For Each` цикла, или в теле [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) инструкции.  
  
## <a name="exceptions"></a>Исключения  
 Большинство асинхронные методы возвращают <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> Свойства возвращаемой задачи содержат сведения о ее состоянии и журнале, например завершена ли задача, вызвал ли асинхронный метод исключение или был отменен и каков окончательный результат. Оператор `Await` обращается к этим свойствам.  
  
 Если вы ожидаете возвращающий задачу асинхронный метод, который вызывает исключение, то оператор `Await` повторно создает это исключение.  
  
 Если ожидать возвращения задач асинхронного метода, отменяется, `Await` <xref:System.OperationCanceledException>.</xref:System.OperationCanceledException> повторно создает оператор  
  
 Одна задача, которая находится в состоянии сбоя, может отражать несколько исключений.  Например задача может быть результатом вызова <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> Если вы ожидаете такую задачу, операция await повторно вызывает только одно из исключений. Однако невозможно предсказать, какие исключения создаются повторно.  
  
 Примеры для обработки ошибок в асинхронные методы в разделе [Try... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере Windows Forms демонстрируется использование `Await` в асинхронном методе `WaitAsynchronouslyAsync`. Сравните поведение этого метода с поведением `WaitSynchronously`. Без `Await` оператор, `WaitSynchronously` выполняется синхронно, несмотря на использование `Async` модификатор в его определение и вызов <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>в его теле.</xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>  
  
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
  
## <a name="see-also"></a>См. также  
 [Асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Async](../../../visual-basic/language-reference/modifiers/async.md)
