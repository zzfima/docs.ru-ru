---
title: Перехватчики (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: 7decfdd738e71a01afa8cb32604953142b46e588
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790441"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="c23a0-102">Перехватчики (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="c23a0-102">Interceptors (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="c23a0-103">позволяет приложению перехватывать сообщения запроса, чтобы можно было добавить в операцию пользовательскую логику.</span><span class="sxs-lookup"><span data-stu-id="c23a0-103">enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="c23a0-104">Эту пользовательскую логику можно использовать для проверки данных во входящих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="c23a0-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="c23a0-105">Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.</span><span class="sxs-lookup"><span data-stu-id="c23a0-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="c23a0-106">Перехват выполняется методами службы данных со специальными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="c23a0-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="c23a0-107">Эти методы вызываются службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в соответствующие моменты обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="c23a0-107">These methods are called by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] at the appropriate point in message processing.</span></span> <span data-ttu-id="c23a0-108">Перехватчики определяются для каждого набора сущностей, и методы перехватчика не могут принимать параметры запроса, например операции службы.</span><span class="sxs-lookup"><span data-stu-id="c23a0-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="c23a0-109">Методы перехватчика запросов, которые вызываются при обработке HTTP-запроса GET, должны возвращать лямбда-выражение, определяющее, должен ли экземпляр набора сущностей перехватчика возвращаться в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="c23a0-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="c23a0-110">Это выражение используется службой данных для дальнейшего уточнения запрошенного действия.</span><span class="sxs-lookup"><span data-stu-id="c23a0-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="c23a0-111">В следующем примере рассмотрено определение перехватчика запроса.</span><span class="sxs-lookup"><span data-stu-id="c23a0-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="c23a0-112">Дополнительные сведения см. в разделе [Практическое руководство. Перехват сообщений](how-to-intercept-data-service-messages-wcf-data-services.md)службы данных.</span><span class="sxs-lookup"><span data-stu-id="c23a0-112">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="c23a0-113">Перехватчики изменений, которые вызываются при обработке операций, не связанных с запросами, должны возвращать значение `void` (`Nothing` в коде Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c23a0-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="c23a0-114">Методы перехватчика изменений должны принимать следующие два параметра.</span><span class="sxs-lookup"><span data-stu-id="c23a0-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1. <span data-ttu-id="c23a0-115">Параметр типа, совместимого с типом сущностей в наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="c23a0-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="c23a0-116">При вызове службой данных перехватчика изменений значение этого параметра будет отражать сведения о сущности, отправленные в запросе.</span><span class="sxs-lookup"><span data-stu-id="c23a0-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2. <span data-ttu-id="c23a0-117">Параметр типа <xref:System.Data.Services.UpdateOperations>.</span><span class="sxs-lookup"><span data-stu-id="c23a0-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="c23a0-118">При вызове службой данных перехватчика изменений значение этого параметра будет отражать операцию, которую пытается выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="c23a0-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="c23a0-119">В следующем примере рассмотрено определение перехватчика изменений.</span><span class="sxs-lookup"><span data-stu-id="c23a0-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="c23a0-120">Дополнительные сведения см. в разделе [Практическое руководство. Перехват сообщений](how-to-intercept-data-service-messages-wcf-data-services.md)службы данных.</span><span class="sxs-lookup"><span data-stu-id="c23a0-120">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="c23a0-121">Для перехватчиков поддерживаются следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="c23a0-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="c23a0-122">**[Куеринтерцептор (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="c23a0-122">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="c23a0-123">Методы с атрибутом <xref:System.Data.Services.QueryInterceptorAttribute> вызываются при получении запроса HTTP GET к целевому ресурсу набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="c23a0-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="c23a0-124">Эти методы всегда должны возвращать лямбда-выражение в форме `Expression<Func<T,bool>>`.</span><span class="sxs-lookup"><span data-stu-id="c23a0-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="c23a0-125">**[Чанжеинтерцептор (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="c23a0-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="c23a0-126">Методы с атрибутом <xref:System.Data.Services.ChangeInterceptorAttribute> вызываются при получении запроса HTTP, отличного от HTTP GET, к целевому ресурсу набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="c23a0-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="c23a0-127">Эти методы должны всегда возвращать значение `void` (`Nothing` в коде Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c23a0-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="c23a0-128">Дополнительные сведения см. в разделе [Практическое руководство. Перехват сообщений](how-to-intercept-data-service-messages-wcf-data-services.md)службы данных.</span><span class="sxs-lookup"><span data-stu-id="c23a0-128">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23a0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c23a0-129">See also</span></span>

- [<span data-ttu-id="c23a0-130">Операции служб</span><span class="sxs-lookup"><span data-stu-id="c23a0-130">Service Operations</span></span>](service-operations-wcf-data-services.md)
