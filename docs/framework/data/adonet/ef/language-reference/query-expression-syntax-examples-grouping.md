---
title: Примеры синтаксиса выражений запроса. Группировка
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: a5222110bc5ac41ecaaa8e5003262360fd4d9ff5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763528"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="0fcc1-102">Примеры синтаксиса выражений запроса. Группировка</span><span class="sxs-lookup"><span data-stu-id="0fcc1-102">Query Expression Syntax Examples: Grouping</span></span>
<span data-ttu-id="0fcc1-103">Примеры в этом разделе демонстрируют, как использовать `GroupBy` метод для запроса [модели AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) с использованием синтаксиса выражений запроса.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="0fcc1-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0fcc1-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="0fcc1-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="0fcc1-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0fcc1-106">Example</span></span>  
 <span data-ttu-id="0fcc1-107">В следующем примере происходит возврат объектов `Address`, сгруппированных по почтовым индексам.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="0fcc1-108">Результаты проецируются в анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="0fcc1-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0fcc1-109">Example</span></span>  
 <span data-ttu-id="0fcc1-110">В следующем примере происходит возврат объектов `Contact`, сгруппированных по первой букве фамилий контактных лиц.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="0fcc1-111">Результаты также сортируются по первой букве фамилии и проецируются в анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="0fcc1-112">Пример</span><span class="sxs-lookup"><span data-stu-id="0fcc1-112">Example</span></span>  
 <span data-ttu-id="0fcc1-113">В следующем примере возвращаются объекты `SalesOrderHeader`, сгруппированные по идентификаторам клиента.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="0fcc1-114">Также возвращается число продаж для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="0fcc1-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="0fcc1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0fcc1-115">See Also</span></span>  
 [<span data-ttu-id="0fcc1-116">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="0fcc1-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
