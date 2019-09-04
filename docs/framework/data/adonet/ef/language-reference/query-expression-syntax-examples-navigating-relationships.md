---
title: Примеры синтаксиса выражений запросов. Навигация по связям
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
ms.openlocfilehash: 38a8ddfe4366fefccd0a874a2ad7a20424ef8fac
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249470"
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a><span data-ttu-id="f2c66-102">Примеры синтаксиса выражений запросов. Навигация по связям</span><span class="sxs-lookup"><span data-stu-id="f2c66-102">Query Expression Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="f2c66-103">Свойства навигации в модели [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] - это свойства быстрого доступа, используемые для нахождения сущностей в элементах ассоциации.</span><span class="sxs-lookup"><span data-stu-id="f2c66-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="f2c66-104">Свойства навигации позволяют пользователю переходить от одной сущности к другой или от сущности к связанным сущностям в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="f2c66-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="f2c66-105">В этом разделе приведены примеры синтаксиса выражений запросов для навигации по связям с помощью свойств навигации в запросах LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="f2c66-105">This topic provides examples in query expression syntax of how to navigate relationships through navigation properties in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="f2c66-106">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f2c66-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f2c66-107">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="f2c66-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="f2c66-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f2c66-108">Example</span></span>  
 <span data-ttu-id="f2c66-109">В следующем примере используется метод <xref:System.Linq.Queryable.Select%2A> для возврата всех идентификаторов контактных лиц и итогового значения суммы заказов для каждого контактного лица с фамилией «Zhou».</span><span class="sxs-lookup"><span data-stu-id="f2c66-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="f2c66-110">Свойство навигации `Contact.SalesOrderHeader` используется для получения коллекции объектов `SalesOrderHeader` для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="f2c66-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="f2c66-111">Метод `Sum` использует свойство навигации `Contact.SalesOrderHeader` для получения суммы всех заказов для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="f2c66-111">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a><span data-ttu-id="f2c66-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f2c66-112">Example</span></span>  
 <span data-ttu-id="f2c66-113">В следующем примере осуществляется возврат всех заказов контактных лиц с фамилией «Zhou».</span><span class="sxs-lookup"><span data-stu-id="f2c66-113">The following example gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="f2c66-114">Свойство навигации `Contact.SalesOrderHeader` используется для получения коллекции объектов `SalesOrderHeader` для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="f2c66-114">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="f2c66-115">Имя и заказы контактного лица возвращаются в анонимном типе.</span><span class="sxs-lookup"><span data-stu-id="f2c66-115">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a><span data-ttu-id="f2c66-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f2c66-116">Example</span></span>  
 <span data-ttu-id="f2c66-117">В следующем примере используются свойства навигации объектов `SalesOrderHeader.Address` и `SalesOrderHeader.Contact` для возврата коллекции объектов `Address` и `Contact`, связанных с каждым заказом.</span><span class="sxs-lookup"><span data-stu-id="f2c66-117">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="f2c66-118">Фамилия контактного лица, адрес, номер заказа на продажу и сумма заказа по каждому заказу в Сиэттле возвращаются в анонимном типе.</span><span class="sxs-lookup"><span data-stu-id="f2c66-118">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a><span data-ttu-id="f2c66-119">Пример</span><span class="sxs-lookup"><span data-stu-id="f2c66-119">Example</span></span>  
 <span data-ttu-id="f2c66-120">В следующем примере используется метод `Where` для нахождения заказов, сделанных после 1 декабря 2003 г. После этого с помощью свойства навигации `order.SalesOrderDetail` определяются подробности каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="f2c66-120">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="f2c66-121">См. также</span><span class="sxs-lookup"><span data-stu-id="f2c66-121">See also</span></span>

- [<span data-ttu-id="f2c66-122">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f2c66-122">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
