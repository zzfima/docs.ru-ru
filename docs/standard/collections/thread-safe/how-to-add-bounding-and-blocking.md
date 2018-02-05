---
title: "Практическое руководство. Добавление функций границы и блокировки в коллекцию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7fe57d99382c3472d0af5e5f64f7b237692b921b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a><span data-ttu-id="34a9b-102">Практическое руководство. Добавление функций границы и блокировки в коллекцию</span><span class="sxs-lookup"><span data-stu-id="34a9b-102">How to: Add Bounding and Blocking Functionality to a Collection</span></span>
<span data-ttu-id="34a9b-103">В этом примере показано, как добавлять функциональные возможности границ и блокировок в пользовательский класс коллекции путем реализации интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> в классе и последующего использования экземпляра класса в качестве механизма внутреннего хранения для объекта класса <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34a9b-103">This example shows how to add bounding and blocking functionality to a custom collection class by implementing the <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> interface in the class, and then using a class instance as the internal storage mechanism for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="34a9b-104">Дополнительные сведения о границах и блокировках см. в разделе [Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="34a9b-104">For more information about bounding and blocking, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a9b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="34a9b-105">Example</span></span>  
 <span data-ttu-id="34a9b-106">Пользовательский класс коллекции является базовой очередью с приоритетами, в которой уровни приоритета представляются в виде массива объектов класса <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34a9b-106">The custom collection class is a basic priority queue in which the priority levels are represented as an array of <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="34a9b-107">Внутри каждой очереди дополнительное упорядочивание не выполняется.</span><span class="sxs-lookup"><span data-stu-id="34a9b-107">No additional ordering is performed within each queue.</span></span>  
  
 <span data-ttu-id="34a9b-108">В клиентском коде запускаются три задачи.</span><span class="sxs-lookup"><span data-stu-id="34a9b-108">In the client code, three tasks are started.</span></span> <span data-ttu-id="34a9b-109">Первая задача просто запрашивает нажатие клавиш, чтобы включить отмену в любой момент во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="34a9b-109">The first task just polls for keyboard strokes to enable cancellation at any point during execution.</span></span> <span data-ttu-id="34a9b-110">Вторая задача является потоком-производителем. Он добавляет новые элементы в заблокированную коллекцию и дает каждому элементу приоритет на основе случайного значения.</span><span class="sxs-lookup"><span data-stu-id="34a9b-110">The second task is the producer thread; it adds new items to the blocking collection and gives each item a priority based on a random value.</span></span> <span data-ttu-id="34a9b-111">Третья задача выполняет удаление элементов из коллекции, как только они становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="34a9b-111">The third task removes items from the collection as they become available.</span></span>  
  
 <span data-ttu-id="34a9b-112">Настройку поведения приложения можно выполнять с помощью задания более быстрого выполнения одного из потоков по сравнению с другими.</span><span class="sxs-lookup"><span data-stu-id="34a9b-112">You can adjust the behavior of the application by making one of the threads run faster than the other.</span></span> <span data-ttu-id="34a9b-113">Если производитель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как заблокированная коллекция предупреждает добавление элементов, если она уже содержит количество элементов, которое задано в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="34a9b-113">If the producer runs faster, you will notice the bounding functionality as the blocking collection prevents items from being added if it already contains the number of items that is specified in the constructor.</span></span> <span data-ttu-id="34a9b-114">Если объект-получатель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как объект-получатель ожидает добавления нового элемента.</span><span class="sxs-lookup"><span data-stu-id="34a9b-114">If the consumer runs faster, you will notice the blocking functionality as the consumer waits for a new item to be added.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 <span data-ttu-id="34a9b-115">По умолчанию хранилищем для <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> является <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34a9b-115">By default, the storage for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> is <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a9b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="34a9b-116">See Also</span></span>  
 [<span data-ttu-id="34a9b-117">Потокобезопасные коллекции</span><span class="sxs-lookup"><span data-stu-id="34a9b-117">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
