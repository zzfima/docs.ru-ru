---
title: "Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b0f0ed30ae5192ed8a8f069d591855857bd2fa49
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="b7299-102">Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="b7299-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>
<span data-ttu-id="b7299-103">Помимо извлечения элементов из коллекции <xref:System.Collections.Concurrent.BlockingCollection%601> с помощью методов <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, можно использовать цикл [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) в Visual Basic) для удаления элементов до тех пор, пока добавление не будет завершено и коллекция не станет пустой.</span><span class="sxs-lookup"><span data-stu-id="b7299-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="b7299-104">Это называется *изменяющим перечислением* или *поглощающим перечислением*, поскольку, в отличие от типичного цикла `foreach` (`For Each`), этот перечислитель изменяет исходную коллекцию путем удаления элементов.</span><span class="sxs-lookup"><span data-stu-id="b7299-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7299-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b7299-105">Example</span></span>  
 <span data-ttu-id="b7299-106">В приведенном ниже примере показано, как удалить все элементы в классе <xref:System.Collections.Concurrent.BlockingCollection%601>, используя цикл `foreach` (`For Each`).</span><span class="sxs-lookup"><span data-stu-id="b7299-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>  
  
 <span data-ttu-id="b7299-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span><span class="sxs-lookup"><span data-stu-id="b7299-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span></span>  
  
 <span data-ttu-id="b7299-108">Этот пример использует цикл `foreach` совместно с методом <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> в потоке-потребителе, что приводит к удалению каждого элемента из коллекции, как только он перечислен.</span><span class="sxs-lookup"><span data-stu-id="b7299-108">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="b7299-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> ограничивает максимальное количество элементов, находящихся в коллекции в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="b7299-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="b7299-110">Выполнение перечисления коллекции подобным образом блокирует поток-потребитель, если доступные элементы отсутствуют или коллекция является пустой.</span><span class="sxs-lookup"><span data-stu-id="b7299-110">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="b7299-111">В этом примере блокировка не имеет значения, так как поток-производитель добавляет элементы быстрее, чем их может использовать потребитель.</span><span class="sxs-lookup"><span data-stu-id="b7299-111">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>  
  
 <span data-ttu-id="b7299-112">Невозможно гарантировать перечисление элементов в том же порядке, в котором они добавляются потоками-производителями.</span><span class="sxs-lookup"><span data-stu-id="b7299-112">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>  
  
 <span data-ttu-id="b7299-113">Для перечисления коллекции без ее изменения просто используйте оператор `foreach` (`For Each`) без использования метода <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="b7299-113">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="b7299-114">Тем не менее важно понимать, что такой тип перечисления представляет снимок коллекции в конкретный момент времени.</span><span class="sxs-lookup"><span data-stu-id="b7299-114">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="b7299-115">Если другие потоки добавят или удалят элементы параллельно с выполнением цикла, цикл может не отобразить фактическое состояние коллекции.</span><span class="sxs-lookup"><span data-stu-id="b7299-115">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7299-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b7299-116">See Also</span></span>  
 <span data-ttu-id="b7299-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b7299-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="b7299-118">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="b7299-118">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)

