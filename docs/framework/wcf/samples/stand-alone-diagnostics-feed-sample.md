---
title: "Пример автономного веб-канала диагностики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c95a2e1e1790633df77e7c4ecd6603e68321e478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="stand-alone-diagnostics-feed-sample"></a><span data-ttu-id="9fd66-102">Пример автономного веб-канала диагностики</span><span class="sxs-lookup"><span data-stu-id="9fd66-102">Stand-Alone Diagnostics Feed Sample</span></span>
<span data-ttu-id="9fd66-103">В этом примере показано, как создавать канал синдикации RSS/Atom с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fd66-103">This sample demonstrates how to create an RSS/Atom feed for syndication with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="9fd66-104">Это основная программа "Здравствуй, мир", которая демонстрирует основные возможности объектной модели и способы ее настройки для службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fd66-104">It is a basic "Hello World" program that shows the basics of the object model and how to set it up on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9fd66-105"> моделирует веб-каналы синдикации как операции службы, возвращающие особый тип данных, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="9fd66-105"> models syndication feeds as service operations that return a special data type, <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="9fd66-106">Экземпляры <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> могут сериализовать веб-канал в форматы RSS 2.0 и Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="9fd66-106">Instances of <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> can serialize a feed into both the RSS 2.0 and Atom 1.0 formats.</span></span> <span data-ttu-id="9fd66-107">В следующем примере кода показан использованный контракт.</span><span class="sxs-lookup"><span data-stu-id="9fd66-107">The following sample code shows the contract used.</span></span>  
  
```  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.   
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 <span data-ttu-id="9fd66-108">Операция `GetProcesses` аннотируется атрибутом <xref:System.ServiceModel.Web.WebGetAttribute>, который позволяет контролировать, как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет запросы HTTP GET в операции службы, и указывать формат отправляемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="9fd66-108">The `GetProcesses` operation is annotated with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute that enables you to control how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dispatches HTTP GET requests to service operations and specify the format of the messages sent.</span></span>  
  
 <span data-ttu-id="9fd66-109">Как и любая другая служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] веб-каналы синдикации могут быть резидентными для любого управляемого приложения.</span><span class="sxs-lookup"><span data-stu-id="9fd66-109">Like any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, syndication feeds can be self hosted in any managed application.</span></span> <span data-ttu-id="9fd66-110">Для правильной работы служб синдикации требуются особая привязка (<xref:System.ServiceModel.WebHttpBinding>) и специальное поведение конечной точки (<xref:System.ServiceModel.Description.WebHttpBehavior>).</span><span class="sxs-lookup"><span data-stu-id="9fd66-110">Syndication services require a specific binding (the <xref:System.ServiceModel.WebHttpBinding>) and a specific endpoint behavior (the <xref:System.ServiceModel.Description.WebHttpBehavior>) to function correctly.</span></span> <span data-ttu-id="9fd66-111">Новый класс <xref:System.ServiceModel.Web.WebServiceHost> обеспечивает удобный программный интерфейс для создания таких конечных точек без особой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9fd66-111">The new <xref:System.ServiceModel.Web.WebServiceHost> class provides a convenient API for creating such endpoints without specific configuration.</span></span>  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 <span data-ttu-id="9fd66-112">В качестве альтернативного варианта можно использовать <xref:System.ServiceModel.Activation.WebServiceHostFactory> из размещенного в службах IIS файла SVC, чтобы обеспечить аналогичную функциональность (этот метод не показан в примере коде).</span><span class="sxs-lookup"><span data-stu-id="9fd66-112">Alternatively, you can use <xref:System.ServiceModel.Activation.WebServiceHostFactory> from within an IIS-hosted .svc file to provide equivalent functionality (this technique is not demonstrated in this sample code).</span></span>  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 <span data-ttu-id="9fd66-113">Поскольку эта служба получает запросы с использованием стандартного метода HTTP GET, для доступа к службе можно использовать любой клиент, поддерживающий RSS или ATOM.</span><span class="sxs-lookup"><span data-stu-id="9fd66-113">Because this service receives requests using the standard HTTP GET, you can use any RSS or ATOM-aware client to access the service.</span></span> <span data-ttu-id="9fd66-114">Например, можно просмотреть выходные данные этой службы, перейдя по адресу http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss в таком браузере с поддержкой RSS, как Internet Explorer 7.</span><span class="sxs-lookup"><span data-stu-id="9fd66-114">For example, you can view the output of this service by navigating to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss in an RSS-aware browser such as Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="9fd66-115">Можно также использовать [как WCF синдикации объект модели сопоставляется Atom и RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) для чтения сводные данные и обработать его с помощью императивного кода.</span><span class="sxs-lookup"><span data-stu-id="9fd66-115">You can also use the [How the WCF Syndication Object Model Maps to Atom and RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) to read syndicated data and process it using imperative code.</span></span>  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9fd66-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="9fd66-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9fd66-117">Убедитесь, что разрешение регистрации правой адреса для HTTP и HTTPS на компьютере, как описано в set up инструкциям [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9fd66-117">Ensure that you have the right address registration permission for HTTP and HTTPS on the computer as explained in the set up instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9fd66-118">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="9fd66-118">Build the solution.</span></span>  
  
3.  <span data-ttu-id="9fd66-119">Запустите консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="9fd66-119">Run the console application.</span></span>  
  
4.  <span data-ttu-id="9fd66-120">Во время работы консольного приложения перейдите по адресу http://localhost:8000/diagnostics/feed/?format=atom или http://localhost:8000/diagnostics/feed/?format=rss с помощью браузера с поддержкой RSS.</span><span class="sxs-lookup"><span data-stu-id="9fd66-120">While the console application is running, navigate to http://localhost:8000/diagnostics/feed/?format=atom or http://localhost:8000/diagnostics/feed/?format=rss using an RSS-aware browser.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9fd66-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9fd66-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9fd66-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9fd66-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9fd66-123">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9fd66-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9fd66-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9fd66-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a><span data-ttu-id="9fd66-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9fd66-125">See Also</span></span>  
 [<span data-ttu-id="9fd66-126">Модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="9fd66-126">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="9fd66-127">Синдикации WCF</span><span class="sxs-lookup"><span data-stu-id="9fd66-127">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
