---
title: "Примеры синтаксиса запросов на основе методов. Отношения навигации"
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
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 42ea8030a9d832117a10feb6b937d05807033c91
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="dd628-102">Примеры синтаксиса запросов на основе методов. Отношения навигации</span><span class="sxs-lookup"><span data-stu-id="dd628-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="dd628-103">Свойства навигации в модели [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] - это свойства быстрого доступа, используемые для нахождения сущностей в элементах ассоциации.</span><span class="sxs-lookup"><span data-stu-id="dd628-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="dd628-104">Свойства навигации позволяют пользователю переходить от одной сущности к другой или от сущности к связанным сущностям в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="dd628-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="dd628-105">В этом разделе содержатся примеры синтаксиса запросов на основе методов для навигации по связям с помощью свойств навигации в запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd628-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="dd628-106">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="dd628-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="dd628-107">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="dd628-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="dd628-108">Пример</span><span class="sxs-lookup"><span data-stu-id="dd628-108">Example</span></span>  
 <span data-ttu-id="dd628-109">В следующем примере синтаксиса запроса на основе методов используется метод <xref:System.Linq.Queryable.SelectMany%2A>, чтобы получить все заказы контактных лиц с фамилией «Zhou».</span><span class="sxs-lookup"><span data-stu-id="dd628-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="dd628-110">Свойство навигации `Contact.SalesOrderHeader` используется для получения коллекции объектов `SalesOrderHeader` для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="dd628-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="dd628-111">Пример</span><span class="sxs-lookup"><span data-stu-id="dd628-111">Example</span></span>  
 <span data-ttu-id="dd628-112">В следующем примере синтаксиса запроса на основе методов используется метод <xref:System.Linq.Queryable.Select%2A>, чтобы получить все идентификаторы контактов и сумму заказа для каждого контактного лица с фамилией «Zhou».</span><span class="sxs-lookup"><span data-stu-id="dd628-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="dd628-113">Свойство навигации `Contact.SalesOrderHeader` используется для получения коллекции объектов `SalesOrderHeader` для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="dd628-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="dd628-114">Метод `Sum` использует свойство навигации `Contact.SalesOrderHeader` для получения суммы всех заказов для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="dd628-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="dd628-115">Пример</span><span class="sxs-lookup"><span data-stu-id="dd628-115">Example</span></span>  
 <span data-ttu-id="dd628-116">В следующем примере синтаксиса запроса на основе методов получаются все заказы контактных лиц с фамилией «Zhou».</span><span class="sxs-lookup"><span data-stu-id="dd628-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="dd628-117">Свойство навигации `Contact.SalesOrderHeader` используется для получения коллекции объектов `SalesOrderHeader` для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="dd628-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="dd628-118">Имя и заказы контактного лица возвращаются в анонимном типе.</span><span class="sxs-lookup"><span data-stu-id="dd628-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="dd628-119">Пример</span><span class="sxs-lookup"><span data-stu-id="dd628-119">Example</span></span>  
 <span data-ttu-id="dd628-120">В следующем примере свойства навигации `SalesOrderHeader.Address` и `SalesOrderHeader.Contact` используются, чтобы получить коллекцию объектов `Address` и `Contact`, связанных с каждым заказом.</span><span class="sxs-lookup"><span data-stu-id="dd628-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="dd628-121">Фамилия контактного лица, адрес, номер заказа на продажу и сумма заказа по каждому заказу в Сиэттле возвращаются в анонимном типе.</span><span class="sxs-lookup"><span data-stu-id="dd628-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="dd628-122">Пример</span><span class="sxs-lookup"><span data-stu-id="dd628-122">Example</span></span>  
 <span data-ttu-id="dd628-123">В следующем примере используется метод `Where` для нахождения заказов, сделанных после 1 декабря 2003 г. После этого с помощью свойства навигации `order.SalesOrderDetail` определяются подробности каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="dd628-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="dd628-124">См. также</span><span class="sxs-lookup"><span data-stu-id="dd628-124">See Also</span></span>  
 [<span data-ttu-id="dd628-125">Свойства навигации</span><span class="sxs-lookup"><span data-stu-id="dd628-125">Navigation Properties</span></span>](http://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
 [<span data-ttu-id="dd628-126">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="dd628-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
