---
title: Примеры синтаксиса выражений запросов. Упорядочение
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: e7591e68490bf1ac35b56d5f483d1838a0a7d0c2
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826321"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="eaf70-102">Примеры синтаксиса выражений запросов. Упорядочение</span><span class="sxs-lookup"><span data-stu-id="eaf70-102">Query Expression Syntax Examples: Ordering</span></span>
<span data-ttu-id="eaf70-103">Примеры в этом разделе демонстрируют, как использовать `OrderBy` и `OrderByDescending` методы запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с использованием синтаксиса выражений запроса.</span><span class="sxs-lookup"><span data-stu-id="eaf70-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="eaf70-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="eaf70-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="eaf70-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="eaf70-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="eaf70-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="eaf70-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="eaf70-107">Пример</span><span class="sxs-lookup"><span data-stu-id="eaf70-107">Example</span></span>  
 <span data-ttu-id="eaf70-108">В следующем примере выражение <xref:System.Linq.Enumerable.OrderBy%2A> используется для возвращения списка контактов, упорядоченного по фамилии.</span><span class="sxs-lookup"><span data-stu-id="eaf70-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="eaf70-109">Пример</span><span class="sxs-lookup"><span data-stu-id="eaf70-109">Example</span></span>  
 <span data-ttu-id="eaf70-110">В следующем примере выражение <xref:System.Linq.Enumerable.OrderBy%2A> используется для сортировки контактов по длине фамилии.</span><span class="sxs-lookup"><span data-stu-id="eaf70-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="eaf70-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="eaf70-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="eaf70-112">Пример</span><span class="sxs-lookup"><span data-stu-id="eaf70-112">Example</span></span>  
 <span data-ttu-id="eaf70-113">В следующем примере выражение `orderby… descending` (`Order By … Descending` на Visual Basic), эквивалентное методу <xref:System.Linq.Enumerable.OrderByDescending%2A>, используется для сортировки прейскуранта по убыванию.</span><span class="sxs-lookup"><span data-stu-id="eaf70-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="eaf70-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="eaf70-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="eaf70-115">Пример</span><span class="sxs-lookup"><span data-stu-id="eaf70-115">Example</span></span>  
 <span data-ttu-id="eaf70-116">В следующем примере выражения <xref:System.Linq.Queryable.OrderBy%2A> и <xref:System.Linq.Queryable.ThenBy%2A> используются для возвращения списка контактов, упорядоченных вначале по фамилии, затем по имени.</span><span class="sxs-lookup"><span data-stu-id="eaf70-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="eaf70-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="eaf70-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="eaf70-118">Пример</span><span class="sxs-lookup"><span data-stu-id="eaf70-118">Example</span></span>  
 <span data-ttu-id="eaf70-119">В следующем примере выражение `OrderBy… Descending`, эквивалентное методу <xref:System.Linq.Enumerable.ThenByDescending%2A>, используется для сортировки списка продуктов: вначале по названию, затем по прейскурантной цене - по убыванию.</span><span class="sxs-lookup"><span data-stu-id="eaf70-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="eaf70-120">См. также</span><span class="sxs-lookup"><span data-stu-id="eaf70-120">See also</span></span>
- [<span data-ttu-id="eaf70-121">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="eaf70-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
