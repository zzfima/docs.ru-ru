---
title: "Как проверить прокси-сервер обнаружения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55a7fe72b34fc8c099d921e7e295c184817825a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="a403e-102">Как проверить прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="a403e-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="a403e-103">Это последний из четырех разделов, в которых демонстрируется реализация прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a403e-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="a403e-104">В предыдущем разделе [как: реализовать клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), можно реализовать [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы, а затем вызывает Служба.</span><span class="sxs-lookup"><span data-stu-id="a403e-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="a403e-105">В данном разделе показано, как проверить работу прокси-сервера обнаружения, службы и клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="a403e-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="a403e-106">Запуск прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="a403e-106">Run the Discovery Proxy</span></span>  
  
1.  <span data-ttu-id="a403e-107">Откройте командную строку от имени учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="a403e-107">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="a403e-108">Может появиться диалоговое окно с сообщением «Брандмауэр Windows заблокировал некоторые из возможностей этой программы».</span><span class="sxs-lookup"><span data-stu-id="a403e-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="a403e-109">Если вы видите это сообщение, нажмите кнопку **Unblock** кнопки.</span><span class="sxs-lookup"><span data-stu-id="a403e-109">If you see this message, click the **Unblock** button.</span></span>  
  
3.  <span data-ttu-id="a403e-110">Запустите из командной строки прокси-сервер обнаружения DiscoveryProxy.exe.</span><span class="sxs-lookup"><span data-stu-id="a403e-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4.  <span data-ttu-id="a403e-111">Приложение должно вывести на экран сообщение: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="a403e-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="a403e-112">Запуск обнаруживаемой службы</span><span class="sxs-lookup"><span data-stu-id="a403e-112">Run the Discoverable Service</span></span>  
  
1.  <span data-ttu-id="a403e-113">Откройте командную строку от имени учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="a403e-113">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="a403e-114">Из командной строки запустите обнаруживаемую службу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="a403e-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3.  <span data-ttu-id="a403e-115">Программа DiscoveryProxy.exe должна вывести следующий текст: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="a403e-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="a403e-116">Запуск клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="a403e-116">Run the Client Application</span></span>  
  
1.  <span data-ttu-id="a403e-117">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="a403e-117">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="a403e-118">Из командной строки запустите приложение client.exe.</span><span class="sxs-lookup"><span data-stu-id="a403e-118">Within the command prompt, run the client.exe application.</span></span>  
  
3.  <span data-ttu-id="a403e-119">Через несколько секунд клиентское приложение выведет на экран сообщение: «Connecting to [Service-Endpoint]».</span><span class="sxs-lookup"><span data-stu-id="a403e-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4.  <span data-ttu-id="a403e-120">Программа service.exe должна затем вывести на экран сообщение: «Greeting request received, I will respond».</span><span class="sxs-lookup"><span data-stu-id="a403e-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5.  <span data-ttu-id="a403e-121">Приложение client.exe должно затем вывести на экран сообщение: «Hello Client!»</span><span class="sxs-lookup"><span data-stu-id="a403e-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="a403e-122">Завершение работы приложений</span><span class="sxs-lookup"><span data-stu-id="a403e-122">Shut Down the Applications</span></span>  
  
1.  <span data-ttu-id="a403e-123">Закройте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="a403e-123">Shut down the client application.</span></span>  
  
2.  <span data-ttu-id="a403e-124">Завершите работу службы.</span><span class="sxs-lookup"><span data-stu-id="a403e-124">Shut down the service.</span></span> <span data-ttu-id="a403e-125">Прокси-сервер обнаружения выведет на экран сообщение: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="a403e-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3.  <span data-ttu-id="a403e-126">Завершите работу прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a403e-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a403e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a403e-127">See Also</span></span>  
 [<span data-ttu-id="a403e-128">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="a403e-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="a403e-129">Как: реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="a403e-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [<span data-ttu-id="a403e-130">Как: реализовать Обнаружимую службу, которая регистрирует с прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="a403e-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [<span data-ttu-id="a403e-131">Как: реализовать клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы</span><span class="sxs-lookup"><span data-stu-id="a403e-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
