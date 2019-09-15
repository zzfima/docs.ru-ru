---
title: Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 6de32c798e7d0db5ad2d8f6666d6c5d1714250d5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991564"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a><span data-ttu-id="7fb56-102">Практическое руководство. Выбор между запросами HTTP POST и HTTP GET для конечных точек ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="7fb56-102">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>

<span data-ttu-id="7fb56-103">Windows Communication Foundation (WCF) позволяет создать службу, предоставляющую конечную точку с поддержкой AJAX ASP.NET, которая может быть вызвана из JavaScript на веб-сайте клиента.</span><span class="sxs-lookup"><span data-stu-id="7fb56-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="7fb56-104">Основные процедуры для создания таких служб обсуждаются в разделе [как: Используйте конфигурацию для добавления конечной точки](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) ASP.NET AJAX и [инструкций: Добавьте конечную точку ASP.NET AJAX без использования](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fb56-104">The basic procedures for building such services is discussed in [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) and [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
 <span data-ttu-id="7fb56-105">ASP.NET AJAX поддерживает операции, которые используют команды HTTP POST и HTTP GET (команда HTTP POST задана по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7fb56-105">ASP.NET AJAX supports operations that use the HTTP POST and HTTP GET verbs, with HTTP POST being the default.</span></span> <span data-ttu-id="7fb56-106">При создании операции, не имеющей побочных эффектов и возвращающей данные, которые меняются очень редко или не меняются никогда, необходимо вместо команды по умолчанию использовать HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="7fb56-106">When creating an operation that has no side effects and returns data that rarely or never changes, use HTTP GET instead.</span></span> <span data-ttu-id="7fb56-107">Результаты операций GET можно кэшировать, чтобы представить несколько вызовов одной операции в виде одного запроса службе.</span><span class="sxs-lookup"><span data-stu-id="7fb56-107">Results of GET operations can be cached, which means that multiple calls to the same operation may result in only one request to your service.</span></span> <span data-ttu-id="7fb56-108">Это кэширование не выполняется WCF, но может выполняться на любом уровне (в браузере пользователя, на прокси-сервере и на других уровнях). Кэширование обладает значительными преимуществами, если необходимо повысить производительность службы, но оказывается неприемлемым, если данные часто изменяются или операция выполняет какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="7fb56-108">The caching is not done by WCF but can take place at any level (in a user's browser, on a proxy server, and other levels.) Caching is advantageous if you want to increase service performance, but may not be acceptable if data changes frequently or if the operation performs some action.</span></span>  
  
 <span data-ttu-id="7fb56-109">Например, при создании службы для управления музыкальной библиотекой пользователя операция, осуществляющая поиск исполнителя по названию альбома, должна использовать команду GET, а операция, добавляющая альбом в личную коллекцию пользователя - команду POST.</span><span class="sxs-lookup"><span data-stu-id="7fb56-109">For example, if you are designing service to manage a user's music library, an operation that looks up the artist based on an album's title benefits from using GET, but an operation that adds an album to the user's personal collection must use POST.</span></span>  
  
 <span data-ttu-id="7fb56-110">Для управления временем существования кэша следует использовать тип <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span><span class="sxs-lookup"><span data-stu-id="7fb56-110">To control the lifetime of the cache, use the <xref:System.ServiceModel.Web.OutgoingWebResponseContext> type.</span></span> <span data-ttu-id="7fb56-111">Например, при создании службы, возвращающей ежечасно обновляемые прогнозы погоды, логично использовать команду GET, ограничив длительность кэширования одним часом (или меньшим промежутком времени), чтобы пользователи службы не имели доступа к устаревшим данным.</span><span class="sxs-lookup"><span data-stu-id="7fb56-111">For example, when designing a service that returns weather forecasts updated hourly, you would use GET but limit the cache duration to an hour or less to prevent the users of the service from accessing stale data.</span></span>  
  
 <span data-ttu-id="7fb56-112">При работе со службами со страницы ASP.NET AJAX, которые используют средство управления диспетчера скриптов, не имеет значения, использует ли операция команду GET или POST, так как механизм диспетчера скриптов обеспечивает выдачу правильного типа запроса.</span><span class="sxs-lookup"><span data-stu-id="7fb56-112">When using services from an ASP.NET AJAX page that use the Script Manager control, it makes no difference whether the operation uses GET or POST - the script manager mechanism ensures that the correct request type is issued.</span></span>  
  
 <span data-ttu-id="7fb56-113">Операции HTTP GET используют любые входные параметры, поддерживаемые операциями POST, включая сложные типы контрактов данных.</span><span class="sxs-lookup"><span data-stu-id="7fb56-113">HTTP GET operations use any input parameters supported by POST operations, including complex data contract types.</span></span> <span data-ttu-id="7fb56-114">Однако в большинстве случаев в операциях GET не рекомендуется использовать слишком много параметров или слишком сложные параметры, так как это снижает эффективность кэширования.</span><span class="sxs-lookup"><span data-stu-id="7fb56-114">However, in most cases it is recommended to avoid too many parameters or parameters that are too complex in GET operations because it reduces caching efficiency.</span></span>  
  
 <span data-ttu-id="7fb56-115">В этом разделе также объясняется, как выбрать между командами GET и POST, добавив в соответствующие операции в контракте службы атрибуты <xref:System.ServiceModel.Web.WebGetAttribute> или <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7fb56-115">This topic demonstrates how to select between GET and POST by adding the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to the relevant operations in the service contract.</span></span> <span data-ttu-id="7fb56-116">Другие действия (для реализации, настройки и размещения службы), необходимые для запуска службы, похожи на те, которые используются любой службой ASP.NET AJAX в WCF.</span><span class="sxs-lookup"><span data-stu-id="7fb56-116">The other steps (to implement, configure and host the service) that are required to get the service running are similar to those used by any ASP.NET AJAX service in WCF.</span></span>  
  
 <span data-ttu-id="7fb56-117">Операция, помеченная атрибутом <xref:System.ServiceModel.Web.WebGetAttribute>, всегда использует запрос GET.</span><span class="sxs-lookup"><span data-stu-id="7fb56-117">An operation marked with the <xref:System.ServiceModel.Web.WebGetAttribute> always uses a GET request.</span></span> <span data-ttu-id="7fb56-118">Операция, помеченная атрибутом <xref:System.ServiceModel.Web.WebInvokeAttribute> или не помеченная ни одним из двух атрибутов, использует запрос POST.</span><span class="sxs-lookup"><span data-stu-id="7fb56-118">An operation marked with the <xref:System.ServiceModel.Web.WebInvokeAttribute>, or not marked with any of the two attributes, uses a POST request.</span></span> <span data-ttu-id="7fb56-119">Атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> позволяет использовать другие HTTP-команды (кроме GET и POST, например PUT и DELETE) через свойство <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fb56-119">The <xref:System.ServiceModel.Web.WebInvokeAttribute> allows the use of other HTTP verbs, other than GET and POST (such as PUT and DELETE) through the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span> <span data-ttu-id="7fb56-120">Однако эти команды не поддерживаются ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="7fb56-120">However, these verbs are not supported by ASP.NET AJAX.</span></span> <span data-ttu-id="7fb56-121">Если планируется использовать службу со страниц ASP.NET с помощью средства управления диспетчера скриптов, применять свойство <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> не следует.</span><span class="sxs-lookup"><span data-stu-id="7fb56-121">If you intend to use the service from ASP.NET pages using the Script Manager control, do not use the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span>  
  
 <span data-ttu-id="7fb56-122">Рабочий пример переключения на получение см. в разделе пример [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) .</span><span class="sxs-lookup"><span data-stu-id="7fb56-122">For a working example of switching to GET, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="7fb56-123">Пример, в котором используется POST, см. в разделе [Служба AJAX с примером HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) .</span><span class="sxs-lookup"><span data-stu-id="7fb56-123">For a sample that uses POST, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a><span data-ttu-id="7fb56-124">Создание службы WCF, отвечающей на запросы HTTP GET или HTTP POST</span><span class="sxs-lookup"><span data-stu-id="7fb56-124">To create a WCF service that responds to HTTP GET or HTTP POST requests</span></span>
  
1. <span data-ttu-id="7fb56-125">Определите базовый контракт службы WCF с интерфейсом, <xref:System.ServiceModel.ServiceContractAttribute> помеченным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="7fb56-125">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="7fb56-126">Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7fb56-126">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="7fb56-127">Добавьте атрибут <xref:System.ServiceModel.Web.WebGetAttribute>, чтобы указать, что операция должна отвечать на запросы HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="7fb56-127">Add the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to stipulate that an operation should respond to HTTP GET requests.</span></span> <span data-ttu-id="7fb56-128">Также можно использовать атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>, чтобы явно задать HTTP POST, либо не указывать атрибут, и в этом случае по умолчанию будет использоваться HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="7fb56-128">You can also add the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute to explicitly specify HTTP POST, or not specify an attribute, which defaults to HTTP POST.</span></span>
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="7fb56-129">Реализуйте контракт службы `IMusicService` с помощью класса `MusicService`.</span><span class="sxs-lookup"><span data-stu-id="7fb56-129">Implement the `IMusicService` service contract with a `MusicService`.</span></span>
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. <span data-ttu-id="7fb56-130">Создайте в приложении новый файл с именем "service" и расширением .svc.</span><span class="sxs-lookup"><span data-stu-id="7fb56-130">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="7fb56-131">Измените этот файл, добавив соответствующие [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) сведения об директиве ServiceHost для службы.</span><span class="sxs-lookup"><span data-stu-id="7fb56-131">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="7fb56-132">Укажите, что <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> [ \@класс](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) должен использоваться в директиве ServiceHost для автоматической настройки конечной точки ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="7fb56-132">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a><span data-ttu-id="7fb56-133">Вызов службы</span><span class="sxs-lookup"><span data-stu-id="7fb56-133">To call the service</span></span>  
  
1. <span data-ttu-id="7fb56-134">Протестировать операции GET службы можно без кода клиента с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="7fb56-134">You can test your service's GET operations without any client code, by using the browser.</span></span> <span data-ttu-id="7fb56-135">Например, если служба настроена по `http://example.com/service.svc` адресу, то при вводе `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` в адресную строку браузера вызывается служба и вызывается Загрузка или отображение ответа.</span><span class="sxs-lookup"><span data-stu-id="7fb56-135">For example, if your service is configured at the `http://example.com/service.svc` address, then typing `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` into the browser address bar invokes the service and causes the response to be downloaded or displayed.</span></span>
  
2. <span data-ttu-id="7fb56-136">Службы с операциями GET можно использовать так же, как и любые другие службы ASP.NET AJAX, т. е. введя URL-адрес службы в коллекцию скриптов средства управления диспетчера скриптов ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="7fb56-136">You can use services with GET operations in the same way as any other ASP.NET AJAX services - by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="7fb56-137">Пример см. в разделе [базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md).</span><span class="sxs-lookup"><span data-stu-id="7fb56-137">For an example, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7fb56-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7fb56-138">See also</span></span>

- [<span data-ttu-id="7fb56-139">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="7fb56-139">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="7fb56-140">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX в WCF</span><span class="sxs-lookup"><span data-stu-id="7fb56-140">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
