---
title: Интеграция кэширования ASP.NET
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 23c10e56dba7daec2d1027de92e8252c8fe69055
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716174"
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="183a4-102">Интеграция кэширования ASP.NET</span><span class="sxs-lookup"><span data-stu-id="183a4-102">ASP.NET Caching Integration</span></span>

<span data-ttu-id="183a4-103">В этом образце демонстрируется использование выходного кэша ASP.NET в модели веб-программирования WCF HTTP .</span><span class="sxs-lookup"><span data-stu-id="183a4-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="183a4-104">В этом разделе основное внимание уделено возможности интеграции выходного кэша ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="183a4-104">This topic focuses on the ASP.NET output cache integration feature.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="183a4-105">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="183a4-105">Demonstrates</span></span>

<span data-ttu-id="183a4-106">Интеграция с выходным кэшем ASP.NET</span><span class="sxs-lookup"><span data-stu-id="183a4-106">Integration with the ASP.NET Output Cache</span></span>

> [!IMPORTANT]
> <span data-ttu-id="183a4-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="183a4-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="183a4-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="183a4-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="183a4-109">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="183a4-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="183a4-110">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="183a4-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a><span data-ttu-id="183a4-111">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="183a4-111">Discussion</span></span>

<span data-ttu-id="183a4-112">В примере используется <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> для использования кэширования выходных данных ASP.NET со службой Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="183a4-112">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="183a4-113">Атрибут <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> применяется к операциям службы и предоставляет имя профиля кэша для файла конфигурации, который будет использован для ответов из заданной операции.</span><span class="sxs-lookup"><span data-stu-id="183a4-113">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>

<span data-ttu-id="183a4-114">В файле Service.cs примера проекта службы операции `GetCustomer` и `GetCustomers` помечаются <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, который предоставляет имя профиля кэша "CacheFor60Seconds".</span><span class="sxs-lookup"><span data-stu-id="183a4-114">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="183a4-115">В файле Web. config проекта службы профиль кэша "CacheFor60Seconds" предоставляется в элементе <`caching`> <`system.web`>.</span><span class="sxs-lookup"><span data-stu-id="183a4-115">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="183a4-116">Для этого профиля кэша значением атрибута `duration` является "60", поэтому ответы, связанные с этим профилем, кэшируются в кэше вывода ASP.NET в течение 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="183a4-116">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="183a4-117">Кроме того, для этого профиля кэша атрибуту `varmByParam` присваивается значение "Format", чтобы запросы с разными значениями для параметра строки запроса `format` были кэшированы отдельно.</span><span class="sxs-lookup"><span data-stu-id="183a4-117">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="183a4-118">Наконец, атрибуту `varyByHeader` профиля кэша присваивается значение Accept, поэтому ответы на запросы с разными значениями заголовков Accept кэшируются отдельно.</span><span class="sxs-lookup"><span data-stu-id="183a4-118">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>

<span data-ttu-id="183a4-119">В файле Program.cs из проекта «Клиент» показывается, как можно разработать клиент с помощью <xref:System.Net.HttpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="183a4-119">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="183a4-120">Заметьте, что это лишь один из способов доступа к WCF-службе.</span><span class="sxs-lookup"><span data-stu-id="183a4-120">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="183a4-121">Доступ к службе также можно получить с помощью других классов .NET Framework, таких как фабрика каналов WCF и <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="183a4-121">It is also possible to access the service using other .NET Framework classes like the WCF channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="183a4-122">Другие примеры в пакете SDK (например, образец [службы HTTP Basic](../../../../docs/framework/wcf/samples/basic-http-service.md) ) иллюстрируют использование этих классов для взаимодействия со службой WCF.</span><span class="sxs-lookup"><span data-stu-id="183a4-122">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample) illustrate how to use these classes to communicate with a WCF service.</span></span>

## <a name="to-run-the-sample"></a><span data-ttu-id="183a4-123">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="183a4-123">To run the sample</span></span>

<span data-ttu-id="183a4-124">Этот образец состоит из трех проектов.</span><span class="sxs-lookup"><span data-stu-id="183a4-124">The sample consists of three projects:</span></span>

- <span data-ttu-id="183a4-125">**Служба**: проект веб-приложения, который включает в себя службу HTTP WCF, размещенную в ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="183a4-125">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>

- <span data-ttu-id="183a4-126">**Клиент**: проект консольного приложения, который выполняет вызовы к службе.</span><span class="sxs-lookup"><span data-stu-id="183a4-126">**Client**: A console application project that makes calls to the service.</span></span>

- <span data-ttu-id="183a4-127">**Common**: Общая библиотека, содержащая тип клиента, используемый клиентом и службой.</span><span class="sxs-lookup"><span data-stu-id="183a4-127">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>

<span data-ttu-id="183a4-128">Во время выполнения клиентского консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.</span><span class="sxs-lookup"><span data-stu-id="183a4-128">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>

#### <a name="to-run-the-sample"></a><span data-ttu-id="183a4-129">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="183a4-129">To run the sample</span></span>

1. <span data-ttu-id="183a4-130">Откройте решение для образца ASP.NET Caching Integration.</span><span class="sxs-lookup"><span data-stu-id="183a4-130">Open the solution for the ASP.NET Caching Integration Sample.</span></span>

2. <span data-ttu-id="183a4-131">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="183a4-131">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="183a4-132">Если окно **Обозреватель решений** еще не открыто, нажмите клавиши CTRL + W + S.</span><span class="sxs-lookup"><span data-stu-id="183a4-132">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>

4. <span data-ttu-id="183a4-133">В окне **Обозреватель решений** щелкните правой кнопкой мыши проект **службы** и выберите команду **запустить новый экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="183a4-133">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="183a4-134">Запускается сервер разработки ASP.NET, на котором размещается служба.</span><span class="sxs-lookup"><span data-stu-id="183a4-134">This launches the ASP.NET development server, which hosts the service.</span></span>

5. <span data-ttu-id="183a4-135">В окне **Обозреватель решений** щелкните правой кнопкой мыши **клиентский** проект и выберите команду **запустить новый экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="183a4-135">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>

6. <span data-ttu-id="183a4-136">На клиенте открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы.</span><span class="sxs-lookup"><span data-stu-id="183a4-136">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="183a4-137">HTML-страницу справки можно просмотреть в любой момент времени, введя URI этой страницы в браузере.</span><span class="sxs-lookup"><span data-stu-id="183a4-137">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>

7. <span data-ttu-id="183a4-138">Во время работы образца клиент записывает состояние текущего действия.</span><span class="sxs-lookup"><span data-stu-id="183a4-138">As the sample runs, the client writes the status of the current activity.</span></span>

8. <span data-ttu-id="183a4-139">Чтобы завершить клиентское консольное приложение, нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="183a4-139">Press any key to terminate the client console application.</span></span>

9. <span data-ttu-id="183a4-140">Чтобы прекратить отладку службы, нажмите клавиши SHIFT+F5.</span><span class="sxs-lookup"><span data-stu-id="183a4-140">Press SHIFT+F5 to stop debugging the service.</span></span>

10. <span data-ttu-id="183a4-141">В области уведомлений Windows щелкните правой кнопкой мыши значок сервера ASP.NET Development Server и выберите пункт **прерывать**.</span><span class="sxs-lookup"><span data-stu-id="183a4-141">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
