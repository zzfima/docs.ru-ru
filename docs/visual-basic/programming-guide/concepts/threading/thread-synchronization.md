---
title: "Поток синхронизации (Visual Basic) | Документы Microsoft"
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
ms.assetid: 04f485d1-8333-4510-9e72-c334e7427e7e
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
ms.openlocfilehash: ec8fa89c8921eadee428a90971d9ae4ce305a109
ms.lasthandoff: 03/13/2017

---
# <a name="thread-synchronization-visual-basic"></a>Синхронизация потоков (Visual Basic)
В следующих разделах описаны функции и классы, которые могут использоваться для синхронизации доступа к ресурсам в многопоточных приложениях.  
  
 Одним из преимуществ использования нескольких потоков в приложении является асинхронное выполнение каждого потока. Для приложений Windows, это позволяет длительные задачи выполняться в фоновом режиме, при этом окно приложения и элементы управления остаются активными. Для сервера приложений многопоточность обеспечивает возможность обработки каждого входящего запроса в отдельном потоке. В противном случае — каждый новый запрос не будет получить обслуживаться, пока предыдущий запрос был полностью удовлетворен.  
  
 Тем не менее должно координироваться асинхронность потоками означает, что доступ к ресурсам, таких как дескрипторы файлов, сетевые подключения и память. В противном случае — два или более потоков удалось получить доступ к тому же ресурсу одновременно, поток не будет учитывать действия другого. Повреждение данных непредсказуемым образом.  
  
 Для простых операций над числовыми типами данных синхронизация потоков может быть выполнено с членами <xref:System.Threading.Interlocked>класса.</xref:System.Threading.Interlocked> Для всех других данных типов и ресурсов не являющихся потокобезопасными, многопоточность может безопасно выполняться только с помощью конструкций в этом разделе.  
  
 Сведения о многопоточном программировании см. в разделе:  
  
