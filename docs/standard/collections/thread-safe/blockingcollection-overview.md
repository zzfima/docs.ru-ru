---
title: "Общие сведения о коллекции BlockingCollection| Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BlockingCollection, overview
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f920d8327a536184c71ad2feb68624cee6bd8ffa
ms.lasthandoff: 04/18/2017

---
# <a name="blockingcollection-overview"></a>Общие сведения о коллекции BlockingCollection
<xref:System.Collections.Concurrent.BlockingCollection%601> — это потокобезопасный класс коллекции, обеспечивающий следующие возможности:  
  
-   реализует шаблон "производитель-получатель";  
  
-   поддерживает параллельное добавление и извлечение элементов из нескольких потоков;  
  
-   допускает указание максимальной емкости;  
  
-   поддерживает операции вставки и удаления, блокирующиеся при опустошении или заполнении коллекции;  
  
-   поддерживает условные операции вставки и удалении, не блокирующиеся или блокирующиеся лишь на определенное время;  
  
-   инкапсулирует все типы коллекций, реализующие интерфейс <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>;  
  
-   поддерживает отмену с помощью токенов отмены;  
  
-   поддерживает два вида перечисления с помощью оператора `foreach` (`For Each` в Visual Basic):  
  
    1.  перечисление "только для чтения";  
  
    2.  перечисление, при котором элементы по мере перечисления удаляются.  
  
## <a name="bounding-and-blocking-support"></a>Поддержка границ и блокировки  
 <xref:System.Collections.Concurrent.BlockingCollection%601> поддерживает границы и блокировку. Поддержка границ означает возможность задать максимальную емкость коллекции. Границы важны в ряде сценариев, поскольку они позволяют контролировать максимальный размер коллекции в памяти, предотвращая ситуации, в которых потоки-создатели слишком сильно обгоняют потоки-потребители.  
  
 Элементы коллекции могут параллельно добавляться из нескольких задач или потоков. Если коллекция достигает максимальной емкости, то потоки-создатели перейдут в состояние блокировки, пока не будет удален хотя бы один элемент. Элементы коллекции могут параллельно удаляться несколькими потребителями. Если коллекция становится пустой, то потоки-потребители перейдут в состояние блокировки, пока поток-создатель не добавит хотя бы один элемент. Поток-создатель может вызвать <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>, чтобы обозначить, что другие элементы не будут добавлены. Потребители могут отслеживать свойство <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A>, чтобы узнать, когда коллекция пуста и другие элементы не будут добавлены. В следующем примере демонстрируется простая коллекция BlockingCollection с максимальной емкостью в 100 элементов. Задача-создатель добавляет элементы в коллекцию, пока некоторое внешнее условие истинно, и затем вызывает <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>. Задача-потребитель извлекает элементы, пока свойство <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> истинно.  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 Полный пример см. в разделе [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## <a name="timed-blocking-operations"></a>Операции с временной блокировкой  
 В операциях с временной блокировкой <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> над ограниченными коллекциями метод пытается добавить или убрать элемент. Если элемент доступен, то он заносится в указанную по ссылке переменную, после чего метод возвращает значение true. Если по прошествии определенного времени ожидания элемент так и не удается извлечь, метод возвращает значение false. После этого поток может перейти к другой полезной работе, прежде чем повторить попытку обращения к коллекции. Пример доступа с временной блокировкой см. во втором примере из раздела [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## <a name="cancelling-add-and-take-operations"></a>Отмена операций Add и Take  
 Операции Add и Take обычно выполняются в цикле. Отменить цикл можно, передав <xref:System.Threading.CancellationToken> в метод <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> или <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, а затем проверяя значение свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> токена при каждой итерации. Если значение равно true, за обработку запроса отмены отвечает разработчик, которому следует освободить ресурсы и завершить цикл. Следующий пример показывает перегрузку метода <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>, который принимает токен отмены, и код, использующий его:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 Пример добавления поддержки отмены см. во втором примере из статьи [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## <a name="specifying-the-collection-type"></a>Указание типа коллекции  
 При создании коллекции <xref:System.Collections.Concurrent.BlockingCollection%601> можно указать не только предельную емкость, но и тип используемой коллекции. Например, можно указать <xref:System.Collections.Concurrent.ConcurrentQueue%601> для поведения "первым поступил — первым обслужен" (FIFO) или <xref:System.Collections.Concurrent.ConcurrentStack%601> для поведения "последним поступил — первым обслужен" (LIFO). Использовать можно любой класс коллекции, реализующий интерфейс <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>. Тип коллекции по умолчанию для <xref:System.Collections.Concurrent.BlockingCollection%601> — <xref:System.Collections.Concurrent.ConcurrentQueue%601>. В следующем примере кода демонстрируется создание коллекции <xref:System.Collections.Concurrent.BlockingCollection%601> емкостью 1000 строк, которая использует <xref:System.Collections.Concurrent.ConcurrentBag%601>:  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 Дополнительные сведения см. в статье [Практическое руководство. Добавление функций границы и блокировки в коллекцию](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md).  
  
## <a name="ienumerable-support"></a>Поддержка интерфейса IEnumerable  
 <xref:System.Collections.Concurrent.BlockingCollection%601> предоставляет метод <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>, который позволяет объектам-получателям использовать `foreach` (`For Each` в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]) для удаления элементов до тех пор, пока не закончится коллекция, т. е. она будет пуста и больше элементы добавляться не будут. Дополнительные сведения см. в разделе [Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).  
  
## <a name="using-many-blockingcollections-as-one"></a>Использование нескольких коллекций BlockingCollection в качестве одной коллекции  
 Для сценариев, в которых потребителю необходимо одновременно извлекать элементы из нескольких коллекций, можно создавать массивы из <xref:System.Collections.Concurrent.BlockingCollection%601> и использовать статические методы, такие как <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A>, позволяющие добавлять и извлекать элементы любой коллекции в массиве. Если одна из коллекций заблокирована, метод немедленно переходит к другой, пока не найдет коллекцию, способную выполнить операцию. Дополнительные сведения см. в разделе [Практическое руководство. Использование массивов для блокировки коллекций в конвейере](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Коллекции и структуры данных](../../../../docs/standard/collections/index.md)   
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)
