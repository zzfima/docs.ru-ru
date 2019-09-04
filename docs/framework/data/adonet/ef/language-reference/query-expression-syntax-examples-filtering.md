---
title: Примеры синтаксиса выражений запросов. Фильтрация
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c27cb89c-1c1d-4988-9f38-950eda3cb275
ms.openlocfilehash: 84de36b79ed646d73a8f2d8e00c26d8dcf6de4b7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249508"
---
# <a name="query-expression-syntax-examples-filtering"></a><span data-ttu-id="d8f49-102">Примеры синтаксиса выражений запросов. Фильтрация</span><span class="sxs-lookup"><span data-stu-id="d8f49-102">Query Expression Syntax Examples: Filtering</span></span>
<span data-ttu-id="d8f49-103">В примерах этого раздела показано, как использовать `Where` методы и `Where…Contains` для запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с помощью синтаксиса выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="d8f49-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="d8f49-104">Примечание. где...`Contains`</span><span class="sxs-lookup"><span data-stu-id="d8f49-104">Note, Where…`Contains`</span></span> <span data-ttu-id="d8f49-105">не может использоваться как часть [скомпилированного запроса](compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="d8f49-105">cannot be used as a part of a [compiled query](compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="d8f49-106">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d8f49-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d8f49-107">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="d8f49-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="d8f49-108">Where</span><span class="sxs-lookup"><span data-stu-id="d8f49-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="d8f49-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d8f49-109">Example</span></span>  
 <span data-ttu-id="d8f49-110">В следующем примере возвращаются все заказы, совершенные через Интернет.</span><span class="sxs-lookup"><span data-stu-id="d8f49-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1)]
 [!code-vb[DP L2E Examples#Where1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1)]  
  
### <a name="example"></a><span data-ttu-id="d8f49-111">Пример</span><span class="sxs-lookup"><span data-stu-id="d8f49-111">Example</span></span>  
 <span data-ttu-id="d8f49-112">В следующем примере возвращаются заказы, объем которых больше 2 и меньше 6.</span><span class="sxs-lookup"><span data-stu-id="d8f49-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2)]
 [!code-vb[DP L2E Examples#Where2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2)]  
  
### <a name="example"></a><span data-ttu-id="d8f49-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d8f49-113">Example</span></span>  
 <span data-ttu-id="d8f49-114">В следующем примере возвращаются все продукты красного цвета.</span><span class="sxs-lookup"><span data-stu-id="d8f49-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3)]
 [!code-vb[DP L2E Examples#Where3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3)]  
  
### <a name="example"></a><span data-ttu-id="d8f49-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d8f49-115">Example</span></span>  
 <span data-ttu-id="d8f49-116">В следующем примере используется метод `Where` для нахождения заказов, сделанных после 1 декабря 2003 г. После этого с помощью свойства навигации `order.SalesOrderDetail` определяются подробности каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="d8f49-116">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="wherecontains"></a><span data-ttu-id="d8f49-117">Конструкция Where…Contains</span><span class="sxs-lookup"><span data-stu-id="d8f49-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="d8f49-118">Пример</span><span class="sxs-lookup"><span data-stu-id="d8f49-118">Example</span></span>  
 <span data-ttu-id="d8f49-119">В следующем примере массив используется как часть предложения `Where…Contains` для поиска всех товаров, идентификатор `ProductModelID` которых имеет совпадающее значение в массиве.</span><span class="sxs-lookup"><span data-stu-id="d8f49-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#1)]
 [!code-vb[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#1)]  
  
> [!NOTE]
> <span data-ttu-id="d8f49-120">В составе предиката в предложении `Where…Contains` можно использовать массив <xref:System.Array>, список <xref:System.Collections.Generic.List%601> или коллекцию любого типа, которые реализуют интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d8f49-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="d8f49-121">Можно также объявить и инициализировать коллекцию в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="d8f49-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="d8f49-122">Дополнительные сведения см. в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d8f49-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d8f49-123">Пример</span><span class="sxs-lookup"><span data-stu-id="d8f49-123">Example</span></span>  
 <span data-ttu-id="d8f49-124">В следующем примере массивы объявляются и инициализируются в предложении `Where…Contains` для поиска всех продуктов, идентификатор `ProductModelID` или размер `Size` которых имеет совпадающее значение в массивах.</span><span class="sxs-lookup"><span data-stu-id="d8f49-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or `Size` that match values in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#2)]
 [!code-vb[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d8f49-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d8f49-125">See also</span></span>

- [<span data-ttu-id="d8f49-126">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d8f49-126">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
