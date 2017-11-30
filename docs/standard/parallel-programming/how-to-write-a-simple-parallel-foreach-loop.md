---
title: "Практическое руководство. Написание простого цикла Parallel.ForEach"
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
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="7454f-102">Практическое руководство. Написание простого цикла Parallel.ForEach</span><span class="sxs-lookup"><span data-stu-id="7454f-102">How to: Write a Simple Parallel.ForEach Loop</span></span>
<span data-ttu-id="7454f-103">В этом примере показано, как использовать <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> цикла, чтобы включить параллелизм данных по какой-либо <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> источника данных.</span><span class="sxs-lookup"><span data-stu-id="7454f-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7454f-104">В этой документации для определения делегатов в PLINQ используются лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="7454f-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="7454f-105">Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="7454f-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7454f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7454f-106">Example</span></span>  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <span data-ttu-id="7454f-107">Объект <xref:System.Threading.Tasks.Parallel.ForEach%2A> цикла работает как <xref:System.Threading.Tasks.Parallel.For%2A> цикла.</span><span class="sxs-lookup"><span data-stu-id="7454f-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="7454f-108">Исходная коллекция секционируются и выполнения работы в нескольких потоках, в зависимости от среды системы.</span><span class="sxs-lookup"><span data-stu-id="7454f-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="7454f-109">Несколько процессоров в системе, тем быстрее параллельного выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="7454f-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="7454f-110">Для некоторых исходных коллекций последовательный цикл может выполняться быстрее в зависимости от размера источника и типа выполняемых работ.</span><span class="sxs-lookup"><span data-stu-id="7454f-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="7454f-111">Дополнительные сведения о производительности см. в разделе [потенциальных проблем в данных и задач](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span><span class="sxs-lookup"><span data-stu-id="7454f-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>  
  
 <span data-ttu-id="7454f-112">Дополнительные сведения о параллельных циклах см. в разделе [как: написание простого цикла Parallel.For](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="7454f-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>  
  
 <span data-ttu-id="7454f-113">Для использования <xref:System.Threading.Tasks.Parallel.ForEach%2A> с неуниверсальной коллекции, можно использовать <xref:System.Linq.Enumerable.Cast%2A> метода расширения для преобразования коллекции базовой коллекции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7454f-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 <span data-ttu-id="7454f-114">Можно также использовать параллельный LINQ (PLINQ) для параллельной обработки <xref:System.Collections.Generic.IEnumerable%601> источники данных.</span><span class="sxs-lookup"><span data-stu-id="7454f-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="7454f-115">PLINQ позволяет использовать декларативный синтаксис запроса для выражения поведения цикла.</span><span class="sxs-lookup"><span data-stu-id="7454f-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="7454f-116">Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="7454f-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7454f-117">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7454f-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="7454f-118">Скопируйте и вставьте этот код в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 проект консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="7454f-118">Copy and paste this code into a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 Console Application project.</span></span>  
  
-   <span data-ttu-id="7454f-119">Добавьте ссылку на System.Drawing.dll</span><span class="sxs-lookup"><span data-stu-id="7454f-119">Add a reference to System.Drawing.dll</span></span>  
  
-   <span data-ttu-id="7454f-120">Нажмите клавишу F5</span><span class="sxs-lookup"><span data-stu-id="7454f-120">Press F5</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7454f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7454f-121">See Also</span></span>  
 [<span data-ttu-id="7454f-122">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="7454f-122">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="7454f-123">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="7454f-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="7454f-124">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="7454f-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
