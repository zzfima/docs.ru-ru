---
title: "Интеграция кэширования ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d56c435088be383821d17250e230cae848d2bab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="90816-102">Интеграция кэширования ASP.NET</span><span class="sxs-lookup"><span data-stu-id="90816-102">ASP.NET Caching Integration</span></span>
<span data-ttu-id="90816-103">В этом образце демонстрируется использование выходного кэша ASP.NET в модели веб-программирования WCF HTTP .</span><span class="sxs-lookup"><span data-stu-id="90816-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="90816-104">См. в разделе [базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образец резидентной версию этого сценария, которое обсуждается реализация service в глубину.</span><span class="sxs-lookup"><span data-stu-id="90816-104">Please see the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample for a self-hosted version of this scenario that discusses the service implementation in depth.</span></span> <span data-ttu-id="90816-105">В этом разделе основное внимание уделено возможности интеграции выходного кэша ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="90816-105">This topic focuses on the ASP.NET output cache integration feature.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="90816-106">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="90816-106">Demonstrates</span></span>  
 <span data-ttu-id="90816-107">Интеграция с выходным кэшем ASP.NET</span><span class="sxs-lookup"><span data-stu-id="90816-107">Integration with the ASP.NET Output Cache</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="90816-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="90816-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="90816-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="90816-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="90816-110">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90816-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="90816-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="90816-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a><span data-ttu-id="90816-112">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="90816-112">Discussion</span></span>  
 <span data-ttu-id="90816-113">В этом образце <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> используется вместе с выходным кэшем ASP.NET для службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90816-113">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="90816-114">Атрибут <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> применяется к операциям службы и предоставляет имя профиля кэша для файла конфигурации, который будет использован для ответов из заданной операции.</span><span class="sxs-lookup"><span data-stu-id="90816-114">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>  
  
 <span data-ttu-id="90816-115">В файле Service.cs из образца проекта Service как `GetCustomer` и `GetCustomers` операции с пометкой <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, который предоставляет имя профиля кэша «CacheFor60Seconds».</span><span class="sxs-lookup"><span data-stu-id="90816-115">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="90816-116">В файле Web.config проекта Service профиль кэша «CacheFor60Seconds» предоставляется в рамках <`caching`> элемента <`system.web`>.</span><span class="sxs-lookup"><span data-stu-id="90816-116">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="90816-117">Для этого профиля кэша значение `duration` атрибут является «60», поэтому ответы, связанные с этим профилем, кэшируются в кэше вывода ASP.NET в 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="90816-117">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="90816-118">Кроме того, для этого профиля кэша `varmByParam` атрибута задано значение «format» так запросы с разными значениями для `format` параметра строки запроса их ответы, кэшируются отдельно.</span><span class="sxs-lookup"><span data-stu-id="90816-118">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="90816-119">Наконец, профиля кэша `varyByHeader` атрибут имеет значение «Accept», поэтому запросы с другими значениями заголовка Accept кэшируются отдельно ответы.</span><span class="sxs-lookup"><span data-stu-id="90816-119">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>  
  
 <span data-ttu-id="90816-120">В файле Program.cs из проекта «Клиент» показывается, как можно разработать клиент с помощью <xref:System.Net.HttpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="90816-120">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="90816-121">Заметьте, что это лишь один из способов доступа к WCF-службе.</span><span class="sxs-lookup"><span data-stu-id="90816-121">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="90816-122">Также возможен доступ к службе с помощью других классов .NET Framework, например фабрики каналов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="90816-122">It is also possible to access the service using other .NET Framework classes like the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="90816-123">Другие примеры в пакете SDK (такие как [базовой службы HTTP](../../../../docs/framework/wcf/samples/basic-http-service.md) образца и [автоматический выбор формата](../../../../docs/framework/wcf/samples/automatic-format-selection.md) образец) показывают, как использовать эти классы для взаимодействия с [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы.</span><span class="sxs-lookup"><span data-stu-id="90816-123">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample and the [Automatic Format Selection](../../../../docs/framework/wcf/samples/automatic-format-selection.md) sample) illustrate how to use these classes to communicate with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
## <a name="to-run-the-sample"></a><span data-ttu-id="90816-124">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="90816-124">To run the sample</span></span>  
 <span data-ttu-id="90816-125">Этот образец состоит из трех проектов.</span><span class="sxs-lookup"><span data-stu-id="90816-125">The sample consists of three projects:</span></span>  
  
-   <span data-ttu-id="90816-126">**Служба**: проект веб-приложения, в который включена служба WCF HTTP, размещенная в ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="90816-126">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>  
  
-   <span data-ttu-id="90816-127">**Клиент**: проект консольного приложения, обращающийся к службе.</span><span class="sxs-lookup"><span data-stu-id="90816-127">**Client**: A console application project that makes calls to the service.</span></span>  
  
-   <span data-ttu-id="90816-128">**Общие**: общая библиотека, содержащая тип Customer, используемые клиентом и службой.</span><span class="sxs-lookup"><span data-stu-id="90816-128">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>  
  
 <span data-ttu-id="90816-129">Во время выполнения клиентского консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.</span><span class="sxs-lookup"><span data-stu-id="90816-129">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="90816-130">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="90816-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="90816-131">Откройте решение для образца ASP.NET Caching Integration.</span><span class="sxs-lookup"><span data-stu-id="90816-131">Open the solution for the ASP.NET Caching Integration Sample.</span></span>  
  
2.  <span data-ttu-id="90816-132">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="90816-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="90816-133">Если **обозревателе решений** окно еще не открыто, нажмите клавиши CTRL + W + S.</span><span class="sxs-lookup"><span data-stu-id="90816-133">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>  
  
4.  <span data-ttu-id="90816-134">Из **обозревателе решений** окна щелкните правой кнопкой мыши **службы** проект и выберите **запустить новый экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="90816-134">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="90816-135">Запускается сервер разработки ASP.NET, на котором размещается служба.</span><span class="sxs-lookup"><span data-stu-id="90816-135">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="90816-136">Из **обозревателе решений** окна щелкните правой кнопкой мыши **клиента** проект и выберите **запустить новый экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="90816-136">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="90816-137">На клиенте открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы.</span><span class="sxs-lookup"><span data-stu-id="90816-137">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="90816-138">HTML-страницу справки можно просмотреть в любой момент времени, введя URI этой страницы в браузере.</span><span class="sxs-lookup"><span data-stu-id="90816-138">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7.  <span data-ttu-id="90816-139">Во время работы образца клиент записывает состояние текущего действия.</span><span class="sxs-lookup"><span data-stu-id="90816-139">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8.  <span data-ttu-id="90816-140">Чтобы завершить клиентское консольное приложение, нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="90816-140">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="90816-141">Чтобы прекратить отладку службы, нажмите клавиши SHIFT+F5.</span><span class="sxs-lookup"><span data-stu-id="90816-141">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="90816-142">В области уведомлений Windows щелкните правой кнопкой мыши значок сервера разработки ASP.NET и выберите **остановить**.</span><span class="sxs-lookup"><span data-stu-id="90816-142">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
