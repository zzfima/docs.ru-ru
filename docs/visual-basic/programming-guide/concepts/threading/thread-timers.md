---
title: "Таймеры (Visual Basic) потоков | Документы Microsoft"
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
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
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
ms.openlocfilehash: 9ea657482d4e8e1465d9bc6ae3f94915badee512
ms.lasthandoff: 03/13/2017

---
# <a name="thread-timers-visual-basic"></a>Таймеры потоков (Visual Basic)
<xref:System.Threading.Timer?displayProperty=fullName>Класс полезен для периодического запуска задач в отдельном потоке.</xref:System.Threading.Timer?displayProperty=fullName> Например можно использовать таймер потока для проверки состояния и целостности базы данных или резервное копирование важных файлов.  
  
## <a name="thread-timer-example"></a>Пример таймера потока  
 В следующем примере задача запускается каждые две секунды и использует флаг для инициирования <xref:System.IDisposable.Dispose%2A>метод, который останавливает таймер.</xref:System.IDisposable.Dispose%2A> В этом примере состояние отображается в окне вывода.  
  
```vb  
Private Class StateObjClass  
    ' Used to hold parameters for calls to TimerTask.  
    Public SomeValue As Integer  
    Public TimerReference As System.Threading.Timer  
    Public TimerCanceled As Boolean  
End Class  
  
Public Sub RunTimer()  
    Dim StateObj As New StateObjClass  
    StateObj.TimerCanceled = False  
    StateObj.SomeValue = 1  
    Dim TimerDelegate As New System.Threading.TimerCallback(AddressOf TimerTask)  
    ' Create a timer that calls a procedure every 2 seconds.  
    ' Note: There is no Start method; the timer starts running as soon as   
    ' the instance is created.  
    Dim TimerItem As New System.Threading.Timer(TimerDelegate, StateObj,  
                                                2000, 2000)  
    ' Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem  
  
    ' Run for ten loops.  
    While StateObj.SomeValue < 10  
        ' Wait one second.  
        System.Threading.Thread.Sleep(1000)  
    End While  
  
    ' Request Dispose of the timer object.  
    StateObj.TimerCanceled = True  
End Sub  
  
Private Sub TimerTask(ByVal StateObj As Object)  
    Dim State As StateObjClass = CType(StateObj, StateObjClass)  
    ' Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(State.SomeValue)  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " & Now.ToString)  
    If State.TimerCanceled Then  
        ' Dispose Requested.  
        State.TimerReference.Dispose()  
        System.Diagnostics.Debug.WriteLine("Done  " & Now)  
    End If  
End Sub  
```  
  
 Таймеры потоков особенно полезны при <xref:System.Windows.Forms.Timer?displayProperty=fullName>объект недоступен, например при разработке консольных приложений.</xref:System.Windows.Forms.Timer?displayProperty=fullName>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading></xref:System.Threading>   
 [Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
