---
title: "Практическое руководство. Использование метода Parallel.Invoke для выполнения параллельных операций"
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
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 942ba120fa5273f84ac3d0a51e276223de5f5484
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="e8929-102">Практическое руководство. Использование метода Parallel.Invoke для выполнения параллельных операций</span><span class="sxs-lookup"><span data-stu-id="e8929-102">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>
<span data-ttu-id="e8929-103">В этом примере показывается, как параллелизовать операции с помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> в библиотеке параллельных задач.</span><span class="sxs-lookup"><span data-stu-id="e8929-103">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="e8929-104">В общем источнике данных выполняются три операции.</span><span class="sxs-lookup"><span data-stu-id="e8929-104">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="e8929-105">Поскольку ни одна из этих операций не изменяет источник, они могут выполняться параллельно простым способом.</span><span class="sxs-lookup"><span data-stu-id="e8929-105">Because none of the operations modifies the source, they can be executed in parallel in a straightforward manner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8929-106">В этой документации для определения делегатов в библиотеке параллельных задач используются лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="e8929-106">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="e8929-107">Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="e8929-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8929-108">Пример</span><span class="sxs-lookup"><span data-stu-id="e8929-108">Example</span></span>  
 [!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
 [!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]  
  
 <span data-ttu-id="e8929-109">Обратите внимание, что с помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> можно просто указать, какие действия должны выполняться параллельно, и среда выполнения обработает все сведения по планированию потока, включая автоматическое масштабирование на число ядер в главном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8929-109">Note that with <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>  
  
 <span data-ttu-id="e8929-110">В этом примере параллелизуются операции, но не данные.</span><span class="sxs-lookup"><span data-stu-id="e8929-110">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="e8929-111">Как вариант можно параллелизовать запросы LINQ с помощью PLINQ и выполнять эти запросы последовательно.</span><span class="sxs-lookup"><span data-stu-id="e8929-111">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="e8929-112">Кроме того, можно параллелизовать данные с помощью PLINQ.</span><span class="sxs-lookup"><span data-stu-id="e8929-112">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="e8929-113">Другим вариантом является параллелизация запросов и задач.</span><span class="sxs-lookup"><span data-stu-id="e8929-113">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="e8929-114">Хотя итоговая нагрузка может снизить производительность главных компьютеров с относительно небольшим числом процессоров, масштабирование будет выполняться гораздо лучше на компьютерах с большим числом процессоров.</span><span class="sxs-lookup"><span data-stu-id="e8929-114">Although the resulting overhead might degrade performance on host computers with relatively few processors, it would scale much better on computers with many processors.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e8929-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e8929-115">Compiling the Code</span></span>  
  
-   <span data-ttu-id="e8929-116">Скопируйте и вставьте весь пример в проект Microsoft Visual Studio 2010 и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="e8929-116">Copy and paste the entire example into a Microsoft Visual Studio 2010 project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8929-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e8929-117">See Also</span></span>  
 [<span data-ttu-id="e8929-118">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="e8929-118">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="e8929-119">Практическое руководство. Отмена задачи и ее дочерних элементов</span><span class="sxs-lookup"><span data-stu-id="e8929-119">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)  
 [<span data-ttu-id="e8929-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="e8929-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
