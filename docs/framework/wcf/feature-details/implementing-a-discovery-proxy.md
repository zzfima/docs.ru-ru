---
title: Реализация прокси-сервера обнаружения
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 5d9296d8ba70d4c9e8d8339fa3a032d9c4c62826
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047065"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="064b6-102">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="064b6-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="064b6-103">В данном разделе приводятся инструкции по реализации прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="064b6-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="064b6-104">Прокси-сервер обнаружения - это автономная служба, содержащая репозиторий служб.</span><span class="sxs-lookup"><span data-stu-id="064b6-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="064b6-105">Клиенты могут выполнять запросы к прокси-серверу обнаружения, чтобы найти обнаружимые службы, доступные серверу.</span><span class="sxs-lookup"><span data-stu-id="064b6-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="064b6-106">Метод заполнения прокси-сервера службами определяется разработчиком.</span><span class="sxs-lookup"><span data-stu-id="064b6-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="064b6-107">Например, прокси-сервер обнаружения может подключаться к существующему репозиторию служб и сделать эту информацию обнаружимой, администратор может при помощи API управления добавить обнаружимые службы к прокси-серверу, а прокси-сервер обнаружения может при помощи функции объявлений обновить свой внутренний кэш.</span><span class="sxs-lookup"><span data-stu-id="064b6-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="064b6-108">Реализация WCF обеспечивает базовые классы, которые позволят легко создавать прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="064b6-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="064b6-109">Эти API-интерфейсы можно использовать для создания прокси-сервера обнаружения поверх существующего репозитория.</span><span class="sxs-lookup"><span data-stu-id="064b6-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="064b6-110">Используемый здесь прокси-сервер обнаружения похож на любую другую службу WCF в том, что можно сделать прокси-сервер обнаруживаемым и позволить клиентам находить его конечные точки.</span><span class="sxs-lookup"><span data-stu-id="064b6-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="064b6-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="064b6-111">In This Section</span></span>  
 [<span data-ttu-id="064b6-112">Практическое руководство. Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="064b6-112">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="064b6-113">Реализация прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="064b6-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="064b6-114">Практическое руководство. Реализовать Обнаружимую службу, которая регистрируется на прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="064b6-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="064b6-115">В этой статье описывается реализация обнаруживаемой службы WCF, которая регистрируется на прокси-сервер обнаружения.</span><span class="sxs-lookup"><span data-stu-id="064b6-115">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="064b6-116">Практическое руководство. Реализовать клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы</span><span class="sxs-lookup"><span data-stu-id="064b6-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="064b6-117">Описывает, как реализовать клиентское приложение WCF, которое использует прокси-сервер обнаружения для поиска службы.</span><span class="sxs-lookup"><span data-stu-id="064b6-117">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="064b6-118">Практическое руководство. Проверить прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="064b6-118">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="064b6-119">Описывает, как проверить код, приведенный в предыдущих трех разделах.</span><span class="sxs-lookup"><span data-stu-id="064b6-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="064b6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="064b6-120">See also</span></span>

- [<span data-ttu-id="064b6-121">Обнаружение WCF</span><span class="sxs-lookup"><span data-stu-id="064b6-121">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)
- [<span data-ttu-id="064b6-122">Практическое руководство. Программно добавьте возможность обнаружения к службе и клиенту WCF</span><span class="sxs-lookup"><span data-stu-id="064b6-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
