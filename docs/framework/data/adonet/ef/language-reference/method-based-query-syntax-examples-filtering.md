---
title: Примеры синтаксиса запросов на основе методов. Фильтрация
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
ms.openlocfilehash: 45000713d0151172762fd797bad7d7736c78a620
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43464085"
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="1bae9-102">Примеры синтаксиса запросов на основе методов. Фильтрация</span><span class="sxs-lookup"><span data-stu-id="1bae9-102">Method-Based Query Syntax Examples: Filtering</span></span>
<span data-ttu-id="1bae9-103">Примеры в этом разделе демонстрируют, как использовать `Where` и `Where…Contains` методы запроса [модели AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="1bae9-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="1bae9-104">Обратите внимание, что где...`Contains`</span><span class="sxs-lookup"><span data-stu-id="1bae9-104">Note, Where…`Contains`</span></span> <span data-ttu-id="1bae9-105">не может использоваться как часть [скомпилированного запроса](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="1bae9-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="1bae9-106">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1bae9-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="1bae9-107">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="1bae9-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="1bae9-108">Where</span><span class="sxs-lookup"><span data-stu-id="1bae9-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="1bae9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="1bae9-109">Example</span></span>  
 <span data-ttu-id="1bae9-110">В следующем примере возвращаются все заказы, совершенные через Интернет.</span><span class="sxs-lookup"><span data-stu-id="1bae9-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="1bae9-111">Пример</span><span class="sxs-lookup"><span data-stu-id="1bae9-111">Example</span></span>  
 <span data-ttu-id="1bae9-112">В следующем примере возвращаются заказы, объем которых больше 2 и меньше 6.</span><span class="sxs-lookup"><span data-stu-id="1bae9-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="1bae9-113">Пример</span><span class="sxs-lookup"><span data-stu-id="1bae9-113">Example</span></span>  
 <span data-ttu-id="1bae9-114">В следующем примере возвращаются все продукты красного цвета.</span><span class="sxs-lookup"><span data-stu-id="1bae9-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="1bae9-115">Пример</span><span class="sxs-lookup"><span data-stu-id="1bae9-115">Example</span></span>  
 <span data-ttu-id="1bae9-116">В следующем примере метод `Where` используется для нахождения заказов, сделанных после 1 декабря 2003 г. После этого свойство навигации `order.SalesOrderDetail` используется для получения подробных сведений о каждом заказе.</span><span class="sxs-lookup"><span data-stu-id="1bae9-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="1bae9-117">Конструкция Where…Contains</span><span class="sxs-lookup"><span data-stu-id="1bae9-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="1bae9-118">Пример</span><span class="sxs-lookup"><span data-stu-id="1bae9-118">Example</span></span>  
 <span data-ttu-id="1bae9-119">В следующем примере массив используется как часть предложения `Where…Contains` для поиска всех товаров, идентификатор `ProductModelID` которых имеет совпадающее значение в массиве.</span><span class="sxs-lookup"><span data-stu-id="1bae9-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="1bae9-120">В составе предиката в предложении `Where…Contains` можно использовать массив <xref:System.Array>, список <xref:System.Collections.Generic.List%601> или коллекцию любого типа, которые реализуют интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="1bae9-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="1bae9-121">Можно также объявить и инициализировать коллекцию в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="1bae9-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="1bae9-122">Дополнительные сведения см. в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1bae9-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1bae9-123">Пример</span><span class="sxs-lookup"><span data-stu-id="1bae9-123">Example</span></span>  
 <span data-ttu-id="1bae9-124">В следующем примере массивы объявляются и инициализируются в предложении `Where…Contains` для поиска всех продуктов, значения `ProductModelID` или `Size` которых имеют совпадения в массивах.</span><span class="sxs-lookup"><span data-stu-id="1bae9-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1bae9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1bae9-125">See Also</span></span>  
 [<span data-ttu-id="1bae9-126">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="1bae9-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