-   [Основы управляемых потоков](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [Использование потоков и работа с потоками](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [Управляемые потоки советы и рекомендации](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-and-synclock-keywords"></a>Lock и SyncLock ключевые слова  
 Visual Basic `SyncLock` инструкция может использоваться для выполнения блока кода к завершению без прерывания работы других потоков. Это достигается путем получения блокировки взаимного исключения для заданного объекта в течение всего блока кода.  
  
 A `SyncLock` инструкция получает объект в качестве аргумента, за которыми блок кода, который должен выполняться одновременно только одним потоком. Например:  
  
```vb  
Public Class TestThreading  
    Dim lockThis As New Object  
  
    Public Sub Process()  
        SyncLock lockThis  
            ' Access thread-sensitive resources.  
        End SyncLock  
    End Sub  
End Class  
```  
  
 Аргумент, предоставляемый для `SyncLock` ключевое слово должно быть объекта на основании ссылочного типа и используется для определения области блокировки. В приведенном выше примере область блокировки ограничена данной функции, так как нет ссылки на объект `lockThis` существует вне функции. Если такая ссылка существовала, область блокировки включала бы для этого объекта. Строго говоря предоставленного объекта используется исключительно для уникальной идентификации ресурса общим для нескольких потоков, поэтому он может быть произвольный экземпляр класса. На практике этот объект обычно представляет ресурс для потока, в который требуется синхронизация. Например если объект контейнера будет использоваться несколькими потоками, контейнер может быть передан блокировки и блок синхронизированного кода после блокировки для доступа к контейнеру. При условии, что другие потоки блокируются для того же контейнера перед доступом к нему, а затем обеспечивается Безопасная синхронизация доступа к объекту.  
  
 Как правило, лучше всего избежать блокировки на `public` типа, или экземпляров объектов, которыми не управляет код вашего приложения. Например `lockThis` может быть проблематичным, если экземпляр доступны публично, поскольку код может блокировать объект также. Это может вызвать ситуаций взаимной блокировки, когда два или более потоков ждать выпуска того же объекта. Блокировка открытого типа данных, в отличие от объекта, может вызвать проблемы по той же причине. Блокировка строковых литералов наиболее опасна, поскольку строковые литералы являются *интернировано* общеязыковой среды выполнения (CLR). Это означает, что существует один экземпляр любого строкового литерала для всей программы, точно такой же объект будет представлять литерал во всех запущенных доменах приложения и во всех потоках. В результате блокировка, устанавливаемая на строку с тем же содержимым в любом месте в приложении, блокирует все экземпляры этой строки в приложении. Поэтому лучше блокировки не интернировано член закрытым или защищенным. Некоторые классы предоставляют члены, специально предназначенные для блокировки. <xref:System.Array>Тип, к примеру, предоставляет <xref:System.Array.SyncRoot%2A>.</xref:System.Array.SyncRoot%2A> </xref:System.Array> Во многих типах коллекций `SyncRoot` также члена.  
  
 Дополнительные сведения о `SyncLock` инструкции содержатся в следующих разделах:  
  
-   [Оператор SyncLock](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a>Мониторы  
 Как `SyncLock` ключевое слово, мониторы предотвратить блоки кода от одновременного выполнения нескольких потоков. <xref:System.Threading.Monitor.Enter%2A>Метод допускает только один поток для продолжения в следующие инструкции, другие потоки блокируются до выполняемый поток вызывает <xref:System.Threading.Monitor.Exit%2A>.</xref:System.Threading.Monitor.Exit%2A> </xref:System.Threading.Monitor.Enter%2A> Это аналогично использованию `SyncLock` ключевое слово. Пример:  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 Это эквивалентно:  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 С помощью `SyncLock` ключевое слово является желательным по сравнению с использованием <xref:System.Threading.Monitor>класса напрямую, и поскольку `SyncLock` компактнее и поскольку `SyncLock` гарантирует освобождение базового монитора, даже если защищенный код вызывает исключение.</xref:System.Threading.Monitor> Это осуществляется с помощью `Finally` ключевое слово, которое выполняет свой блок кода, независимо от того, является ли исключение.  
  
## <a name="synchronization-events-and-wait-handles"></a>События синхронизации и дескрипторы ожидания  
 Использование блокировки или монитора полезно для предотвращения одновременного выполнения чувствительных поток блоков кода, но эти структуры не позволяют одному потоку передавать события в другой. Это требует *события синхронизации*, которые являются объекты, обладающие одним из двух состояний сигнальное и без получения сигнала, который может использоваться для активации и приостановки потоков. Потоки можно приостанавливать их ожидать события синхронизации, заставляя и можно активировать, меняя сигнальное состояние события. Если поток попытается ожидать события, который уже получил сигнал, поток продолжает выполняться без задержек.  
  
 Существует два типа событий синхронизации: <xref:System.Threading.AutoResetEvent>и <xref:System.Threading.ManualResetEvent>.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent> Они отличаются только в том, что <xref:System.Threading.AutoResetEvent>изменения из сигнал до состояния автоматически каждый раз, он активирует потока.</xref:System.Threading.AutoResetEvent> И наоборот <xref:System.Threading.ManualResetEvent>позволяет любому числу потоков, чтобы активировать его сигнальное состояние и только вернется к несигнальное состояние при его <xref:System.Threading.EventWaitHandle.Reset%2A>вызывается метод.</xref:System.Threading.EventWaitHandle.Reset%2A> </xref:System.Threading.ManualResetEvent>  
  
 Можно сделать потоков для ожидания события путем вызова одного из методов ожидания, например <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, или <xref:System.Threading.WaitHandle.WaitAll%2A>.</xref:System.Threading.WaitHandle.WaitAll%2A> </xref:System.Threading.WaitHandle.WaitAny%2A> </xref:System.Threading.WaitHandle.WaitOne%2A> <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName>вызывающий поток ожидает сигнала одно событие <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>блокирует поток до сигнальное одно или несколько указанных событий, и <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>блокирует поток, пока все указанные события сигнальное.</xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> </xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName></xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> Событие оповещенным, когда его <xref:System.Threading.EventWaitHandle.Set%2A>вызывается метод.</xref:System.Threading.EventWaitHandle.Set%2A>  
  
 В следующем примере создается и запускается по потоку `Main` функции. Новый поток ожидает события с помощью <xref:System.Threading.WaitHandle.WaitOne%2A>метод.</xref:System.Threading.WaitHandle.WaitOne%2A> Выполнение потока приостанавливается до получения сигнала главным потоком, выполняющего `Main` функции. После получения сигнала возвращается дополнительный поток. В этом случае поскольку событие используется только для активации одного потока, либо <xref:System.Threading.AutoResetEvent>или <xref:System.Threading.ManualResetEvent>классы могут использоваться.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent>  
  
```vb  
Imports System.Threading  
  
Module Module1  
    Dim autoEvent As AutoResetEvent  
  
    Sub DoWork()  
        Console.WriteLine("   worker thread started, now waiting on event...")  
        autoEvent.WaitOne()  
        Console.WriteLine("   worker thread reactivated, now exiting...")  
    End Sub  
  
    Sub Main()  
        autoEvent = New AutoResetEvent(False)  
  
        Console.WriteLine("main thread starting worker thread...")  
        Dim t As New Thread(AddressOf DoWork)  
        t.Start()  
  
        Console.WriteLine("main thread sleeping for 1 second...")  
        Thread.Sleep(1000)  
  
        Console.WriteLine("main thread signaling worker thread...")  
        autoEvent.Set()  
    End Sub  
End Module  
```  
  
## <a name="mutex-object"></a>Объект взаимного исключения  
 Объект *мьютекс* похож на монитор; предотвращает одновременное выполнение блока кода, несколько потоков одновременно. На самом деле название «мьютекс» – сокращенная форма термина «взаимно исключают друг друга.» В отличие от мониторов тем не менее, мьютекс может использоваться для синхронизации потоков по процессам. Мьютекс представленного <xref:System.Threading.Mutex>класса.</xref:System.Threading.Mutex>  
  
 При использовании для синхронизации внутри процесса мьютекс называется *именованный мьютекс* так, как он будет использоваться в другом приложении, и поэтому его нельзя сделать общим посредством глобальной или статической переменной. Ему необходимо назначить имя, чтобы оба приложения могут обращаться к тому же объекту мьютекса.  
  
 Несмотря на то, что семафор может использоваться для синхронизации потоков внутри процесса, с помощью <xref:System.Threading.Monitor>обычно является более предпочтительной, поскольку мониторы были созданы специально для .NET Framework и более эффективно используют ресурсы.</xref:System.Threading.Monitor> Напротив <xref:System.Threading.Mutex>класс является оболочкой для конструкции Win32.</xref:System.Threading.Mutex> Хотя мощнее монитора, мьютекса требуются переходы взаимодействия, которые больше вычислительных ресурсов, чем <xref:System.Threading.Monitor>класс.</xref:System.Threading.Monitor> Пример использования мьютекса см. в разделе [мьютексы](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).  
  
## <a name="interlocked-class"></a>Interlocked-класс  
 Можно использовать методы <xref:System.Threading.Interlocked>класса для предотвращения проблем, возникающих при попытке нескольких потоков одновременно обновить или сравнить значения.</xref:System.Threading.Interlocked> Методы этого класса позволяют безопасно увеличивать, уменьшение, обмен и сравнения значений из любого потока.  
  
## <a name="readerwriter-locks"></a>Замок  
 В некоторых случаях может потребоваться заблокировать ресурс только в том случае, когда данные записываются и разрешить нескольким клиентам одновременно считывать данные, когда данные не обновляются. <xref:System.Threading.ReaderWriterLock>Класс обеспечивает монопольный доступ к ресурсу во время которого поток изменяет ресурс, но разрешает монопольного доступа чтения.</xref:System.Threading.ReaderWriterLock> Замок являются альтернативой монопольные блокировки, которые заставляют другие потоки ожидать, даже если их не нужно обновлять данные.  
  
## <a name="deadlocks"></a>Взаимоблокировок  
 Синхронизация потоков является необходимостью в многопоточных приложениях, но всегда существует опасность создания `deadlock`, где несколько потоков ожидают друг друга, и приложение к остановке. Взаимоблокировка аналогично ситуации, в которой автомобили останавливаются на stop четырехстороннюю и каждый пользователь ожидает другая для перехода. Как избежать взаимоблокировок важна. ключом является тщательное планирование. Взаимоблокировки часто можно предвидеть, диаграмму многопотокового приложения, прежде чем приступить к кодированию.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 <xref:System.Threading.WaitHandle.WaitOne%2A></xref:System.Threading.WaitHandle.WaitOne%2A>   
 <xref:System.Threading.WaitHandle.WaitAny%2A></xref:System.Threading.WaitHandle.WaitAny%2A>   
 <xref:System.Threading.WaitHandle.WaitAll%2A></xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>   
 <xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>   
 <xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>   
 <xref:System.Threading.Monitor></xref:System.Threading.Monitor>   
 <xref:System.Threading.Mutex></xref:System.Threading.Mutex>   
 <xref:System.Threading.AutoResetEvent></xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Interlocked></xref:System.Threading.Interlocked>   
 <xref:System.Threading.WaitHandle></xref:System.Threading.WaitHandle>   
 <xref:System.Threading.EventWaitHandle></xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.EventWaitHandle.Set%2A></xref:System.Threading.EventWaitHandle.Set%2A>   
 [Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [Оператор SyncLock](../../../../visual-basic/language-reference/statements/synclock-statement.md)   
 [Мьютексы](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)   
 @System.Threading.Monitor   
 [Блокируемые операции](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b)   
 [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18)   
 [Синхронизация данных для многопоточности](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)
