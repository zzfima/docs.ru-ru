---
title: "Параметры и возвращаемые значения для многопоточных процедур (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 071e0aa916e4b3464c7c0cbff6596cabc6b67906
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>Параметры и возвращаемые значения для многопоточных процедур (Visual Basic)
Предоставлять и возвращать значения в многопоточном приложении сложно, поскольку в конструктор для класса потока должна передаваться ссылка на процедуру, которая принимает аргумент и не возвращает никакое значение. В следующих разделах показано несколько простых способов предоставления параметров и возвращения значений из процедур в отдельных потоках.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Предоставление параметров для многопоточных процедур  
 Лучший способ передать параметры для вызова многопоточного метода — это вложить нужный метод в класс и определить для этого класса поля, которые будут служить параметрами для нового потока. Преимущество этого подхода состоит в том, что новый экземпляр класса с его собственными параметрами можно создавать каждый раз, когда вам нужно запустить новый поток. Допустим, например, что у вас есть функция, вычисляющая площадь треугольника, как в следующем коде:  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 Напишем класс, в который вложена функция `CalcArea` и который создает поля для хранения входных параметров:  
  
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
  
 Чтобы использовать `AreaClass`, можно создать объект `AreaClass` и задать свойства `Base` и `Height`, как показано в следующем коде:  
  
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
  
 Обратите внимание на то, что процедура `TestArea` не проверяет значение поля `Area` после вызова метода `CalcArea`. Поскольку `CalcArea` выполняется в отдельном потоке, поле `Area` может оказаться не заданным, если проверять его сразу после вызова `Thread.Start`. В следующем разделе рассматривается более удобный способ получения возвращаемых значений из многопоточных процедур.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Получение возвращаемых значений из многопоточных процедур  
 Получение возвращаемых значений из процедур, выполняемых в отдельных потоках, осложняется тем, что процедуры не могут быть функциями, а аргументы `ByRef` использовать нельзя. Самый простой способ получить возвращаемые значения — это применить компонент <xref:System.ComponentModel.BackgroundWorker>, управляющий потоками и создающий событие по завершении задачи, а затем обработать результаты с помощью обработчика событий.  
  
 В следующем примере значение возвращается в результате создания события из процедуры, выполняемой в отдельном потоке:  
  
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
  
 Параметры и возвращаемые значения можно передавать в поток пула потоков с помощью необязательной переменной объекта состояния `ByVal` метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>. Потоки таймера потоков также поддерживают объект состояния в этом контексте. Сведения о группировке потоков и таймеры потоков см. в разделе [пул потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[пул потоков](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) и [таймеры потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [Группировка потоков в пул (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [Синхронизация потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Многопоточность в компонентах](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
