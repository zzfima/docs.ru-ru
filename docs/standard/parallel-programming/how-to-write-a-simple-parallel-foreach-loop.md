---
title: Создание простой параллельной программы с использованием Parallel.ForEach
ms.date: 09/12/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cdf4aeb6de027e26687d41d6311b6d7da49e7948
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562222"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="ff968-102">Практическое руководство. Написание простого цикла Parallel.ForEach</span><span class="sxs-lookup"><span data-stu-id="ff968-102">How to: Write a Simple Parallel.ForEach Loop</span></span>

<span data-ttu-id="ff968-103">В этом примере показано, как использовать цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> для включения параллелизма данных в любом источнике данных <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ff968-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="ff968-104">В этой документации для определения делегатов в PLINQ используются лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="ff968-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="ff968-105">Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="ff968-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="ff968-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ff968-106">Example</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="ff968-107">Цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A> действует как цикл <xref:System.Threading.Tasks.Parallel.For%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff968-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="ff968-108">Исходная коллекция разделяется на секции, и задачи распределяются по нескольким потокам с учетом доступной среды системы.</span><span class="sxs-lookup"><span data-stu-id="ff968-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="ff968-109">Чем больше в системе процессоров, тем быстрее выполняются параллельные методы.</span><span class="sxs-lookup"><span data-stu-id="ff968-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="ff968-110">Для некоторых исходных коллекций, в зависимости от размера источника и типа выполняемых работ, последовательный цикл может оказаться быстрее.</span><span class="sxs-lookup"><span data-stu-id="ff968-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="ff968-111">Дополнительные сведения о производительности см. в статье [Потенциальные ошибки, связанные с параллелизмом данных и задач](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="ff968-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>

<span data-ttu-id="ff968-112">Дополнительные сведения о параллельных циклах см. в статье [Практическое руководство. Написание простого цикла Parallel.For](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="ff968-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="ff968-113">Чтобы применить <xref:System.Threading.Tasks.Parallel.ForEach%2A> для неуниверсальной коллекции, вы можете преобразовать ее в универсальную коллекцию с помощью метода расширения <xref:System.Linq.Enumerable.Cast%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ff968-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="ff968-114">Также вы можете использовать Parallel LINQ (PLINQ) для параллельной обработки источников данных <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ff968-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="ff968-115">PLINQ позволяет применять декларативный синтаксис запроса для описания поведения цикла.</span><span class="sxs-lookup"><span data-stu-id="ff968-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="ff968-116">Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="ff968-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="ff968-117">Скомпилируйте и запустите код.</span><span class="sxs-lookup"><span data-stu-id="ff968-117">Compile and run the code</span></span>

- <span data-ttu-id="ff968-118">Скопируйте этот код и вставьте его в проект **консольного приложения** Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff968-118">Copy and paste this code into a Visual Studio **Console App** project.</span></span>

- <span data-ttu-id="ff968-119">Добавьте ссылку на файл System.Drawing.dll.</span><span class="sxs-lookup"><span data-stu-id="ff968-119">Add a reference to System.Drawing.dll</span></span>

- <span data-ttu-id="ff968-120">Нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="ff968-120">Press **F5**</span></span>

## <a name="see-also"></a><span data-ttu-id="ff968-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ff968-121">See also</span></span>

- [<span data-ttu-id="ff968-122">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="ff968-122">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="ff968-123">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="ff968-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="ff968-124">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="ff968-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
