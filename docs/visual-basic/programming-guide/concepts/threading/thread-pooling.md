---
title: "Группировка потоков в пул (Visual Basic) | Документы Microsoft"
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
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
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
ms.openlocfilehash: 6037d7ea17e260d44bae571aa25d413996f5a123
ms.lasthandoff: 03/13/2017

---
# <a name="thread-pooling-visual-basic"></a>Группировка потоков в пул (Visual Basic)
Объект *пул потоков* — это коллекция потоков, которые могут использоваться для выполнения нескольких задач в фоновом режиме. (См. [потоки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) сведения общего характера.) Это оставляет главный поток для асинхронного выполнения других задач.  
  
 Пулы потоков часто используются в серверных приложениях. Каждый входящий запрос назначается потоку из пула потоков, таким образом, запрос может обрабатываться асинхронно, без прерывания основного потока и задержки обработки последующих запросов.  
  
 Когда поток в пуле завершает выполнение задачи, возвращается в очередь ожидающих потоков, где он может быть повторно использован. Повторное использование позволяет приложениям избежать затрат на создание новых потоков для каждой задачи.  
  
 Обычно пулы имеют максимальное количество потоков. Если все потоки заняты, дополнительные задачи помещаются в очередь, пока они могут обслуживаться как потоки становятся доступными.  
  
 Можно реализовать собственный пул потоков, но проще использовать пул потоков, предоставляемых .NET Framework с помощью <xref:System.Threading.ThreadPool>класса.</xref:System.Threading.ThreadPool>  
  
 При группировке потоков вызвать <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>метод с помощью делегата для процедуры требуется запустить, и Visual Basic создает поток и запускает указанную процедуру.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>  
  
## <a name="thread-pooling-example"></a>Пример группировки потоков  
 В следующем примере показано, как можно использовать группировку потоков для запуска нескольких задач.  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 Одно из преимуществ группировки потоков — можно передать аргументы в виде объекта процедуры. Если вызываемой процедуре требуется нескольких аргументов, можно привести структуру или экземпляр класса в `Object` тип данных.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Параметры пула потоков и возвращаемые значения  
 Получение возвращаемых значений от поток из пула потоков не является простой задачей. Стандартный способ получения возвращаемого значения при вызове функции не допускается, поскольку `Sub` процедуры — это единственный тип процедуры, которые могут быть поставлены в очередь в пул потоков. Один из способов можно указать параметры и возврата значений — это заключение параметров, возвращаемых значений и методов в оболочку класса, как описано в [параметры и возвращаемые значения для многопоточных процедур (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).  
  
 Более простым способом передачи параметров и возвращаемых значений является использование необязательной `ByVal` объекта <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>метод.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> Если эта переменная используется для передачи ссылки на экземпляр класса, члены экземпляра можно изменить потоком пула потоков и используется в качестве возвращаемого значения.  
  
 Поначалу может оказаться очевидно, что можно изменить объект, на который ссылается переменная, который передается по значению. Это можно сделать, поскольку только ссылка на объект передается по значению. При изменении членов объекта, указанного в ссылке, изменения применяются к реальному экземпляру класса.  
  
 Структуры не может использоваться для возврата значения, входящие в состав объектов. Поскольку структуры являются типами значений, изменения, вносимые асинхронным процессом, не изменяйте элементы исходной структуры. Используйте структуры для предоставления параметров, когда возвращаемые значения не требуется.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool>   
 [Практическое руководство: использование пула потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)   
 [Работа с потоками (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [Синхронизация потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
