---
title: Статистические запросы
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: e61b16d6337c9b40f9e94052869a4c5592291d71
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248104"
---
# <a name="aggregate-queries"></a><span data-ttu-id="fafcc-102">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="fafcc-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fafcc-103">поддерживает агрегатные операторы `Average`, `Count`, `Max`, `Min` и `Sum`.</span><span class="sxs-lookup"><span data-stu-id="fafcc-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="fafcc-104">Обратите внимание на следующие характеристики агрегатных операторов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fafcc-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="fafcc-105">Агрегатные запросы выполняются немедленно.</span><span class="sxs-lookup"><span data-stu-id="fafcc-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="fafcc-106">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fafcc-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="fafcc-107">Агрегатные запросы обычно возвращают число, а не коллекцию.</span><span class="sxs-lookup"><span data-stu-id="fafcc-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="fafcc-108">Дополнительные сведения см. в разделе [операции агрегирования](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="fafcc-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="fafcc-109">В анонимном типе вызвать агрегаты нельзя.</span><span class="sxs-lookup"><span data-stu-id="fafcc-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="fafcc-110">В следующих разделах используются примеры из учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="fafcc-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="fafcc-111">Дополнительные сведения см. в статье [Загрузка образцов баз данных](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fafcc-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fafcc-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fafcc-112">In This Section</span></span>  
 [<span data-ttu-id="fafcc-113">Возврат среднего значения из числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="fafcc-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="fafcc-114">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="fafcc-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="fafcc-115">Подсчет количества элементов в последовательности</span><span class="sxs-lookup"><span data-stu-id="fafcc-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="fafcc-116">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="fafcc-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="fafcc-117">Нахождение наибольшего значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="fafcc-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="fafcc-118">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="fafcc-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="fafcc-119">Нахождение наименьшего значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="fafcc-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="fafcc-120">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="fafcc-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="fafcc-121">Вычисление суммы значений числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="fafcc-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="fafcc-122">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="fafcc-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fafcc-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fafcc-123">Related Sections</span></span>  
 [<span data-ttu-id="fafcc-124">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="fafcc-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="fafcc-125">Содержит ссылки на запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] в Visual Basic и C#.</span><span class="sxs-lookup"><span data-stu-id="fafcc-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="fafcc-126">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="fafcc-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="fafcc-127">Содержит ссылки на разделы, в которых объясняются принципы разработки запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fafcc-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="fafcc-128">Введение в запросы LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="fafcc-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="fafcc-129">Содержит описание принципов работы запросов в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fafcc-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
