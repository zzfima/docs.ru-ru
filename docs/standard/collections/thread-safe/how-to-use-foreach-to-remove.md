---
title: Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collection
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
ms.openlocfilehash: f9a858dea74be63634f887c4204aefa8ac338ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711237"
---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="2b183-102">Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="2b183-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>

<span data-ttu-id="2b183-103">Помимо извлечения элементов из коллекции <xref:System.Collections.Concurrent.BlockingCollection%601> с помощью методов <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, можно использовать цикл [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) в Visual Basic) для удаления элементов до тех пор, пока добавление не будет завершено и коллекция не станет пустой.</span><span class="sxs-lookup"><span data-stu-id="2b183-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="2b183-104">Это называется *изменяющим перечислением* или *поглощающим перечислением*, поскольку, в отличие от типичного цикла `foreach` (`For Each`), этот перечислитель изменяет исходную коллекцию путем удаления элементов.</span><span class="sxs-lookup"><span data-stu-id="2b183-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>

## <a name="example"></a><span data-ttu-id="2b183-105">Пример</span><span class="sxs-lookup"><span data-stu-id="2b183-105">Example</span></span>

<span data-ttu-id="2b183-106">В приведенном ниже примере показано, как удалить все элементы в классе <xref:System.Collections.Concurrent.BlockingCollection%601>, используя цикл `foreach` (`For Each`).</span><span class="sxs-lookup"><span data-stu-id="2b183-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>

[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
[!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]

<span data-ttu-id="2b183-107">Этот пример использует цикл `foreach` совместно с методом <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> в потоке-потребителе, что приводит к удалению каждого элемента из коллекции, как только он перечислен.</span><span class="sxs-lookup"><span data-stu-id="2b183-107">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="2b183-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> ограничивает максимальное количество элементов, находящихся в коллекции в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="2b183-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="2b183-109">Выполнение перечисления коллекции подобным образом блокирует поток-потребитель, если доступные элементы отсутствуют или коллекция является пустой.</span><span class="sxs-lookup"><span data-stu-id="2b183-109">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="2b183-110">В этом примере блокировка не имеет значения, так как поток-производитель добавляет элементы быстрее, чем их может использовать потребитель.</span><span class="sxs-lookup"><span data-stu-id="2b183-110">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>

<span data-ttu-id="2b183-111">Невозможно гарантировать перечисление элементов в том же порядке, в котором они добавляются потоками-производителями.</span><span class="sxs-lookup"><span data-stu-id="2b183-111">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>

<span data-ttu-id="2b183-112">Для перечисления коллекции без ее изменения просто используйте оператор `foreach` (`For Each`) без использования метода <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b183-112">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="2b183-113">Тем не менее важно понимать, что такой тип перечисления представляет снимок коллекции в конкретный момент времени.</span><span class="sxs-lookup"><span data-stu-id="2b183-113">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="2b183-114">Если другие потоки добавят или удалят элементы параллельно с выполнением цикла, цикл может не отобразить фактическое состояние коллекции.</span><span class="sxs-lookup"><span data-stu-id="2b183-114">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b183-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2b183-115">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="2b183-116">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="2b183-116">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)
