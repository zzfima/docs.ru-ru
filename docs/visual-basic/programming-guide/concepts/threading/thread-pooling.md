---
title: Группировка потоков в пул (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
ms.openlocfilehash: 445c1c70cc1371ef918f32046e0c30ae2a473da2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="thread-pooling-visual-basic"></a>Группировка потоков в пул (Visual Basic)
*Пул потоков* — это коллекция потоков, которые могут использоваться для выполнения нескольких задач в фоновом режиме. (См. [потоки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) сведения общего характера.) Это позволяет разгрузить главный поток для асинхронного выполнения других задач.  
  
 Пулы потоков часто используются в серверных приложениях. Каждый входящий запрос назначается потоку из пула, таким образом запрос может обрабатываться асинхронно без задействования главного потока и задержки обработки последующих запросов.  
  
 Когда поток в пуле завершает выполнение задачи, он возвращается в очередь ожидания, в которой может быть повторно использован. Повторное использование позволяет приложениям избежать дополнительных затрат на создание новых потоков для каждой задачи.  
  
 Обычно пулы имеют максимальное количество потоков. Если все потоки заняты, дополнительные задачи помещаются в очередь, где находятся до тех пор, пока не появятся свободные потоки.  
  
 Можно реализовать собственный пул потоков, но гораздо проще использовать пул потоков, предоставляемых .NET Framework через класс <xref:System.Threading.ThreadPool>.  
  
 При группировке потоков вызова <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> метод с помощью делегата для процедуры требуется запустить, и Visual Basic создает поток и запускает указанную процедуру.  
  
## <a name="thread-pooling-example"></a>Пример группировки потоков в пул  
 В следующем примере показано, как можно использовать группировку потоков в пул для запуска нескольких задач.  
  
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
  
 Одно из преимуществ группировки потоков заключается в возможности передачи аргументов в процедуру задачи в виде объекта состояния. Если вызываемой процедуре требуется несколько аргументов, можно привести структуру или экземпляр некоторого класса к типу данных `Object`.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Параметры и возвращаемые значения пула потоков  
 Получение возвращаемого значения из пула потоков является не такой простой задачей. Стандартный способ получения возвращаемого значения при вызове функции использовать нельзя, поскольку помещать в очередь на выполнение в пуле потоков можно только процедуры `Sub`. Одним из способов вы можете передачи параметров и возвращаемых значений — это заключение параметров, возвращаемых значений и методов в оболочке класса, как описано в [параметры и возвращаемые значения для многопоточных процедур (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).  
  
 Параметры и возвращаемые значения проще предоставить с помощью необязательной переменной объекта состояния `ByVal` метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>. Если эта переменная используется для передачи ссылки на экземпляр класса, члены экземпляра могут быть изменены потоком, входящим в пул потоков, и использоваться в качестве возвращаемых значений.  
  
 На первый взгляд, возможность изменения объекта, на который ссылается переданная по значению переменная, не является очевидной. На самом деле это возможно, потому что по значению передается только ссылка на объект. При изменении членов объекта, указанного в ссылке, изменения применяются к реальному экземпляру класса.  
  
 Структуры, входящие в состав объектов состояния, нельзя использовать для получения возвращаемых значений. Поскольку структуры являются типами, передаваемыми по значению, изменения, вносимые асинхронным процессом, не влияют на члены исходной структуры. Структуры следует использовать для передачи параметров, когда не требуется получать возвращаемые значения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Практическое руководство. Использование пула потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) (Работа с потоками (Visual Basic))  
 [Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Синхронизация потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
