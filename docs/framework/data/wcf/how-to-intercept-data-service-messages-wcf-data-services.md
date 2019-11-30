---
title: Практическое руководство. Перехват сообщений службы данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 4f2d6cf34c820c60181d5287298898af5eb8d038
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569042"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="73a95-102">Практическое руководство. Перехват сообщений службы данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="73a95-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="73a95-103">С помощью WCF Data Services можно перехватывать сообщения запросов, чтобы можно было добавить в операцию пользовательскую логику.</span><span class="sxs-lookup"><span data-stu-id="73a95-103">With WCF Data Services, you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="73a95-104">Для перехвата сообщения используются методы с особыми атрибутами в службе данных.</span><span class="sxs-lookup"><span data-stu-id="73a95-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="73a95-105">Дополнительные сведения см. в разделе [перехватчики](interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="73a95-105">For more information, see [Interceptors](interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="73a95-106">В примере этого раздела используется образец службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="73a95-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="73a95-107">Эта служба создается при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="73a95-107">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="73a95-108">Определение перехватчика запросов для набора сущностей Orders</span><span class="sxs-lookup"><span data-stu-id="73a95-108">To define a query interceptor for the Orders entity set</span></span>  
  
1. <span data-ttu-id="73a95-109">Откройте в проекте службы данных Northwind файл Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="73a95-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="73a95-110">На странице кода класса `Northwind` добавьте следующую инструкцию `using` (`Imports` в коде Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="73a95-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. <span data-ttu-id="73a95-111">Определите в классе `Northwind` метод операции службы с именем `OnQueryOrders`, как показано дальше:</span><span class="sxs-lookup"><span data-stu-id="73a95-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="73a95-112">Определение перехватчика изменений для набора сущностей Products</span><span class="sxs-lookup"><span data-stu-id="73a95-112">To define a change interceptor for the Products entity set</span></span>  
  
1. <span data-ttu-id="73a95-113">Откройте в проекте службы данных Northwind файл Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="73a95-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="73a95-114">Определите в классе `Northwind` метод операции службы с именем `OnChangeProducts`, как показано дальше:</span><span class="sxs-lookup"><span data-stu-id="73a95-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="73a95-115">Пример</span><span class="sxs-lookup"><span data-stu-id="73a95-115">Example</span></span>  
 <span data-ttu-id="73a95-116">Этот пример определяет метод перехватчика запросов для набора сущностей `Orders`, который возвращает лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="73a95-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="73a95-117">Это выражение содержит делегат, который фильтрует запрошенный набор сущностей `Orders` на основе связанных сущностей `Customers` с определенным именем контакта.</span><span class="sxs-lookup"><span data-stu-id="73a95-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="73a95-118">Имя в свою очередь определяется в зависимости от вызывающего пользователя.</span><span class="sxs-lookup"><span data-stu-id="73a95-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="73a95-119">Пример предполагает, что служба данных размещена в веб-приложении ASP.NET, использующем WCF, и что проверка подлинности включена.</span><span class="sxs-lookup"><span data-stu-id="73a95-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="73a95-120">Класс <xref:System.Web.HttpContext> используется для извлечения участника текущего запроса.</span><span class="sxs-lookup"><span data-stu-id="73a95-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="73a95-121">Пример</span><span class="sxs-lookup"><span data-stu-id="73a95-121">Example</span></span>  
 <span data-ttu-id="73a95-122">Этот пример определяет метод перехватчика изменений для набора сущностей `Products`.</span><span class="sxs-lookup"><span data-stu-id="73a95-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="73a95-123">Метод проверяет входные данные службы для операции <xref:System.Data.Services.UpdateOperations.Add> или <xref:System.Data.Services.UpdateOperations.Change> и формирует исключение, если изменение производится над отсутствующим продуктом.</span><span class="sxs-lookup"><span data-stu-id="73a95-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="73a95-124">Кроме того, удаление продуктов блокируется как неподдерживаемая операция.</span><span class="sxs-lookup"><span data-stu-id="73a95-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="73a95-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="73a95-125">See also</span></span>

- [<span data-ttu-id="73a95-126">Практическое руководство. Определение операции службы</span><span class="sxs-lookup"><span data-stu-id="73a95-126">How to: Define a Service Operation</span></span>](how-to-define-a-service-operation-wcf-data-services.md)
- [<span data-ttu-id="73a95-127">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="73a95-127">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
