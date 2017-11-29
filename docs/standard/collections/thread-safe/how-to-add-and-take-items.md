---
title: "Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b365d6d3236919f65c840343ec3b33edebea758b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a><span data-ttu-id="6d731-102">Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="6d731-102">How to: Add and Take Items Individually from a BlockingCollection</span></span>
<span data-ttu-id="6d731-103">В этом примере показано, как добавлять и удалять элементы в <xref:System.Collections.Concurrent.BlockingCollection%601> с блокировкой и без блокировки.</span><span class="sxs-lookup"><span data-stu-id="6d731-103">This example shows how to add and remove items from a <xref:System.Collections.Concurrent.BlockingCollection%601> in both a blocking and non-blocking manner.</span></span> <span data-ttu-id="6d731-104">Дополнительные сведения о <xref:System.Collections.Concurrent.BlockingCollection%601> см. в разделе [Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6d731-104">For more information on <xref:System.Collections.Concurrent.BlockingCollection%601>, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
 <span data-ttu-id="6d731-105">Пример перечисления коллекции <xref:System.Collections.Concurrent.BlockingCollection%601> до тех пор, пока она не станет пустой и никакие элементы не будут добавляться, см. в разделе [Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).</span><span class="sxs-lookup"><span data-stu-id="6d731-105">For an example of how to enumerate a <xref:System.Collections.Concurrent.BlockingCollection%601> until it is empty and no more elements will be added, see [How to: Use ForEach to Remove Items in a BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d731-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6d731-106">Example</span></span>  
 <span data-ttu-id="6d731-107">В первом примере показано, как добавлять и удалять элементы, чтобы операции блокировались, если коллекция временно пуста (при извлечении) или имеет максимальную заполненность (при добавлении), или если заданное время ожидания истекло.</span><span class="sxs-lookup"><span data-stu-id="6d731-107">This first example shows how to add and take items so that the operations will block if the collection is either temporarily empty (when taking) or at maximum capacity (when adding), or a specified timeout period has elapsed.</span></span> <span data-ttu-id="6d731-108">Обратите внимание, что блокирование при максимальной заполненности доступно, только если BlockingCollection создана с указанием максимальной емкости в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="6d731-108">Note that blocking on maximum capacity is only enabled when the BlockingCollection has been created with a maximum capacity specified in the constructor.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="6d731-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6d731-109">Example</span></span>  
 <span data-ttu-id="6d731-110">Во втором примере показано, как добавлять и извлекать элементы без блокирования операций.</span><span class="sxs-lookup"><span data-stu-id="6d731-110">This second example shows how to add and take items so that the operations will not block.</span></span> <span data-ttu-id="6d731-111">Если элементы отсутствуют, или достигнута максимальная емкость ограниченной коллекции, или время ожидания истекло, то операция <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> или <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="6d731-111">If no item is present, or maximum capacity on a bounded collection has been reached, or the timeout period has elapsed, then the <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> or <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operation returns false.</span></span> <span data-ttu-id="6d731-112">Это позволяет потоку короткое время выполнять некоторые другие полезные действия, а затем повторить попытку позднее, чтобы либо получить новый элемент, либо попытаться добавить тот же элемент, который не удалось добавить ранее.</span><span class="sxs-lookup"><span data-stu-id="6d731-112">This allows the thread to do some other useful work for awhile and then try again later to either retrieve a new item, or try to add the same item that could not be added previously.</span></span> <span data-ttu-id="6d731-113">Программа также демонстрирует, как реализовать отмену при доступе к <xref:System.Collections.Concurrent.BlockingCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="6d731-113">The program also demonstrates how to implement cancellation when accessing a <xref:System.Collections.Concurrent.BlockingCollection%601>.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="6d731-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6d731-114">See Also</span></span>  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [<span data-ttu-id="6d731-115">Общие сведения о коллекции BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="6d731-115">BlockingCollection Overview</span></span>](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)
