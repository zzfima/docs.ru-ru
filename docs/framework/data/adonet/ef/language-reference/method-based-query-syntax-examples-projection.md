---
title: Примеры синтаксиса запросов на основе методов. Проекция
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: a38fce33fe34bf6485d0d5fcef4f194f4c2470b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194998"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="b7916-102">Примеры синтаксиса запросов на основе методов. Проекция</span><span class="sxs-lookup"><span data-stu-id="b7916-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="b7916-103">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.Select%2A> и <xref:System.Linq.Enumerable.SelectMany%2A> методы запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="b7916-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="b7916-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b7916-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b7916-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="b7916-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="b7916-106">Выбрать</span><span class="sxs-lookup"><span data-stu-id="b7916-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="b7916-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b7916-107">Example</span></span>  
 <span data-ttu-id="b7916-108">В следующем примере используется метод <xref:System.Linq.Queryable.Select%2A> для проецирования свойств `Product.Name` и `Product.ProductID` в последовательность анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="b7916-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="b7916-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b7916-109">Example</span></span>  
 <span data-ttu-id="b7916-110">В следующем примере используется метод <xref:System.Linq.Enumerable.Select%2A> для возвращения последовательности только названий продуктов.</span><span class="sxs-lookup"><span data-stu-id="b7916-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="b7916-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="b7916-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="b7916-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b7916-112">Example</span></span>  
 <span data-ttu-id="b7916-113">В следующем примере используется метод <xref:System.Linq.Enumerable.SelectMany%2A> для выборки всех заказов, в которых `TotalDue` меньше 500,00.</span><span class="sxs-lookup"><span data-stu-id="b7916-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="b7916-114">Пример</span><span class="sxs-lookup"><span data-stu-id="b7916-114">Example</span></span>  
 <span data-ttu-id="b7916-115">В следующем примере используется метод <xref:System.Linq.Enumerable.SelectMany%2A> для выборки всех заказов, сделанных 1 октября 2002 или позже.</span><span class="sxs-lookup"><span data-stu-id="b7916-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="b7916-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b7916-116">See also</span></span>

- [<span data-ttu-id="b7916-117">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b7916-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
