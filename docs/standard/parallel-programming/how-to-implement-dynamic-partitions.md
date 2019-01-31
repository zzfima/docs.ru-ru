---
title: Как выполнить Реализация динамических секций
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 792488e53ffb7f870e21fdd1ad3ef94bf0303b1a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720240"
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="269af-102">Как выполнить Реализация динамических секций</span><span class="sxs-lookup"><span data-stu-id="269af-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="269af-103">Приведенный ниже пример демонстрирует, как реализовать пользовательский <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> с реализацией динамического секционирования, который можно использовать из некоторых перегрузок <xref:System.Threading.Tasks.Parallel.ForEach%2A> и из PLINQ.</span><span class="sxs-lookup"><span data-stu-id="269af-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="269af-104">Пример</span><span class="sxs-lookup"><span data-stu-id="269af-104">Example</span></span>  
 <span data-ttu-id="269af-105">Каждый раз, когда секция вызывает для перечислителя <xref:System.Collections.IEnumerator.MoveNext%2A>, этот перечислитель предоставляет ей один элемент списка.</span><span class="sxs-lookup"><span data-stu-id="269af-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="269af-106">При работе с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A> секция реализована в виде экземпляра <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="269af-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="269af-107">Поскольку запросы возникают параллельно в нескольких потоках, доступ к текущему индексу синхронизируется.</span><span class="sxs-lookup"><span data-stu-id="269af-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="269af-108">Здесь представлен пример блочного секционирования, в котором каждый блок состоит из одного элемента.</span><span class="sxs-lookup"><span data-stu-id="269af-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="269af-109">Передавая несколько элементов на один запрос, вы снизите риск конфликтов блокировки и, возможно, увеличите производительность.</span><span class="sxs-lookup"><span data-stu-id="269af-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="269af-110">Но использование больших блоков в определенный момент потребует дополнительной логики для балансировки нагрузки, чтобы все потоки оставались равномерно загруженными до полного завершения всех действий.</span><span class="sxs-lookup"><span data-stu-id="269af-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269af-111">См. также</span><span class="sxs-lookup"><span data-stu-id="269af-111">See also</span></span>

- [<span data-ttu-id="269af-112">Пользовательские разделители для PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="269af-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="269af-113">Практическое руководство. Реализация разделителя для статического секционирования</span><span class="sxs-lookup"><span data-stu-id="269af-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
