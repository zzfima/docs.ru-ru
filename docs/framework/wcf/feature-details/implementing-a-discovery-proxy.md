---
title: "Реализация прокси-сервера обнаружения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ddea7bf69f697c5b9ecd9d41021bff2407522a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="5f647-102">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="5f647-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="5f647-103">В данном разделе приводятся инструкции по реализации прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5f647-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="5f647-104">Прокси-сервер обнаружения - это автономная служба, содержащая репозиторий служб.</span><span class="sxs-lookup"><span data-stu-id="5f647-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="5f647-105">Клиенты могут выполнять запросы к прокси-серверу обнаружения, чтобы найти обнаружимые службы, доступные серверу.</span><span class="sxs-lookup"><span data-stu-id="5f647-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="5f647-106">Метод заполнения прокси-сервера службами определяется разработчиком.</span><span class="sxs-lookup"><span data-stu-id="5f647-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="5f647-107">Например, прокси-сервер обнаружения может подключаться к существующему репозиторию служб и сделать эту информацию обнаружимой, администратор может при помощи API управления добавить обнаружимые службы к прокси-серверу, а прокси-сервер обнаружения может при помощи функции объявлений обновить свой внутренний кэш.</span><span class="sxs-lookup"><span data-stu-id="5f647-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="5f647-108">Реализация WCF обеспечивает базовые классы, которые позволят легко создавать прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="5f647-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="5f647-109">Эти API-интерфейсы можно использовать для создания прокси-сервера обнаружения поверх существующего репозитория.</span><span class="sxs-lookup"><span data-stu-id="5f647-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="5f647-110">Используемый здесь прокси-сервер обнаружения похож на любую другую службу WCF в том, что можно сделать прокси-сервер обнаруживаемым и позволить клиентам находить его конечные точки.</span><span class="sxs-lookup"><span data-stu-id="5f647-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f647-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="5f647-111">In This Section</span></span>  
 [<span data-ttu-id="5f647-112">Как: реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="5f647-112">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="5f647-113">Реализация прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5f647-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="5f647-114">Как: реализовать Обнаружимую службу, которая регистрирует с прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="5f647-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="5f647-115">Описано, как реализовать обнаружимую службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которая регистрируется в прокси-сервере обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5f647-115">Describes how to implement a discoverable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="5f647-116">Как: реализовать клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы</span><span class="sxs-lookup"><span data-stu-id="5f647-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="5f647-117">Описывает, как реализовать клиентское приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которое при помощи прокси-сервера обнаружения ищет службы.</span><span class="sxs-lookup"><span data-stu-id="5f647-117">Describes how to implement a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="5f647-118">Как: тестирования прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="5f647-118">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="5f647-119">Описывает, как проверить код, приведенный в предыдущих трех разделах.</span><span class="sxs-lookup"><span data-stu-id="5f647-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f647-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5f647-120">See Also</span></span>  
 [<span data-ttu-id="5f647-121">Обнаружение WCF</span><span class="sxs-lookup"><span data-stu-id="5f647-121">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
 [<span data-ttu-id="5f647-122">Как: программно добавить возможность обнаружения службы WCF и клиент</span><span class="sxs-lookup"><span data-stu-id="5f647-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
