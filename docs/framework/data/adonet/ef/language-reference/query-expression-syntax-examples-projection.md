---
title: "Примеры синтаксиса выражений запроса. Проекция"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9f859032f1dd1de2a3e3c9cbf88735e09c923b82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="query-expression-syntax-examples-projection"></a><span data-ttu-id="b5428-102">Примеры синтаксиса выражений запроса. Проекция</span><span class="sxs-lookup"><span data-stu-id="b5428-102">Query Expression Syntax Examples: Projection</span></span>
<span data-ttu-id="b5428-103">Примеры в этом разделе демонстрируют, как использовать `Select` метод и `From … From …` ключевых слов [модели AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) с использованием синтаксиса выражений запроса.</span><span class="sxs-lookup"><span data-stu-id="b5428-103">The examples in this topic demonstrate how to use the `Select` method and the `From … From …` keywords to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="b5428-104">`From … From …` - это основанный на запросе эквивалент метода `SelectMany`.</span><span class="sxs-lookup"><span data-stu-id="b5428-104">`From … From …` is the query based equivalent of the `SelectMany` method.</span></span> <span data-ttu-id="b5428-105">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b5428-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b5428-106">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="b5428-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="b5428-107">Выбрать</span><span class="sxs-lookup"><span data-stu-id="b5428-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="b5428-108">Пример</span><span class="sxs-lookup"><span data-stu-id="b5428-108">Example</span></span>  
 <span data-ttu-id="b5428-109">В следующем примере метод <xref:System.Linq.Enumerable.Select%2A> используется для возврата всех строк из таблицы `Product` и отображения названий продуктов.</span><span class="sxs-lookup"><span data-stu-id="b5428-109">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="b5428-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b5428-110">Example</span></span>  
 <span data-ttu-id="b5428-111">В следующем примере используется метод <xref:System.Linq.Enumerable.Select%2A> для возврата последовательности, состоящей только из названий продуктов.</span><span class="sxs-lookup"><span data-stu-id="b5428-111">The following example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a><span data-ttu-id="b5428-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b5428-112">Example</span></span>  
 <span data-ttu-id="b5428-113">В следующем примере используется метод <xref:System.Linq.Queryable.Select%2A> для проецирования свойств `Product.Name` и `Product.ProductID` в последовательность анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="b5428-113">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a><span data-ttu-id="b5428-114">От...</span><span class="sxs-lookup"><span data-stu-id="b5428-114">From …</span></span> <span data-ttu-id="b5428-115">От...</span><span class="sxs-lookup"><span data-stu-id="b5428-115">From …</span></span> <span data-ttu-id="b5428-116">(SelectMany)</span><span class="sxs-lookup"><span data-stu-id="b5428-116">(SelectMany)</span></span>  
  
### <a name="example"></a><span data-ttu-id="b5428-117">Пример</span><span class="sxs-lookup"><span data-stu-id="b5428-117">Example</span></span>  
 <span data-ttu-id="b5428-118">В следующем примере используется инструкция `From … From …` (эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>) для выделения всех заказов, в которых значение `TotalDue` меньше 500,00.</span><span class="sxs-lookup"><span data-stu-id="b5428-118">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="b5428-119">Пример</span><span class="sxs-lookup"><span data-stu-id="b5428-119">Example</span></span>  
 <span data-ttu-id="b5428-120">В следующем примере используется инструкция `From … From …` (эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>) для выборки всех заказов, сделанных 1 октября 2002 г. или позже.</span><span class="sxs-lookup"><span data-stu-id="b5428-120">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="b5428-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b5428-121">Example</span></span>  
 <span data-ttu-id="b5428-122">В следующем примере используется инструкция `From … From …` (эквивалент метода <xref:System.Linq.Enumerable.SelectMany%2A>) для выборки всех тех заказов, в которых итоговая сумма превышает 10 000,00, и применяется присваивание `From` для предотвращения повторного запроса того же итога.</span><span class="sxs-lookup"><span data-stu-id="b5428-122">The following example uses a `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="b5428-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b5428-123">See Also</span></span>  
 [<span data-ttu-id="b5428-124">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b5428-124">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
