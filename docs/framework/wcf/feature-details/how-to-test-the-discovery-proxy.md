---
title: Практическое руководство. Как проверить прокси-сервер обнаружения
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 13d2e8ca46e634e3b27c8eb967d89d860df1c72d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176284"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="95630-102">Практическое руководство. Как проверить прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="95630-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="95630-103">Это последний из четырех разделов, в которых демонстрируется реализация прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="95630-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="95630-104">В предыдущем разделе [как: Реализовать клиентское приложение, которое использует прокси-сервер обнаружения для поиска службы](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), было реализовано клиентское приложение WCF, которое использует прокси-сервер обнаружения для поиска служб, а затем вызывает службу.</span><span class="sxs-lookup"><span data-stu-id="95630-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="95630-105">В данном разделе показано, как проверить работу прокси-сервера обнаружения, службы и клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="95630-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="95630-106">Запуск прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="95630-106">Run the Discovery Proxy</span></span>  
  
1.  <span data-ttu-id="95630-107">Откройте командную строку от имени учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="95630-107">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="95630-108">Может появиться диалоговое окно с текстом: Брандмауэр Windows заблокировал некоторые из возможностей этой программы.</span><span class="sxs-lookup"><span data-stu-id="95630-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="95630-109">Если вы видите это сообщение, нажмите кнопку **Unblock** кнопки.</span><span class="sxs-lookup"><span data-stu-id="95630-109">If you see this message, click the **Unblock** button.</span></span>  
  
3.  <span data-ttu-id="95630-110">Запустите из командной строки прокси-сервер обнаружения DiscoveryProxy.exe.</span><span class="sxs-lookup"><span data-stu-id="95630-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4.  <span data-ttu-id="95630-111">Приложение должно вывести на экран сообщение: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="95630-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="95630-112">Запуск обнаруживаемой службы</span><span class="sxs-lookup"><span data-stu-id="95630-112">Run the Discoverable Service</span></span>  
  
1.  <span data-ttu-id="95630-113">Откройте командную строку от имени учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="95630-113">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="95630-114">Из командной строки запустите обнаруживаемую службу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="95630-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3.  <span data-ttu-id="95630-115">Программа DiscoveryProxy.exe должна вывести следующий текст: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="95630-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="95630-116">Запуск клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="95630-116">Run the Client Application</span></span>  
  
1.  <span data-ttu-id="95630-117">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="95630-117">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="95630-118">Из командной строки запустите приложение client.exe.</span><span class="sxs-lookup"><span data-stu-id="95630-118">Within the command prompt, run the client.exe application.</span></span>  
  
3.  <span data-ttu-id="95630-119">Через несколько секунд клиентское приложение выводит следующий текст: Подключение к [Service-Endpoint].</span><span class="sxs-lookup"><span data-stu-id="95630-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4.  <span data-ttu-id="95630-120">Service.exe должна затем вывести на экран сообщение: Приветствие получен запрос, я ответит.</span><span class="sxs-lookup"><span data-stu-id="95630-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5.  <span data-ttu-id="95630-121">Client.exe должно затем вывести на экран сообщение: Клиент Hello!</span><span class="sxs-lookup"><span data-stu-id="95630-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="95630-122">Завершение работы приложений</span><span class="sxs-lookup"><span data-stu-id="95630-122">Shut Down the Applications</span></span>  
  
1.  <span data-ttu-id="95630-123">Закройте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="95630-123">Shut down the client application.</span></span>  
  
2.  <span data-ttu-id="95630-124">Завершите работу службы.</span><span class="sxs-lookup"><span data-stu-id="95630-124">Shut down the service.</span></span> <span data-ttu-id="95630-125">Прокси-сервер обнаружения выведет на экран сообщение: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="95630-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3.  <span data-ttu-id="95630-126">Завершите работу прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="95630-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95630-127">См. также</span><span class="sxs-lookup"><span data-stu-id="95630-127">See also</span></span>

- [<span data-ttu-id="95630-128">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="95630-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="95630-129">Практическое руководство. Как реализовать прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="95630-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="95630-130">Практическое руководство. Как реализовать обнаружимую службу, которая регистрируется в прокси-сервере обнаружения</span><span class="sxs-lookup"><span data-stu-id="95630-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="95630-131">Практическое руководство. Как реализовать клиентское приложение, которое для поиска служб использует прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="95630-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
