---
title: Примеры синтаксиса запросов на основе методов. Проекция
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: 231fe6072d9a9a561aa91d3cb52fa6963f2d72dd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250064"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="438b6-102">Примеры синтаксиса запросов на основе методов. Проекция</span><span class="sxs-lookup"><span data-stu-id="438b6-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="438b6-103">В примерах этого раздела показано, как использовать <xref:System.Linq.Enumerable.Select%2A> методы и <xref:System.Linq.Enumerable.SelectMany%2A> для запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с помощью синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="438b6-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="438b6-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="438b6-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="438b6-105">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="438b6-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="438b6-106">Выбор</span><span class="sxs-lookup"><span data-stu-id="438b6-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="438b6-107">Пример</span><span class="sxs-lookup"><span data-stu-id="438b6-107">Example</span></span>  
 <span data-ttu-id="438b6-108">В следующем примере используется метод <xref:System.Linq.Queryable.Select%2A> для проецирования свойств `Product.Name` и `Product.ProductID` в последовательность анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="438b6-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="438b6-109">Пример</span><span class="sxs-lookup"><span data-stu-id="438b6-109">Example</span></span>  
 <span data-ttu-id="438b6-110">В следующем примере используется метод <xref:System.Linq.Enumerable.Select%2A> для возвращения последовательности только названий продуктов.</span><span class="sxs-lookup"><span data-stu-id="438b6-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="438b6-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="438b6-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="438b6-112">Пример</span><span class="sxs-lookup"><span data-stu-id="438b6-112">Example</span></span>  
 <span data-ttu-id="438b6-113">В следующем примере используется метод <xref:System.Linq.Enumerable.SelectMany%2A> для выборки всех заказов, в которых `TotalDue` меньше 500,00.</span><span class="sxs-lookup"><span data-stu-id="438b6-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="438b6-114">Пример</span><span class="sxs-lookup"><span data-stu-id="438b6-114">Example</span></span>  
 <span data-ttu-id="438b6-115">В следующем примере используется метод <xref:System.Linq.Enumerable.SelectMany%2A> для выборки всех заказов, сделанных 1 октября 2002 или позже.</span><span class="sxs-lookup"><span data-stu-id="438b6-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="438b6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="438b6-116">See also</span></span>

- [<span data-ttu-id="438b6-117">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="438b6-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
