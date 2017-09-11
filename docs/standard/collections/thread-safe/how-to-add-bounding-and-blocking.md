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
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3258534cb0bf67b180080eca4f7cefc65c609fa4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a><span data-ttu-id="be4d4-102">Практическое руководство. Добавление функций границы и блокировки в коллекцию</span><span class="sxs-lookup"><span data-stu-id="be4d4-102">How to: Add Bounding and Blocking Functionality to a Collection</span></span>
<span data-ttu-id="be4d4-103">В этом примере показано, как добавлять функциональные возможности границ и блокировок в пользовательский класс коллекции путем реализации интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> в классе и последующего использования экземпляра класса в качестве механизма внутреннего хранения для объекта класса <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="be4d4-103">This example shows how to add bounding and blocking functionality to a custom collection class by implementing the <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> interface in the class, and then using a class instance as the internal storage mechanism for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>.</span></span> <span data-ttu-id="be4d4-104">Дополнительные сведения о границах и блокировках см. в разделе [Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="be4d4-104">For more information about bounding and blocking, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be4d4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="be4d4-105">Example</span></span>  
 <span data-ttu-id="be4d4-106">Пользовательский класс коллекции является базовой очередью с приоритетами, в которой уровни приоритета представляются в виде массива объектов класса <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="be4d4-106">The custom collection class is a basic priority queue in which the priority levels are represented as an array of <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> objects.</span></span> <span data-ttu-id="be4d4-107">Внутри каждой очереди дополнительное упорядочивание не выполняется.</span><span class="sxs-lookup"><span data-stu-id="be4d4-107">No additional ordering is performed within each queue.</span></span>  
  
 <span data-ttu-id="be4d4-108">В клиентском коде запускаются три задачи.</span><span class="sxs-lookup"><span data-stu-id="be4d4-108">In the client code, three tasks are started.</span></span> <span data-ttu-id="be4d4-109">Первая задача просто запрашивает нажатие клавиш, чтобы включить отмену в любой момент во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="be4d4-109">The first task just polls for keyboard strokes to enable cancellation at any point during execution.</span></span> <span data-ttu-id="be4d4-110">Вторая задача является потоком-производителем. Он добавляет новые элементы в заблокированную коллекцию и дает каждому элементу приоритет на основе случайного значения.</span><span class="sxs-lookup"><span data-stu-id="be4d4-110">The second task is the producer thread; it adds new items to the blocking collection and gives each item a priority based on a random value.</span></span> <span data-ttu-id="be4d4-111">Третья задача выполняет удаление элементов из коллекции, как только они становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="be4d4-111">The third task removes items from the collection as they become available.</span></span>  
  
 <span data-ttu-id="be4d4-112">Настройку поведения приложения можно выполнять с помощью задания более быстрого выполнения одного из потоков по сравнению с другими.</span><span class="sxs-lookup"><span data-stu-id="be4d4-112">You can adjust the behavior of the application by making one of the threads run faster than the other.</span></span> <span data-ttu-id="be4d4-113">Если производитель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как заблокированная коллекция предупреждает добавление элементов, если она уже содержит количество элементов, которое задано в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="be4d4-113">If the producer runs faster, you will notice the bounding functionality as the blocking collection prevents items from being added if it already contains the number of items that is specified in the constructor.</span></span> <span data-ttu-id="be4d4-114">Если объект-получатель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как объект-получатель ожидает добавления нового элемента.</span><span class="sxs-lookup"><span data-stu-id="be4d4-114">If the consumer runs faster, you will notice the blocking functionality as the consumer waits for a new item to be added.</span></span>  
  
 <span data-ttu-id="be4d4-115">[!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]</span><span class="sxs-lookup"><span data-stu-id="be4d4-115">[!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]</span></span>  
  
 <span data-ttu-id="be4d4-116">По умолчанию хранилищем для <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> является <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="be4d4-116">By default, the storage for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> is <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4d4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="be4d4-117">See Also</span></span>  
 [<span data-ttu-id="be4d4-118">Потокобезопасные коллекции</span><span class="sxs-lookup"><span data-stu-id="be4d4-118">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)

