---
title: Практическое руководство. Реализация динамических разделов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 3970566b4e3f51ce538c328d4e69b20ec22ec09b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091421"
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="7a9eb-102">Практическое руководство. Реализация динамических разделов</span><span class="sxs-lookup"><span data-stu-id="7a9eb-102">How to: Implement Dynamic Partitions</span></span>

<span data-ttu-id="7a9eb-103">Приведенный ниже пример демонстрирует, как реализовать пользовательский <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> с реализацией динамического секционирования, который можно использовать из некоторых перегрузок <xref:System.Threading.Tasks.Parallel.ForEach%2A> и из PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a9eb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7a9eb-104">Example</span></span>

<span data-ttu-id="7a9eb-105">Каждый раз, когда секция вызывает для перечислителя <xref:System.Collections.IEnumerator.MoveNext%2A>, этот перечислитель предоставляет ей один элемент списка.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="7a9eb-106">При работе с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A> секция реализована в виде экземпляра <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="7a9eb-107">Поскольку запросы возникают параллельно в нескольких потоках, доступ к текущему индексу синхронизируется.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

<span data-ttu-id="7a9eb-108">Здесь представлен пример блочного секционирования, в котором каждый блок состоит из одного элемента.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="7a9eb-109">Передавая несколько элементов на один запрос, вы снизите риск конфликтов блокировки и, возможно, увеличите производительность.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="7a9eb-110">Но использование больших блоков в определенный момент потребует дополнительной логики для балансировки нагрузки, чтобы все потоки оставались равномерно загруженными до полного завершения всех действий.</span><span class="sxs-lookup"><span data-stu-id="7a9eb-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9eb-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7a9eb-111">See also</span></span>

* [<span data-ttu-id="7a9eb-112">Пользовательские разделители для PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="7a9eb-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
* [<span data-ttu-id="7a9eb-113">Практическое руководство. Реализация разделителя для статического секционирования</span><span class="sxs-lookup"><span data-stu-id="7a9eb-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
