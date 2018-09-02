---
title: Примеры синтаксиса запросов на основе методов. Группировка
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 2fd64cb16224290d76efe327978083b1e834d6cb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401062"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="eb90c-102">Примеры синтаксиса запросов на основе методов. Группировка</span><span class="sxs-lookup"><span data-stu-id="eb90c-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="eb90c-103">Примеры в этом разделе демонстрируется использование `GroupBy` метод для запроса [модели AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="eb90c-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="eb90c-104">Модель AdventureWorks Sales, которая используется в этих примерах, построена на основе таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail в образце базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="eb90c-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="eb90c-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="eb90c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="eb90c-106">Пример</span><span class="sxs-lookup"><span data-stu-id="eb90c-106">Example</span></span>  
 <span data-ttu-id="eb90c-107">В следующем примере метод `GroupBy` возвращает объекты `Address`, сгруппированные по почтовому индексу.</span><span class="sxs-lookup"><span data-stu-id="eb90c-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="eb90c-108">Результаты проецируются в анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="eb90c-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="eb90c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="eb90c-109">Example</span></span>  
 <span data-ttu-id="eb90c-110">В следующем примере метод `GroupBy` возвращает объекты `Contact`, сгруппированные по первой букве фамилии контактного лица.</span><span class="sxs-lookup"><span data-stu-id="eb90c-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="eb90c-111">Кроме того, результаты сортируются по первой букве фамилии и проецируются на анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="eb90c-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="eb90c-112">Пример</span><span class="sxs-lookup"><span data-stu-id="eb90c-112">Example</span></span>  
 <span data-ttu-id="eb90c-113">В следующем примере метод `GroupBy` возвращает объекты `SalesOrderHeader`, сгруппированные по идентификаторам клиентов.</span><span class="sxs-lookup"><span data-stu-id="eb90c-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="eb90c-114">Также возвращается число продаж для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="eb90c-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="eb90c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="eb90c-115">See Also</span></span>  
 [<span data-ttu-id="eb90c-116">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="eb90c-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
