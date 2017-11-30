---
title: "Практическое руководство. Синхронизация параллельных операций с барьером"
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="cb7a8-102">Практическое руководство. Синхронизация параллельных операций с барьером</span><span class="sxs-lookup"><span data-stu-id="cb7a8-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="cb7a8-103">В следующем примере показано, как синхронизация параллельных задач с <xref:System.Threading.Barrier>.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb7a8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cb7a8-104">Example</span></span>  
 <span data-ttu-id="cb7a8-105">Следующая программа предназначена для подсчета количества итераций (или этапы), необходимые для двух потоков, чтобы каждый нашел свою половину решения одной фазе, используя алгоритм перемешивания слов.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="cb7a8-106">После каждого перемешает свои слова, операция следующего этапа барьера сравнивает два результата, чтобы увидеть, если отображается полное предложение в правильном порядке слова.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="cb7a8-107">Объект <xref:System.Threading.Barrier> — это объект, который предотвращает индивидуальные задачи в параллельном режиме продолжение, пока все задачи не достигнут барьера.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="cb7a8-108">Это полезно при параллельной операции поэтапно и каждый этап требуется синхронизация между задачами.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="cb7a8-109">В этом примере осуществляется в два этапа для операции.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="cb7a8-110">На первом этапе каждая задача заполняет его часть буфера с данными.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="cb7a8-111">После завершения каждой задачи, заполняя его разделе, задача сообщает барьера, можно продолжить и ожиданий.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="cb7a8-112">Если все задачи отправили сигналы барьера, будут разблокированы и запускает на втором этапе.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="cb7a8-113">Барьер необходим, так как на втором этапе требует, чтобы каждая задача доступ ко всем данным, созданным в этой точке.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="cb7a8-114">Без барьера первого выполнения задач может попытаться выполнить чтение из буферов, которое не было заполнено еще другими задачами.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="cb7a8-115">Вы можете синхронизировать любое количество этапов таким образом.</span><span class="sxs-lookup"><span data-stu-id="cb7a8-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7a8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cb7a8-116">See Also</span></span>  
 [<span data-ttu-id="cb7a8-117">Структуры данных для параллельного программирования</span><span class="sxs-lookup"><span data-stu-id="cb7a8-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
