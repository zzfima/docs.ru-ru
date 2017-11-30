---
title: "Отложенное выполнение и отложенное вычисление в LINQ to XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3a465c4448157505a42db57202298cb18e44a562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a><span data-ttu-id="fd540-102">Отложенное выполнение и отложенное вычисление в LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd540-102">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="fd540-103">Операции по обработке запросов и осей часто реализуются с использованием отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="fd540-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="fd540-104">В этом разделе разъясняются требования и достоинства отложенного выполнения, а также содержатся некоторые соображения относительно реализации.</span><span class="sxs-lookup"><span data-stu-id="fd540-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="fd540-105">Отложенное выполнение</span><span class="sxs-lookup"><span data-stu-id="fd540-105">Deferred Execution</span></span>  
 <span data-ttu-id="fd540-106">Отложенное выполнение означает, что вычисление выражения откладывается до тех пор, пока не возникнет действительная потребность в его *реализованном* значении.</span><span class="sxs-lookup"><span data-stu-id="fd540-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="fd540-107">Отложенное выполнение может значительно повышать производительность в ситуациях, когда приходится манипулировать большими коллекциями данных, особенно в программах, содержащих ряд последовательных запросов или манипуляций.</span><span class="sxs-lookup"><span data-stu-id="fd540-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="fd540-108">В лучшем случае отложенное выполнение обеспечивает только один проход по исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="fd540-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="fd540-109">Технологии LINQ предусматривают широкое использование отложенного выполнения как в членах основных классов <xref:System.Linq?displayProperty=nameWithType>, так и в методах расширений в различных пространствах имен LINQ, таких как <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd540-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=nameWithType> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="fd540-110">Сравнение безотложного  и отложенного вычислений</span><span class="sxs-lookup"><span data-stu-id="fd540-110">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="fd540-111">При создании метода, реализующего отложенное выполнение, необходимо также решать вопрос о том, следует ли реализовывать этот метод с помощью отложенного или безотложного вычисления.</span><span class="sxs-lookup"><span data-stu-id="fd540-111">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="fd540-112">В случае *отложенного вычисления* один элемент исходной коллекции обрабатывается при каждом обращении к итератору.</span><span class="sxs-lookup"><span data-stu-id="fd540-112">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="fd540-113">Это типичный способ реализации итераторов.</span><span class="sxs-lookup"><span data-stu-id="fd540-113">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="fd540-114">В случае *безотложного вычисления* при первом же обращении к итератору обрабатывается вся коллекция.</span><span class="sxs-lookup"><span data-stu-id="fd540-114">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="fd540-115">Может также потребоваться временная копия исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="fd540-115">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="fd540-116">Так, метод <xref:System.Linq.Enumerable.OrderBy%2A> должен отсортировать всю коллекцию, перед тем как возвратить ее первый элемент.</span><span class="sxs-lookup"><span data-stu-id="fd540-116">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="fd540-117">Метод неспешного вычисления обычно обеспечивает более высокую производительность, поскольку он равномерно распределяет затраты на обработку по всему периоду вычисления и сводит к минимуму использование временных данных.</span><span class="sxs-lookup"><span data-stu-id="fd540-117">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="fd540-118">Разумеется, при выполнении некоторых операций не остается ничего иного, как материализовать промежуточные результаты.</span><span class="sxs-lookup"><span data-stu-id="fd540-118">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fd540-119">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fd540-119">Next Steps</span></span>  
 <span data-ttu-id="fd540-120">Следующий раздел настоящего учебника иллюстрирует отложенное выполнение:</span><span class="sxs-lookup"><span data-stu-id="fd540-120">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="fd540-121">Пример отложенного выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd540-121">Deferred Execution Example (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd540-122">См. также</span><span class="sxs-lookup"><span data-stu-id="fd540-122">See Also</span></span>  
 [<span data-ttu-id="fd540-123">Учебник: Отложенного выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd540-123">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)  
 [<span data-ttu-id="fd540-124">Основные понятия и терминология (функциональное преобразование) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd540-124">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)  
 [<span data-ttu-id="fd540-125">Операции статистической обработки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd540-125">Aggregation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
