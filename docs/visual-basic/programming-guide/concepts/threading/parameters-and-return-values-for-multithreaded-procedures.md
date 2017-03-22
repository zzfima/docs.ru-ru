---
title: "Параметры и возвращаемые значения для многопоточных процедур (Visual Basic) | Документы Microsoft"
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
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d5d8adde531d31aa6bf353f53bd4cfecc084f515
ms.lasthandoff: 03/13/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>Параметры и возвращаемые значения для многопоточных процедур (Visual Basic)
Предоставление и возврат значений в многопоточных приложениях является сложной, так как конструктор для класса поток должен быть передан ссылку на процедуру, которая не принимает аргументов и не возвращает значений. В следующих разделах показаны некоторые простые способы передачи параметров и возвращаемых значений из процедур в отдельных потоках.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Предоставление параметров для многопоточных процедур  
 Лучший способ передачи параметров при вызове многопотокового метода является заключение нужного метода в класс и определение полей для этого класса, который будет использоваться в качестве параметров для нового потока. Преимуществом этого подхода является то, что новый экземпляр класса, позволяет создавать со своими параметрами нужно запустить новый поток каждый раз. Например рассмотрим функцию, вычисляющую площадь треугольника, как показано в следующем коде:  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 Можно написать класс-оболочку `CalcArea` и имеет поля для хранения входных параметров, как показано ниже:  
  
```vb  
Class AreaClass  
    Public Base As Double  
    Public Height As Double  
    Public Area As Double  
    Sub CalcArea()  
        Area = 0.5 * Base * Height  
        MessageBox.Show("The area is: " & Area.ToString)  
    End Sub  
End Class  
```  
  
 Для использования `AreaClass`, можно создать `AreaClass` и установить `Base` и `Height` свойства, как показано в следующем коде:  
  
```vb  
Protected Sub TestArea()  
    Dim AreaObject As New AreaClass  
    Dim Thread As New System.Threading.Thread(  
                        AddressOf AreaObject.CalcArea)  
    AreaObject.Base = 30  
    AreaObject.Height = 40  
    Thread.Start()  
End Sub  
```  
  
 Обратите внимание, что `TestArea` не проверяет значение `Area` после вызова `CalcArea` метод. Поскольку `CalcArea` выполняется в отдельном потоке, `Area` поле не обязательно быть задано, если проверить его сразу после вызова `Thread.Start`. В следующем разделе описываются более эффективный способ возвращения значений из многопоточных процедур.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Получение возвращаемых значений от многопоточных процедур  
 Получение возвращаемых значений от процедур, выполняемых в отдельных потоках, осложняется тем, что процедуры не могут быть функциями и нельзя использовать `ByRef` аргументы. Самый простой способ возвращения значений является использование <xref:System.ComponentModel.BackgroundWorker>компонент для управления потоками и вызова события при завершении задачи и обработки результатов с помощью обработчика событий.</xref:System.ComponentModel.BackgroundWorker>  
  
 В следующем примере возвращается значение, при возникновении события от процедуры, выполняющейся в отдельном потоке:  
  
```vb  
Private Class AreaClass2  
    Public Base As Double  
    Public Height As Double  
    Function CalcArea() As Double  
        ' Calculate the area of a triangle.  
        Return 0.5 * Base * Height  
    End Function  
End Class  
  
Private WithEvents BackgroundWorker1 As New System.ComponentModel.BackgroundWorker  
  
Private Sub TestArea2()  
    Dim AreaObject2 As New AreaClass2  
    AreaObject2.Base = 30  
    AreaObject2.Height = 40  
  
    ' Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2)  
End Sub  
  
' This method runs on the background thread when it starts.  
Private Sub BackgroundWorker1_DoWork(  
    ByVal sender As Object,   
    ByVal e As System.ComponentModel.DoWorkEventArgs  
    ) Handles BackgroundWorker1.DoWork  
  
    Dim AreaObject2 As AreaClass2 = CType(e.Argument, AreaClass2)  
    ' Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea()  
End Sub  
  
' This method runs on the main thread when the background thread finishes.  
Private Sub BackgroundWorker1_RunWorkerCompleted(  
    ByVal sender As Object,  
    ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
    ) Handles BackgroundWorker1.RunWorkerCompleted  
  
    ' Access the result through the Result property.  
    Dim Area As Double = CDbl(e.Result)  
    MessageBox.Show("The area is: " & Area.ToString)  
End Sub  
```  
  
 Можно указать параметры и возвращаемые значения для потоков из пула потоков с помощью необязательного `ByVal` объект состояния переменной <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>метод.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> Таймер потока потоков также поддерживает объект состояния для этой цели. Сведения о группировке потоков и таймеры потоков в разделе [пул потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[пул потоков](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) и [таймеры потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Многопоточность с помощью компонента BackgroundWorker (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)   
 [Группировка потоков в пул (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)   
 [Синхронизация потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)   
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Многопоточность в компонентах](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
