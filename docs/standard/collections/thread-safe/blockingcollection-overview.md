---
title: "Общие сведения о коллекции BlockingCollection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BlockingCollection, обзор"
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения о коллекции BlockingCollection
<xref:System.Collections.Concurrent.BlockingCollection%601> — это потокобезопасный класс коллекции, предоставляющий следующую функциональность:  
  
-   реализует шаблон "Producer\-Consumer";  
  
-   поддерживает параллельное добавление и извлечение элементов несколькими потоками;  
  
-   допускает указание максимальной емкости;  
  
-   поддерживает операции вставки и удалении, блокирующиеся при опустошении или заполнении коллекции;  
  
-   поддерживает условные операции вставки и удалении, не блокирующиеся или блокирующиеся лишь на определенное время;  
  
-   инкапсулирует все типы коллекций, реализующие интерфейс <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>;  
  
-   поддерживает отмену с помощью токенов отмены;  
  
-   поддерживает два вида перечисления с помощью оператора `foreach` \(`For Each` в Visual Basic\):  
  
    1.  перечисление "только для чтения";  
  
    2.  перечисление, при котором элементы по мере перечисления удаляются.  
  
## Поддержка границ и блокировки  
 <xref:System.Collections.Concurrent.BlockingCollection%601> поддерживает границы и блокировку.  Поддержка границ означает, что можно задать максимальную емкость коллекции.  Границы важны в ряде сценариев, поскольку они позволяют контролировать максимальный размер коллекции в памяти, предотвращая ситуации, в которых потоки\-создатели слишком сильно обгоняют потоки\-потребители.  
  
 Элементы коллекции могут параллельно добавляться из нескольких задач или потоков. Если коллекция достигает максимальной емкости, то потоки\-создатели перейдут в состояние блокировки, пока не будет удален хотя бы один элемент.  Элементы коллекции могут параллельно удаляться несколькими потребителями. Если коллекция становится пустой, то потоки\-потребители перейдут в состояние блокировки, пока поток\-создатель не добавит хотя бы один элемент.  Поток\-создатель может вызвать метод <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>, чтобы указать, что он больше не будет добавлять элементы.  Потребители могут отслеживать свойство <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A>, позволяющее определить, что коллекция опустела, а новые элементы добавляться не будут.  В следующем примере демонстрируется простая коллекция BlockingCollection с максимальной емкостью в 100 элементов.  Задача\-создатель добавляет элементы в коллекцию на протяжении всего времени сохранения истинности некоторого внешнего условия, а после этого вызывает метод <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>.  Задача\-потребитель извлекает элементы, пока свойство <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> не примет логическое значение "true".  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 Полный пример см. в разделе [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Операции с временной блокировкой  
 При использовании операций <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> ограниченных коллекций, использующих временную блокировку, метод предпринимает попытку добавления или удаления элемента.  Если элемент доступен, то он заносится в указанную по ссылке переменную, после чего метод возвращает значение "истина".  Если по прошествии определенного времени ожидания элемент так и не удается извлечь, метод возвращает значение "ложь".  После этого поток может перейти к другой полезной работе, прежде чем повторить попытку обращения к коллекции.  Пример доступа с временной блокировкой см. во втором примере из раздела [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Отмена операций Add и Take  
 Операции Add и Take обычно выполняются в цикле.  Отменить цикл можно, передав в метод <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> или <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> токен <xref:System.Threading.CancellationToken> и проверяя значение его свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> на каждой итерации.  Если значение истинно, то разработчик может обработать запрос отмены, освободив ресурсы и завершив цикл.  В следующем примере показана перегрузка метода <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A>, которая принимает токен отмены, а также код, использующий эту перегрузку:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 Пример реализации поддержки отмены см. во втором примере из раздела [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Указание типа коллекции  
 При создании класса <xref:System.Collections.Concurrent.BlockingCollection%601> можно указать не только ограничиваемую емкость, но и тип используемой коллекции.  Например, можно задать тип <xref:System.Collections.Concurrent.ConcurrentQueue%601> для использования принципа "первым поступил — первым обслужен", или тип <xref:System.Collections.Concurrent.ConcurrentStack%601> для использования принципа "последним поступил — первым обслужен".  Использовать можно любой класс коллекции, реализующий интерфейс <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.  Тип коллекции, используемый в классе <xref:System.Collections.Concurrent.BlockingCollection%601> по умолчанию — это <xref:System.Collections.Concurrent.ConcurrentQueue%601>.  В следующем примере кода показывается, как создать строковую коллекцию <xref:System.Collections.Concurrent.BlockingCollection%601> емкостью в 1000 элементов, которая использует класс <xref:System.Collections.Concurrent.ConcurrentBag%601>:  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 Для получения дополнительной информации см. [Практическое руководство. Добавление функций границы и блокировки в коллекцию](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md).  
  
## Поддержка интерфейса IEnumerable  
 <xref:System.Collections.Concurrent.BlockingCollection%601> предоставляет метод <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>, позволяющий потребителям использовать оператор `foreach` \(`For Each` в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) для удаления элементов до исчерпания коллекции \(состояния, в котором коллекция пуста и новые элементы не будут добавляться\).  Для получения дополнительной информации см. [Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).  
  
## Использование нескольких коллекций BlockingCollection в качестве одной коллекции  
 В сценариях, где потребителю необходимо одновременно извлекать элементы из нескольких коллекций, можно создавать массивы <xref:System.Collections.Concurrent.BlockingCollection%601> и использовать такие статические методы, как <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A>, позволяющие добавлять и извлекать элементы любой коллекции в массиве.  Если одна из коллекций заблокирована, метод немедленно переходит к другой, пока не найдет коллекцию, способную выполнить операцию.  Для получения дополнительной информации см. [Практическое руководство. Использование массивов для блокировки коллекций в конвейере](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md).  
  
## См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Коллекции и структуры данных](../../../../docs/standard/collections/index.md)   
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)