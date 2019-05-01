---
title: Статистические запросы
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: ed8624c47ca8e68646f176ff91b63577d64b6d1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032556"
---
# <a name="aggregate-queries"></a><span data-ttu-id="37a35-102">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="37a35-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="37a35-103">поддерживает агрегатные операторы `Average`, `Count`, `Max`, `Min` и `Sum`.</span><span class="sxs-lookup"><span data-stu-id="37a35-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="37a35-104">Обратите внимание на следующие характеристики агрегатных операторов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a35-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="37a35-105">Агрегатные запросы выполняются немедленно.</span><span class="sxs-lookup"><span data-stu-id="37a35-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="37a35-106">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="37a35-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="37a35-107">Агрегатные запросы обычно возвращают число, а не коллекцию.</span><span class="sxs-lookup"><span data-stu-id="37a35-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="37a35-108">Дополнительные сведения см. в разделе [операции агрегирования](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="37a35-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="37a35-109">В анонимном типе вызвать агрегаты нельзя.</span><span class="sxs-lookup"><span data-stu-id="37a35-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="37a35-110">В следующих разделах используются примеры из учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="37a35-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="37a35-111">Дополнительные сведения см. в разделе [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="37a35-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37a35-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="37a35-112">In This Section</span></span>  
 [<span data-ttu-id="37a35-113">Возврат среднего значения из числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="37a35-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="37a35-114">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="37a35-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="37a35-115">Подсчет количества элементов в последовательности</span><span class="sxs-lookup"><span data-stu-id="37a35-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="37a35-116">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="37a35-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="37a35-117">Нахождение наибольшего значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="37a35-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="37a35-118">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="37a35-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="37a35-119">Нахождение наименьшего значения в числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="37a35-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="37a35-120">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="37a35-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="37a35-121">Вычисление суммы значений числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="37a35-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="37a35-122">Демонстрируется использование оператора <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="37a35-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="37a35-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="37a35-123">Related Sections</span></span>  
 [<span data-ttu-id="37a35-124">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="37a35-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="37a35-125">Содержит ссылки на запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] в Visual Basic и C#.</span><span class="sxs-lookup"><span data-stu-id="37a35-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="37a35-126">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="37a35-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="37a35-127">Содержит ссылки на разделы, в которых объясняются принципы разработки запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a35-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="37a35-128">Введение в запросы LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="37a35-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="37a35-129">Содержит описание принципов работы запросов в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a35-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
