---
title: Parallel LINQ (PLINQ)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
caps.latest.revision: 17
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5c24f51401b1e493864409ddafe580cea7ac435e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="parallel-linq-plinq"></a><span data-ttu-id="94379-102">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="94379-102">Parallel LINQ (PLINQ)</span></span>
<span data-ttu-id="94379-103">Parallel LINQ (PLINQ) является параллельной реализацией LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="94379-103">Parallel LINQ (PLINQ) is a parallel implementation of LINQ to Objects.</span></span> <span data-ttu-id="94379-104">PLINQ реализует полный набор стандартных операторов запроса LINQ как методов расширения для пространства имен <xref:System.Linq> и имеет дополнительные операторы для параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="94379-104">PLINQ implements the full set of LINQ standard query operators as extension methods for the <xref:System.Linq> namespace and has additional operators for parallel operations.</span></span> <span data-ttu-id="94379-105">PLINQ объединяет простоту и удобство чтения синтаксиса LINQ с мощностью параллельного программирования.</span><span class="sxs-lookup"><span data-stu-id="94379-105">PLINQ combines the simplicity and readability of LINQ syntax with the power of parallel programming.</span></span> <span data-ttu-id="94379-106">Подобно коду, предназначенному для библиотеки параллельных задач, запросы PLINQ масштабируются в степень параллелизма на основе возможностей главного компьютера.</span><span class="sxs-lookup"><span data-stu-id="94379-106">Just like code that targets the Task Parallel Library, PLINQ queries scale in the degree of concurrency based on the capabilities of the host computer.</span></span>  
  
 <span data-ttu-id="94379-107">Во многих сценариях PLINQ может значительно увеличить скорость запросов LINQ to Objects, более эффективно используя все доступные ядра на главном компьютере.</span><span class="sxs-lookup"><span data-stu-id="94379-107">In many scenarios, PLINQ can significantly increase the speed of LINQ to Objects queries by using all available cores on the host computer more efficiently.</span></span> <span data-ttu-id="94379-108">Повышенная производительность увеличивает мощность высокопроизводительных вычислений на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="94379-108">This increased performance brings high performance computing power onto the desktop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94379-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="94379-109">In This Section</span></span>  
 [<span data-ttu-id="94379-110">Введение в PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-110">Introduction to PLINQ</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [<span data-ttu-id="94379-111">Общее представление об ускорении выполнения в PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-111">Understanding Speedup in PLINQ</span></span>](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [<span data-ttu-id="94379-112">Сохранение порядка в PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-112">Order Preservation in PLINQ</span></span>](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [<span data-ttu-id="94379-113">Параметры слияния в PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-113">Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [<span data-ttu-id="94379-114">Практическое руководство. Создание и выполнение простого запроса PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-114">How to: Create and Execute a Simple PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [<span data-ttu-id="94379-115">Практическое руководство. Управление порядком в запросе PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-115">How to: Control Ordering in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [<span data-ttu-id="94379-116">Практическое руководство. Объединение параллельных и последовательных запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="94379-116">How to: Combine Parallel and Sequential LINQ Queries</span></span>](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [<span data-ttu-id="94379-117">Практическое руководство. Обработка исключений в запросе PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-117">How to: Handle Exceptions in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [<span data-ttu-id="94379-118">Практическое руководство. Отмена запроса PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-118">How to: Cancel a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [<span data-ttu-id="94379-119">Практическое руководство. Написание пользовательской агрегатной функции PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-119">How to: Write a Custom PLINQ Aggregate Function</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [<span data-ttu-id="94379-120">Практическое руководство. Задание режима выполнения в PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-120">How to: Specify the Execution Mode in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [<span data-ttu-id="94379-121">Практическое руководство. Задание параметров слияния в PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-121">How to: Specify Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [<span data-ttu-id="94379-122">Практическое руководство. Перебор каталогов с файлами с помощью PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-122">How to: Iterate File Directories with PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [<span data-ttu-id="94379-123">Практическое руководство. Измерение производительности запросов PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-123">How to: Measure PLINQ Query Performance</span></span>](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [<span data-ttu-id="94379-124">Пример данных PLINQ</span><span class="sxs-lookup"><span data-stu-id="94379-124">PLINQ Data Sample</span></span>](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a><span data-ttu-id="94379-125">См. также</span><span class="sxs-lookup"><span data-stu-id="94379-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="94379-126">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="94379-126">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="94379-127">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="94379-127">LINQ (Language-Integrated Query)</span></span>](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
