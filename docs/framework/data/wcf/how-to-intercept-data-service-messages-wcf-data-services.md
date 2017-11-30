---
title: "Практическое руководство. Перехват сообщений службы данных (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c18664eaa154fbc048c77cb359d0926f04b7e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="ab123-102">Практическое руководство. Перехват сообщений службы данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="ab123-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="ab123-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет приложению перехватывать сообщения запросов, что дает возможность добавить в операцию специализированную логику.</span><span class="sxs-lookup"><span data-stu-id="ab123-103">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="ab123-104">Для перехвата сообщений, можно использовать со специальными атрибутами методы в службе данных.</span><span class="sxs-lookup"><span data-stu-id="ab123-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="ab123-105">Дополнительные сведения см. в разделе [перехватчики](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ab123-105">For more information, see [Interceptors](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ab123-106">В примере этого раздела используется образец службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="ab123-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="ab123-107">Эта служба создается после завершения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ab123-107">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="ab123-108">Определение перехватчика запросов для набора сущностей Orders</span><span class="sxs-lookup"><span data-stu-id="ab123-108">To define a query interceptor for the Orders entity set</span></span>  
  
1.  <span data-ttu-id="ab123-109">Откройте в проекте службы данных Northwind файл Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="ab123-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="ab123-110">На странице кода класса `Northwind` добавьте следующую инструкцию `using` (`Imports` в коде Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="ab123-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  <span data-ttu-id="ab123-111">Определите в классе `Northwind` метод операции службы с именем `OnQueryOrders`, как показано дальше:</span><span class="sxs-lookup"><span data-stu-id="ab123-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="ab123-112">Определение перехватчика изменений для набора сущностей Products</span><span class="sxs-lookup"><span data-stu-id="ab123-112">To define a change interceptor for the Products entity set</span></span>  
  
1.  <span data-ttu-id="ab123-113">Откройте в проекте службы данных Northwind файл Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="ab123-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="ab123-114">Определите в классе `Northwind` метод операции службы с именем `OnChangeProducts`, как показано дальше:</span><span class="sxs-lookup"><span data-stu-id="ab123-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="ab123-115">Пример</span><span class="sxs-lookup"><span data-stu-id="ab123-115">Example</span></span>  
 <span data-ttu-id="ab123-116">Этот пример определяет метод перехватчика запросов для набора сущностей `Orders`, который возвращает лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="ab123-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="ab123-117">Это выражение содержит делегат, который фильтрует запрошенный набор сущностей `Orders` на основе связанных сущностей `Customers` с определенным именем контакта.</span><span class="sxs-lookup"><span data-stu-id="ab123-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="ab123-118">Имя в свою очередь определяется в зависимости от вызывающего пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab123-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="ab123-119">Пример предполагает, что служба данных размещена в веб-приложении ASP.NET, использующем WCF, и что проверка подлинности включена.</span><span class="sxs-lookup"><span data-stu-id="ab123-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="ab123-120">Класс <xref:System.Web.HttpContext> используется для извлечения участника текущего запроса.</span><span class="sxs-lookup"><span data-stu-id="ab123-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="ab123-121">Пример</span><span class="sxs-lookup"><span data-stu-id="ab123-121">Example</span></span>  
 <span data-ttu-id="ab123-122">Этот пример определяет метод перехватчика изменений для набора сущностей `Products`.</span><span class="sxs-lookup"><span data-stu-id="ab123-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="ab123-123">Метод проверяет входные данные службы для операции <xref:System.Data.Services.UpdateOperations.Add> или <xref:System.Data.Services.UpdateOperations.Change> и формирует исключение, если изменение производится над отсутствующим продуктом.</span><span class="sxs-lookup"><span data-stu-id="ab123-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="ab123-124">Кроме того, удаление продуктов блокируется как неподдерживаемая операция.</span><span class="sxs-lookup"><span data-stu-id="ab123-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="ab123-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ab123-125">See Also</span></span>  
 [<span data-ttu-id="ab123-126">Как: определение операции службы</span><span class="sxs-lookup"><span data-stu-id="ab123-126">How to: Define a Service Operation</span></span>](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)  
 [<span data-ttu-id="ab123-127">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ab123-127">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
