---
title: Введение в маршрутизацию
ms.date: 03/30/2017
ms.assetid: bf6ceb38-6622-433b-9ee7-f79bc93497a1
ms.openlocfilehash: d0f07d0dd171de428f7d556d84dfda04e35880b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158682"
---
# <a name="routing-introduction"></a><span data-ttu-id="654d4-102">Введение в маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="654d4-102">Routing Introduction</span></span>
<span data-ttu-id="654d4-103">Служба маршрутизации реализует универсальный расширяемый SOAP-посредник, маршрутизирующий сообщения с использованием их содержимого.</span><span class="sxs-lookup"><span data-stu-id="654d4-103">The Routing Service provides a generic pluggable SOAP intermediary that is capable of routing messages based on message content.</span></span> <span data-ttu-id="654d4-104">Эта служба позволяет создавать сложные алгоритмы маршрутизации для реализации сценариев объединения служб, управления версиями, управления приоритетами и многоадресной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-104">With the Routing Service, you can create complex routing logic that allows you to implement scenarios such as service aggregation, service versioning, priority routing, and multicast routing.</span></span> <span data-ttu-id="654d4-105">Функция обработки ошибок службы маршрутизации позволяет создавать списки резервных конечных точек (сообщения отправляются в резервные конечные точки в случае сбоя при отправке в основную целевую конечную точку).</span><span class="sxs-lookup"><span data-stu-id="654d4-105">The Routing Service also provides error handling that allows you to set up lists of backup endpoints, to which messages are sent if a failure occurs when sending to the primary destination endpoint.</span></span>  
  
 <span data-ttu-id="654d4-106">Данный раздел предназначен для тех, кто впервые знакомится со службой маршрутизации. В разделе приведены базовые сведения о конфигурации и размещении службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-106">This topic is intended for those new to the Routing Service and covers basic configuration and hosting of the Routing Service.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="654d4-107">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="654d4-107">Configuration</span></span>  
 <span data-ttu-id="654d4-108">Служба маршрутизация представляет собой службу WCF, которая обнаруживает одну или несколько конечных точек службы, получающих сообщения от клиентских приложений и перенаправляющих их в одну или несколько целевых конечных точек.</span><span class="sxs-lookup"><span data-stu-id="654d4-108">The Routing Service is implemented as a WCF service that exposes one or more service endpoints that receive messages from client applications and route the messages to one or more destination endpoints.</span></span> <span data-ttu-id="654d4-109">Эта служба предоставляет поведение <xref:System.ServiceModel.Routing.RoutingBehavior>, которое применяется к обнаруженным конечным точкам службы.</span><span class="sxs-lookup"><span data-stu-id="654d4-109">The service provides a <xref:System.ServiceModel.Routing.RoutingBehavior>, which is applied to the service endpoints exposed by the service.</span></span> <span data-ttu-id="654d4-110">Это поведение используется для настройки различных аспектов работы службы.</span><span class="sxs-lookup"><span data-stu-id="654d4-110">This behavior is used to configure various aspects of how the service operates.</span></span> <span data-ttu-id="654d4-111">Для упрощения настройки с помощью файла конфигурации, параметры указываются в **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="654d4-111">For ease of configuration when using a configuration file, the parameters are specified on the **RoutingBehavior**.</span></span> <span data-ttu-id="654d4-112">В сценариях на основе кода, эти параметры указываются как часть <xref:System.ServiceModel.Routing.RoutingConfiguration> объект, который может быть передан **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="654d4-112">In code-based scenarios, these parameters would be specified as part of a <xref:System.ServiceModel.Routing.RoutingConfiguration> object, which can then be passed to a **RoutingBehavior**.</span></span>  
  
 <span data-ttu-id="654d4-113">При запуске этого поведения к клиентским конечным точкам добавляется параметр <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, который используется для обработки сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="654d4-113">When starting, this behavior adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, which is used to perform SOAP processing of messages, to the client endpoints.</span></span> <span data-ttu-id="654d4-114">Данное значение позволяет службе маршрутизации для передачи сообщений в конечные точки, требующие **MessageVersion** чем конечная точка, через которую было получено сообщение.</span><span class="sxs-lookup"><span data-stu-id="654d4-114">This allows the Routing Service to transmit messages to endpoints that require a different **MessageVersion** than the endpoint the message was received over.</span></span> <span data-ttu-id="654d4-115">**RoutingBehavior** также регистрирует расширение службы <xref:System.ServiceModel.Routing.RoutingExtension>, который предоставляет точку доступа для изменения конфигурации службы маршрутизации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="654d4-115">The **RoutingBehavior** also registers a service extension, the <xref:System.ServiceModel.Routing.RoutingExtension>, which provides an accessibility point for modifying the Routing Service configuration at run time.</span></span>  
  
 <span data-ttu-id="654d4-116">**RoutingConfiguration** класс позволяет согласованным образом настраивать и обновлять конфигурацию службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-116">The **RoutingConfiguration** class provides a consistent means of configuring and updating the configuration of the Routing Service.</span></span>  <span data-ttu-id="654d4-117">Оно содержит параметры, которые действуют как параметры для службы маршрутизации и используется для настройки **RoutingBehavior** при запуске службы, или передается **RoutingExtension** для изменения маршрутизации конфигурации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="654d4-117">It contains parameters that act as the settings for the Routing Service and is used to configure the **RoutingBehavior** when the service starts, or is passed to the **RoutingExtension** to modify routing configuration at run time.</span></span>  
  
 <span data-ttu-id="654d4-118">Логика маршрутизации на основе содержимого определяется путем группирования нескольких объектов <xref:System.ServiceModel.Dispatcher.MessageFilter> в таблицы фильтрации (объекты <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>).</span><span class="sxs-lookup"><span data-stu-id="654d4-118">The routing logic used to perform content-based routing of messages is defined by grouping multiple <xref:System.ServiceModel.Dispatcher.MessageFilter> objects together into filter tables (<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> objects).</span></span> <span data-ttu-id="654d4-119">Входящие сообщения анализируются с использованием фильтров сообщений, содержащихся в таблице фильтров, а также для каждого **MessageFilter** , соответствующий сообщения, передаваемые для целевой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="654d4-119">Incoming messages are evaluated against the message filters contained in the filter table, and for each **MessageFilter** that matches the message, forwarded to a destination endpoint.</span></span> <span data-ttu-id="654d4-120">Таблица фильтров, который должен использоваться для маршрутизации сообщений задается с помощью либо **RoutingBehavior** в конфигурации или посредством кода с помощью **RoutingConfiguration** объекта.</span><span class="sxs-lookup"><span data-stu-id="654d4-120">The filter table that should be used to route messages is specified by using either the **RoutingBehavior** in configuration or through code by using the **RoutingConfiguration** object.</span></span>  
  
### <a name="defining-endpoints"></a><span data-ttu-id="654d4-121">Определение конечных точек</span><span class="sxs-lookup"><span data-stu-id="654d4-121">Defining Endpoints</span></span>  
 <span data-ttu-id="654d4-122">Кажется логичным, что начинать настройку нужно с определения используемой логики маршрутизации. Тем не менее, сперва нужно задать форму конечных точек, куда будут перенаправляться сообщения.</span><span class="sxs-lookup"><span data-stu-id="654d4-122">While it may seem that you should start your configuration by defining the routing logic you will use, your first step should actually be to determine the shape of the endpoints you will be routing messages to.</span></span> <span data-ttu-id="654d4-123">Служба маршрутизации использует контракты, определяющие форму каналов, которые будут использованы для получения и отправки сообщений. Форма входящего канала должна соответствовать форме исходящего канала.</span><span class="sxs-lookup"><span data-stu-id="654d4-123">The Routing Service uses contracts that define the shape of the channels used to receive and send messages, and therefore the shape of the input channel must match that of the output channel.</span></span>  <span data-ttu-id="654d4-124">Если маршрутизация выполняется в точки, использующие форму канала «запрос-ответ», необходимо использовать совместимый контракт для входящих конечных точек (например, <xref:System.ServiceModel.Routing.IRequestReplyRouter>).</span><span class="sxs-lookup"><span data-stu-id="654d4-124">For example, if you are routing to endpoints that use the request-reply channel shape, then you must use a compatible contract on the inbound endpoints, such as the <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span></span>  
  
 <span data-ttu-id="654d4-125">Это означает, что если целевые конечные точки используют контракты с несколькими шаблонами взаимодействия (например со смешением односторонних и двусторонних операций), нельзя создать единую конечную точку службы, которая могла бы принимать и перенаправлять сообщения во все целевые точки.</span><span class="sxs-lookup"><span data-stu-id="654d4-125">This means that if your destination endpoints use contracts with multiple communication patterns (such as mixing one-way and two-way operations,) you cannot create a single service endpoint that can receive and route messages to all of them.</span></span> <span data-ttu-id="654d4-126">Нужно понять, какие конечные точки имеют совместимые формы, и определить одну или несколько конечных точек службы, предназначенных для получения сообщений, которые будут перенаправлены в целевые конечные точки.</span><span class="sxs-lookup"><span data-stu-id="654d4-126">You must determine which endpoints have compatible shapes and define one or more service endpoints that will be used to receive messages to be routed to the destination endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="654d4-127">При работе с контрактами, задействующими несколько шаблонов взаимодействия (например со смешением односторонних и двусторонних операций), правильным решением будет использование в службе маршрутизации дуплексного контракта (например <xref:System.ServiceModel.Routing.IDuplexSessionRouter>).</span><span class="sxs-lookup"><span data-stu-id="654d4-127">When working with contracts that specify multiple communication patterns (such as a mix of one-way and two-way operations,) a workaround is to use a duplex contract at the Routing Service such as <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span></span> <span data-ttu-id="654d4-128">Это значит, что привязка должна быть совместима с дуплексным взаимодействием, однако это неприменимо ко всем сценариям.</span><span class="sxs-lookup"><span data-stu-id="654d4-128">However this means that the binding must be capable of duplex communication, which may not be possible for all scenarios.</span></span> <span data-ttu-id="654d4-129">В сценариях, для которых это неприменимо, может понадобиться разбиение модели взаимодействия на несколько конечных точек либо изменение приложения.</span><span class="sxs-lookup"><span data-stu-id="654d4-129">In scenarios where this is not possible, factoring the communication into multiple endpoints or modifying the application may be necessary.</span></span>  
  
 <span data-ttu-id="654d4-130">Дополнительные сведения о контрактах маршрутизации см. в разделе [контракты маршрутизации](routing-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="654d4-130">For more information about routing contracts, see [Routing Contracts](routing-contracts.md).</span></span>  
  
 <span data-ttu-id="654d4-131">После определения конечной точки службы можно использовать **RoutingBehavior** для связывания конкретной **RoutingConfiguration** с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="654d4-131">After the service endpoint is defined, you can use the **RoutingBehavior** to associate a specific **RoutingConfiguration** with the endpoint.</span></span> <span data-ttu-id="654d4-132">При настройке службы маршрутизации с помощью файла конфигурации, **RoutingBehavior** используется для указания фильтра таблицы, содержащей логику маршрутизации, используемый для обработки сообщений, получаемых этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="654d4-132">When configuring the Routing Service by using a configuration file, the **RoutingBehavior** is used to specify the filter table that contains the routing logic used to process messages received on this endpoint.</span></span> <span data-ttu-id="654d4-133">При настройке службы маршрутизации программными средствами можно указать в таблицу фильтров с помощью **RoutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="654d4-133">If you are configuring the Routing Service programmatically you can specify the filter table by using the **RoutingConfiguration**.</span></span>  
  
 <span data-ttu-id="654d4-134">В следующем примере показано, как определять клиентские конечные точки для службы маршрутизации (как с использованием файла конфигурации, так и с помощью программного кода).</span><span class="sxs-lookup"><span data-stu-id="654d4-134">The following example defines the service and client endpoints that are used by the Routing Service both programmatically and by using a configuration file.</span></span>  
  
```xml  
    <services>  
      <!--ROUTING SERVICE -->  
      <service behaviorConfiguration="routingData"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/routingservice/router"/>  
          </baseAddresses>  
        </host>  
        <!-- Define the service endpoints that are receive messages -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  name="reqReplyEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="routingData">  
          <serviceMetadata httpGetEnabled="True"/>  
          <!-- Add the RoutingBehavior and specify the Routing Table to use -->  
          <routing filterTableName="routingTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <client>  
    <!-- Define the client endpoint(s) to route messages to -->  
      <endpoint name="CalculatorService"  
                address="http://localhost:8000/servicemodelsamples/service"  
                binding="wsHttpBinding" contract="*" />  
    </client>  
```  
  
```csharp  
//set up some communication defaults  
string clientAddress = "http://localhost:8000/servicemodelsamples/service";  
string routerAddress = "http://localhost:8000/routingservice/router";  
Binding routerBinding = new WSHttpBinding();  
Binding clientBinding = new WSHttpBinding();  
//add the endpoint the router uses to receive messages  
serviceHost.AddServiceEndpoint(  
     typeof(IRequestReplyRouter),   
     routerBinding,   
     routerAddress);  
//create the client endpoint the router routes messages to  
ContractDescription contract = ContractDescription.GetContract(  
     typeof(IRequestReplyRouter));  
ServiceEndpoint client = new ServiceEndpoint(  
     contract,   
     clientBinding,   
     new EndpointAddress(clientAddress));  
//create a new routing configuration object  
RoutingConfiguration rc = new RoutingConfiguration();  
….  
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);  
//attach the behavior to the service host  
serviceHost.Description.Behaviors.Add(  
     new RoutingBehavior(rc));  
```  
  
 <span data-ttu-id="654d4-135">В этом примере настраивается служба маршрутизации будет единственной конечной точки с адресом `http://localhost:8000/routingservice/router`, который используется для получения сообщений для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-135">This example configures the Routing Service to expose a single endpoint with an address of `http://localhost:8000/routingservice/router`, which is used to receive messages to be routed.</span></span> <span data-ttu-id="654d4-136">Сообщения перенаправляются в конечные точки типа «запрос-ответ», поэтому конечная точка службы использует контракт <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="654d4-136">Because the messages are routed to request-reply endpoints, the service endpoint uses the <xref:System.ServiceModel.Routing.IRequestReplyRouter> contract.</span></span> <span data-ttu-id="654d4-137">Эта конфигурация также определяет единственную клиентскую конечную точку `http://localhost:8000/servicemodelsample/service` что направляются сообщения.</span><span class="sxs-lookup"><span data-stu-id="654d4-137">This configuration also defines a single client endpoint of `http://localhost:8000/servicemodelsample/service` that messages are routed to.</span></span> <span data-ttu-id="654d4-138">Таблицы фильтров (не показано) с именем «routingTable1» содержит логику маршрутизации, используемый для перенаправления сообщений она связывается с конечной точки службы с помощью **RoutingBehavior** (для файла конфигурации) или  **RoutingConfiguration** (для программной конфигурации).</span><span class="sxs-lookup"><span data-stu-id="654d4-138">The filter table (not shown) named "routingTable1" contains the routing logic used to route messages, and is associated with the service endpoint by using the **RoutingBehavior** (for a configuration file) or **RoutingConfiguration** (for programmatic configuration).</span></span>  
  
### <a name="routing-logic"></a><span data-ttu-id="654d4-139">Логика маршрутизации</span><span class="sxs-lookup"><span data-stu-id="654d4-139">Routing Logic</span></span>  
 <span data-ttu-id="654d4-140">Для определения логики маршрутизации, используемой при перенаправлении сообщений, необходимо указать, какие данные, содержащиеся во входящих сообщениях, будут обрабатываться уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="654d4-140">To define the routing logic used to route messages, you must determine what data contained within the incoming messages can be uniquely acted upon.</span></span> <span data-ttu-id="654d4-141">Например, если все целевые конечные точки используют одинаковые действия SOAP, то значение действия внутри сообщения не может указывать, в какую конкретную точку должно перенаправляться сообщение.</span><span class="sxs-lookup"><span data-stu-id="654d4-141">For example, if all the destination endpoints you are routing to share the same SOAP Actions, the value of the Action contained within the message is not a good indicator of which specific endpoint the message should be routed to.</span></span> <span data-ttu-id="654d4-142">Если нужно перенаправить сообщения в одну конкретную точку, необходимо задать соответствующую фильтрацию (по данным, которые уникальным образом определяют целевую конечную точку).</span><span class="sxs-lookup"><span data-stu-id="654d4-142">If you must uniquely route messages to one specific endpoint, you should filter upon data that uniquely identifies the destination endpoint that the message is routed to.</span></span>  
  
 <span data-ttu-id="654d4-143">Служба маршрутизации предоставляет несколько **MessageFilter** реализаций, которые проверяют определенных значений в сообщении, например адрес, действия, имя конечной точки или даже запрос XPath.</span><span class="sxs-lookup"><span data-stu-id="654d4-143">The Routing Service provides several **MessageFilter** implementations that inspect specific values within the message, such as the address, action, endpoint name, or even an XPath query.</span></span> <span data-ttu-id="654d4-144">Если ни одна из этих реализаций не соответствует вашим потребностям, можно создать пользовательскую **MessageFilter** реализации.</span><span class="sxs-lookup"><span data-stu-id="654d4-144">If none of these implementations meet your needs you can create a custom **MessageFilter** implementation.</span></span> <span data-ttu-id="654d4-145">Дополнительные сведения о фильтрах сообщений и сравнение различных реализаций, используемых службой маршрутизации, см. в разделе [фильтры сообщений](message-filters.md) и [Выбор фильтра](choosing-a-filter.md).</span><span class="sxs-lookup"><span data-stu-id="654d4-145">For more information about message filters and a comparison of the implementations used by the Routing Service, see [Message Filters](message-filters.md) and [Choosing a Filter](choosing-a-filter.md).</span></span>  
  
 <span data-ttu-id="654d4-146">Множество фильтров сообщений организовано в таблицы фильтров, связывающие каждый **MessageFilter** с целевой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="654d4-146">Multiple message filters are organized together into filter tables, which associate each **MessageFilter** with a destination endpoint.</span></span> <span data-ttu-id="654d4-147">Кроме того, в таблице фильтров можно привести список резервных конечных точек, в которые служба маршрутизации отправляет сообщение в случае сбоя соединения.</span><span class="sxs-lookup"><span data-stu-id="654d4-147">Optionally, the filter table can also be used to specify a list of back-up endpoints that the Routing Service will attempt to send the message to in the event of a transmission failure.</span></span>  
  
 <span data-ttu-id="654d4-148">По умолчанию все фильтры сообщений в таблице оцениваются одновременно. Однако, если нужно, чтобы фильтры оценивались в определенном порядке, можно указать приоритет оценки - <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A>.</span><span class="sxs-lookup"><span data-stu-id="654d4-148">By default all message filters within a filter table are evaluated simultaneously; however, you can specify a <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> that causes the message filters to be evaluated in a specific order.</span></span> <span data-ttu-id="654d4-149">Сначала оцениваются все записи с наивысшим приоритетом. Если найдено сопоставление на более высоком уровне, фильтры сообщений с низким приоритетом не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="654d4-149">All entries with the highest priority are evaluated first, and message filters of lower priorities are not evaluated if a match is found at a higher priority level.</span></span> <span data-ttu-id="654d4-150">Дополнительные сведения о таблицах фильтров см. в разделе [фильтры сообщений](message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="654d4-150">For more information about filter tables, see [Message Filters](message-filters.md).</span></span>  
  
 <span data-ttu-id="654d4-151">В следующем примере использован фильтр <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, который оценивает все сообщения как `true`.</span><span class="sxs-lookup"><span data-stu-id="654d4-151">The following examples use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, which evaluates to `true` for all messages.</span></span> <span data-ttu-id="654d4-152">Это **MessageFilter** добавляется в таблицу «routingTable1» фильтров, которая связывает **MessageFilter** с клиентской конечной точкой «CalculatorService».</span><span class="sxs-lookup"><span data-stu-id="654d4-152">This **MessageFilter** is added to the "routingTable1" filter table, which associates the **MessageFilter** with the client endpoint named "CalculatorService".</span></span> <span data-ttu-id="654d4-153">**RoutingBehavior** указывает, что эта таблица следует использовать для маршрутизации сообщений, обрабатываемых этой конечной точкой службы.</span><span class="sxs-lookup"><span data-stu-id="654d4-153">The **RoutingBehavior** then specifies that this table should be used to route messages processed by the service endpoint.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="routingData">  
      <serviceMetadata httpGetEnabled="True"/>  
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->  
      <routing filterTableName="routingTable1" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="MatchAllFilter1" filterType="MatchAll" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
//create a new routing configuration object  
RoutingConfiguration rc = new RoutingConfiguration();  
//create the endpoint list that contains the endpoints to route to  
//in this case we have only one  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
//add a MatchAll filter to the Router's filter table  
//map it to the endpoint list defined earlier  
//when a message matches this filter, it is sent to the endpoint contained in the list  
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);  
```  
  
> [!NOTE]
>  <span data-ttu-id="654d4-154">По умолчанию служба маршрутизации оценивает только заголовки сообщений.</span><span class="sxs-lookup"><span data-stu-id="654d4-154">By default, the Routing Service only evaluates the headers of the message.</span></span> <span data-ttu-id="654d4-155">Чтобы предоставить фильтрам доступ к тексту сообщения, нужно присвоить параметру <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="654d4-155">To allow the filters to access the message body, you must set <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> to `false`.</span></span>  
  
 <span data-ttu-id="654d4-156">**Многоадресная рассылка**</span><span class="sxs-lookup"><span data-stu-id="654d4-156">**Multicast**</span></span>  
  
 <span data-ttu-id="654d4-157">Множество конфигураций службы маршрутизации используют логику монопольной фильтрации (сообщения перенаправляются в одну конкретную конечную точку). Однако может возникнуть необходимость перенаправить сообщение в несколько целевых конечных точек.</span><span class="sxs-lookup"><span data-stu-id="654d4-157">While many Routing Service configurations use exclusive filter logic that routes messages to only one specific endpoint, you may need to route a given message to multiple destination endpoints.</span></span> <span data-ttu-id="654d4-158">Для многоадресной рассылки сообщения в разные целевые точки должны быть выполнены следующие условия.</span><span class="sxs-lookup"><span data-stu-id="654d4-158">To multicast a message to multiple destinations, the following conditions must be true:</span></span>  
  
-   <span data-ttu-id="654d4-159">Форма канала не должна иметь тип «запрос-ответ» (хотя он может быть односторонним или дуплексным), так как данный тип требует, чтобы на запрос от клиентского приложения выдавался только один ответ.</span><span class="sxs-lookup"><span data-stu-id="654d4-159">The channel shape must not be request-reply (though may be one-way or duplex,) because only one reply can be received by the client application in response to the request.</span></span>  
  
-   <span data-ttu-id="654d4-160">При оценке сообщения несколько фильтров должны возвращать значение `true`.</span><span class="sxs-lookup"><span data-stu-id="654d4-160">Multiple filters must return `true` when evaluating the message.</span></span>  
  
 <span data-ttu-id="654d4-161">Если эти условия выполняются, сообщение перенаправляется во все конечные точки всех фильтров, обнаруживших значение `true`.</span><span class="sxs-lookup"><span data-stu-id="654d4-161">If these conditions are met, the message is routed to all endpoints of all filters that evaluate to `true`.</span></span> <span data-ttu-id="654d4-162">В следующем примере определяется конфигурация маршрутизации, полученного сообщения перенаправляются в обе конечные точки, если адрес конечной точки в сообщении `http://localhost:8000/routingservice/router/rounding`.</span><span class="sxs-lookup"><span data-stu-id="654d4-162">The following example defines a routing configuration that results in messages being routed to both endpoints if the endpoint address in the message is `http://localhost:8000/routingservice/router/rounding`.</span></span>  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="MatchAllFilter1" filterType="MatchAll" />  
    <filter name="RoundingFilter1" filterType="EndpointAddress"  
            filterData="http://localhost:8000/routingservice/router/rounding" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />  
        <add filterName="RoundingFilter1" endpointName="RoundingCalcService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
rc.FilterTable.Add(new MatchAllMessageFilter(), calculatorEndpointList);  
rc.FilterTable.Add(new EndpointAddressMessageFilter(new EndpointAddress(  
    "http://localhost:8000/routingservice/router/rounding")),  
    roundingCalcEndpointList);  
```  
  
### <a name="soap-processing"></a><span data-ttu-id="654d4-163">Обработка SOAP</span><span class="sxs-lookup"><span data-stu-id="654d4-163">SOAP Processing</span></span>  
 <span data-ttu-id="654d4-164">Для поддержки маршрутизации сообщений между разнородными протоколами **RoutingBehavior** по умолчанию добавляет <xref:System.ServiceModel.Routing.SoapProcessingBehavior> к всем клиентским конечным точкам, которые направляются сообщения.</span><span class="sxs-lookup"><span data-stu-id="654d4-164">To support the routing of messages between dissimilar protocols, the **RoutingBehavior** by default adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior> to all client endpoint(s) that messages are routed to.</span></span> <span data-ttu-id="654d4-165">Это поведение автоматически создает новую **MessageVersion** до маршрутизации сообщения в конечную точку, а также создается **MessageVersion** для любого ответного документа перед возвращением к запрашивающему клиентскому приложению.</span><span class="sxs-lookup"><span data-stu-id="654d4-165">This behavior automatically creates a new **MessageVersion** before routing the message to the endpoint, as well as creating a compatible **MessageVersion** for any response document before returning it to the requesting client application.</span></span>  
  
 <span data-ttu-id="654d4-166">Действия, предпринятые для создания нового **MessageVersion** для исходящего сообщения, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="654d4-166">The steps taken to create a new **MessageVersion** for the outbound message are as follows:</span></span>  
  
 <span data-ttu-id="654d4-167">**Обработка запросов**</span><span class="sxs-lookup"><span data-stu-id="654d4-167">**Request processing**</span></span>  
  
-   <span data-ttu-id="654d4-168">Получить **MessageVersion** из исходящей привязки или канала.</span><span class="sxs-lookup"><span data-stu-id="654d4-168">Get the **MessageVersion** of the outbound binding/channel.</span></span>  
  
-   <span data-ttu-id="654d4-169">Получение модуля чтения текста для первоначального сообщения.</span><span class="sxs-lookup"><span data-stu-id="654d4-169">Get the body reader for the original message.</span></span>  
  
-   <span data-ttu-id="654d4-170">Создайте новое сообщение с те же действия, модуля чтения текста и новый **MessageVersion**.</span><span class="sxs-lookup"><span data-stu-id="654d4-170">Create a new message with the same action, body reader, and a new **MessageVersion**.</span></span>  
  
-   <span data-ttu-id="654d4-171">Если <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> ! = **Addressing.None**, скопируйте To, From, FaultTo и RelatesTo в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="654d4-171">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>  
  
-   <span data-ttu-id="654d4-172">Копирование всех свойств в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="654d4-172">Copy all message properties to the new message.</span></span>  
  
-   <span data-ttu-id="654d4-173">Сохранение первоначального сообщения с запросом для обработки ответа.</span><span class="sxs-lookup"><span data-stu-id="654d4-173">Store the original request message to use when processing the response.</span></span>  
  
-   <span data-ttu-id="654d4-174">Возврат нового сообщения с запросом.</span><span class="sxs-lookup"><span data-stu-id="654d4-174">Return the new request message.</span></span>  
  
 <span data-ttu-id="654d4-175">**Обработка ответа**</span><span class="sxs-lookup"><span data-stu-id="654d4-175">**Response processing**</span></span>  
  
-   <span data-ttu-id="654d4-176">Получить **MessageVersion** исходного сообщения запроса.</span><span class="sxs-lookup"><span data-stu-id="654d4-176">Get the **MessageVersion** of the original request message.</span></span>  
  
-   <span data-ttu-id="654d4-177">Получение модуля чтения текста для принятого ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="654d4-177">Get the body reader for the received response message.</span></span>  
  
-   <span data-ttu-id="654d4-178">Создание нового ответного сообщения с тем же действием и модулем чтения текста и **MessageVersion** исходного сообщения запроса.</span><span class="sxs-lookup"><span data-stu-id="654d4-178">Create a new response message with the same action, body reader, and the **MessageVersion** of the original request message.</span></span>  
  
-   <span data-ttu-id="654d4-179">Если <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> ! = **Addressing.None**, скопируйте To, From, FaultTo и RelatesTo в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="654d4-179">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>  
  
-   <span data-ttu-id="654d4-180">Копирование всех свойств в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="654d4-180">Copy the message properties to the new message.</span></span>  
  
-   <span data-ttu-id="654d4-181">Возврат нового ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="654d4-181">Return the new response message.</span></span>  
  
 <span data-ttu-id="654d4-182">По умолчанию **SoapProcessingBehavior** клиентских конечных точек, автоматически добавляется <xref:System.ServiceModel.Routing.RoutingBehavior> при запуске службы; тем не менее, можно управлять, добавляется ли обработки SOAP ко всем клиентским конечным точкам с помощью <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="654d4-182">By default, the **SoapProcessingBehavior** is automatically added to the client endpoints by the <xref:System.ServiceModel.Routing.RoutingBehavior> when the service starts; however, you can control whether SOAP processing is added to all client endpoints by using the <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A> property.</span></span> <span data-ttu-id="654d4-183">Можно напрямую добавить поведение к конкретной клиентской точке, а также включить или отключить это поведение на уровне конечной точки, если требуется более точное управление обработкой SOAP.</span><span class="sxs-lookup"><span data-stu-id="654d4-183">You can also add the behavior directly to a specific endpoint and enable or disable this behavior at the endpoint level if a more granular control of SOAP processing is required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="654d4-184">Если обработка SOAP отключена для точки, требующей версии (MessageVersion), отличной от версии первоначального сообщения с запросом, то перед отправкой сообщения в целевую конечную точку необходимо указать пользовательский механизм для выполнения любых требуемых изменений SOAP.</span><span class="sxs-lookup"><span data-stu-id="654d4-184">If SOAP processing is disabled for an endpoint that requires a different MessageVersion than that of the original request message, you must provide a custom mechanism for performing any SOAP modifications that are required before sending the message to the destination endpoint.</span></span>  
  
 <span data-ttu-id="654d4-185">В следующих примерах **soapProcessingEnabled** свойство используется для предотвращения **SoapProcessingBehavior** автоматическое добавление ко всем клиентским конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="654d4-185">In the following examples, the **soapProcessingEnabled** property is used to prevent the **SoapProcessingBehavior** from being automatically added to all client endpoints.</span></span>  
  
```xml  
<behaviors>  
  <!--default routing service behavior definition-->  
  <serviceBehaviors>  
    <behavior name="routingConfiguration">  
      <routing filterTableName="filterTable1" soapProcessingEnabled="false"/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
```csharp  
//create the default RoutingConfiguration  
RoutingConfiguration rc = new RoutingConfiguration();  
rc.SoapProcessingEnabled = false;  
```  
  
### <a name="dynamic-configuration"></a><span data-ttu-id="654d4-186">Динамическая конфигурация</span><span class="sxs-lookup"><span data-stu-id="654d4-186">Dynamic Configuration</span></span>  
 <span data-ttu-id="654d4-187">Если добавляются дополнительные клиентские конечные точки или возникает необходимость изменить фильтры маршрутизации сообщений, нужно иметь возможность динамически обновлять конфигурацию во время выполнения. Таким образом можно предотвратить прерывание службы в конечных точках, в настоящий момент получающих сообщения через службу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-187">When you add additional client endpoints, or need to modify the filters that are used to route messages, you must have a way to update the configuration dynamically at run time to prevent interrupting the service to the endpoints currently receiving messages through the Routing Service.</span></span> <span data-ttu-id="654d4-188">Может оказаться недостаточным изменить файл конфигурации или код размещающего приложения. Оба этих метода требуют перезапуска приложения, что может привести к потере передаваемых в настоящий момент сообщений, а также к простою на время перезапуска службы.</span><span class="sxs-lookup"><span data-stu-id="654d4-188">Modifying a configuration file or the code of the host application is not always sufficient, because either method requires recycling the application, which would lead to the potential loss of any messages currently in transit and the potential for downtime while waiting on the service to restart.</span></span>  
  
 <span data-ttu-id="654d4-189">Можно изменять только **RoutingConfiguration** программным способом.</span><span class="sxs-lookup"><span data-stu-id="654d4-189">You can only modify the **RoutingConfiguration** programmatically.</span></span> <span data-ttu-id="654d4-190">Изначально можно настроить службу с помощью файла конфигурации, можно только изменить конфигурацию во время выполнения, создав новый **RoutingConfigution** и передается в качестве параметра <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> метод предоставляемые <xref:System.ServiceModel.Routing.RoutingExtension> расширения службы.</span><span class="sxs-lookup"><span data-stu-id="654d4-190">While you can initially configure the service by using a configuration file, you can only modify the configuration at run time by constructing a new **RoutingConfigution** and passing it as a parameter to the <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> method exposed by the <xref:System.ServiceModel.Routing.RoutingExtension> service extension.</span></span> <span data-ttu-id="654d4-191">Наличие сообщений, передаваемых в настоящий момент по-прежнему будет направляться с предыдущей конфигурацией, во время сообщения, полученные после вызова **ApplyConfiguration** использовать новую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="654d4-191">Any messages currently in transit continue to be routed using the previous configuration, while messages received after the call to **ApplyConfiguration** use the new configuration.</span></span> <span data-ttu-id="654d4-192">В следующем примере показано создание экземпляра службы маршрутизации с последующим изменением конфигурации.</span><span class="sxs-lookup"><span data-stu-id="654d4-192">The following example demonstrates creating an instance of the Routing Service and then subsequently modifying the configuration.</span></span>  
  
```csharp  
RoutingConfiguration routingConfig = new RoutingConfiguration();  
routingConfig.RouteOnHeadersOnly = true;  
routingConfig.FilterTable.Add(new MatchAllMessageFilter(), endpointList);  
RoutingBehavior routing = new RoutingBehavior(routingConfig);  
routerHost.Description.Behaviors.Add(routing);  
routerHost.Open();  
// Construct a new RoutingConfiguration  
RoutingConfiguration rc2 = new RoutingConfiguration();  
ServiceEndpoint clientEndpoint = new ServiceEndpoint();  
ServiceEndpoint clientEndpoint2 = new ServiceEndpoint();  
// Add filters to the FilterTable in the new configuration  
rc2.FilterTable.add(new MatchAllMessageFilter(),  
       new List<ServiceEndpoint>() { clientEndpoint });  
rc2.FilterTable.add(new MatchAllMessageFilter(),  
       new List<ServiceEndpoint>() { clientEndpoint2 });  
rc2.RouteOnHeadersOnly = false;  
// Apply the new configuration to the Routing Service hosted in  
routerHost.routerHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc2);  
```  
  
> [!NOTE]
>  <span data-ttu-id="654d4-193">При обновлении службы маршрутизации подобным образом возможно только передать новую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="654d4-193">When updating the Routing Service in this manner it is only possible to pass a new configuration.</span></span> <span data-ttu-id="654d4-194">Нельзя изменить отдельные элементы текущей конфигурации или добавить в нее новые записи. Необходимо создать и передать новую конфигурацию, которая заменит текущую.</span><span class="sxs-lookup"><span data-stu-id="654d4-194">It is not possible to modify only select elements of the current configuration or append new entries to the current configuration; you must create and pass a new configuration that replaces the existing one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="654d4-195">Все сеансы, открытые с предыдущей конфигурацией, продолжат ее использовать.</span><span class="sxs-lookup"><span data-stu-id="654d4-195">Any sessions opened using the previous configuration continue using the previous configuration.</span></span> <span data-ttu-id="654d4-196">Новая конфигурация применяется только к новым сеансам.</span><span class="sxs-lookup"><span data-stu-id="654d4-196">The new configuration is only used by new sessions.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="654d4-197">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="654d4-197">Error Handling</span></span>  
 <span data-ttu-id="654d4-198">Если при попытке отправки сообщения возникнет исключение <xref:System.ServiceModel.CommunicationException>, будет запущена обработка ошибок.</span><span class="sxs-lookup"><span data-stu-id="654d4-198">If any <xref:System.ServiceModel.CommunicationException> is encountered while attempting to send a message, error handling take place.</span></span> <span data-ttu-id="654d4-199">Эти исключения обычно указывают на то, что при попытке связаться с определенной конечной точкой клиента была обнаружена проблема, например <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> или <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span><span class="sxs-lookup"><span data-stu-id="654d4-199">These exceptions typically indicate that a problem was encountered while attempting to communicate with the defined client endpoint, such as an <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, or <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span> <span data-ttu-id="654d4-200">Код обработки ошибок также перехватит и попытается повторить отправку при <xref:System.TimeoutException> происходит, это еще одно общее исключение, которое не является производным от **CommunicationException**.</span><span class="sxs-lookup"><span data-stu-id="654d4-200">The error handling-code will also catch and attempt to retry sending when a <xref:System.TimeoutException> occurs, which is another common exception that is not derived from **CommunicationException**.</span></span>  
  
 <span data-ttu-id="654d4-201">Если возникнет одно из вышеприведенных исключений, служба маршрутизации перейдет к резервному списку конечных точек.</span><span class="sxs-lookup"><span data-stu-id="654d4-201">When one of the preceding exceptions occurs, the Routing Service fails over to a list of backup endpoints.</span></span> <span data-ttu-id="654d4-202">В случае, если все резервные конечные точки обнаружат сбой сети или канала связи, либо конечная точка вернет исключение, указывающее на сбой целевой службы, служба маршрутизации вернет клиентскому приложению ошибку.</span><span class="sxs-lookup"><span data-stu-id="654d4-202">If all backup endpoints fail with a communications failure, or if an endpoint returns an exception that indicates a failure within the destination service, the Routing Service returns a fault to the client application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="654d4-203">Функция обработки ошибок перехватывает и обрабатывает исключения, возникающие при отправке сообщения или при закрытии канала.</span><span class="sxs-lookup"><span data-stu-id="654d4-203">The error-handling functionality captures and handles exceptions that occur when attempting to send a message and when attempting to close a channel.</span></span> <span data-ttu-id="654d4-204">Код обработки ошибок не предназначен для обнаружения или обработки исключений, созданных конечных точек приложения, в которой он взаимодействует с; <xref:System.ServiceModel.FaultException> , создаваемых службой, отображается в службе маршрутизации как **FaultMessage** и передается обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="654d4-204">The error-handling code is not intended to detect or handle exceptions created by the application endpoints it is communicating with; a <xref:System.ServiceModel.FaultException> thrown by a service appears at the Routing Service as a **FaultMessage** and is flowed back to the client.</span></span>  
>   
>  <span data-ttu-id="654d4-205">Если при попытке службы маршрутизации перенаправить сообщение возникает ошибка, на стороне клиента можно получить исключение <xref:System.ServiceModel.FaultException>, а не исключение <xref:System.ServiceModel.EndpointNotFoundException>, которое обычно формируется при отсутствии службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-205">If an error occurs when the routing service tries to relay a message, you may  get a <xref:System.ServiceModel.FaultException> on the client side, rather than a <xref:System.ServiceModel.EndpointNotFoundException> you would normally get in the absence of the routing service.</span></span> <span data-ttu-id="654d4-206">Таким способом служба маршрутизации может маскировать исключения и не обеспечивать полную прозрачность при просмотре вложенных исключений.</span><span class="sxs-lookup"><span data-stu-id="654d4-206">A routing service may thus mask exceptions and not provide full transparency unless you examine nested exceptions.</span></span>  
  
### <a name="tracing-exceptions"></a><span data-ttu-id="654d4-207">Исключения трассировки</span><span class="sxs-lookup"><span data-stu-id="654d4-207">Tracing Exceptions</span></span>  
 <span data-ttu-id="654d4-208">При отправке сообщение в конечную точку в списке не, служба маршрутизации отслеживает полученные данные исключения и прикрепляет их в виде свойства сообщения с именем **исключения**.</span><span class="sxs-lookup"><span data-stu-id="654d4-208">When sending a message to an endpoint in a list fails, the Routing Service traces the resulting exception data and attaches the exception details as a message property named **Exceptions**.</span></span> <span data-ttu-id="654d4-209">Таким образом данные исключения сохраняются, а пользователь получает к ним программный доступ (через инспектор сообщений).</span><span class="sxs-lookup"><span data-stu-id="654d4-209">This preserves the exception data and allows a user programmatic access through a message inspector.</span></span>  <span data-ttu-id="654d4-210">Данные исключения хранятся в сообщении в словаре, который сопоставляет имя конечной точки со сведениями об исключении, полученными при попытке отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="654d4-210">The exception data is stored per message in a dictionary that maps the endpoint name to the exception details encountered when trying to send a message to it.</span></span>  
  
### <a name="backup-endpoints"></a><span data-ttu-id="654d4-211">Резервные конечные точки</span><span class="sxs-lookup"><span data-stu-id="654d4-211">Backup Endpoints</span></span>  
 <span data-ttu-id="654d4-212">Для каждой записи фильтра в таблице фильтров можно указать список резервных конечных точек, которые будут использованы в случае сбоя при отправке в основную точку.</span><span class="sxs-lookup"><span data-stu-id="654d4-212">Each filter entry within the filter table can optionally specify a list of backup endpoints, which are used in the event of a transmission failure when sending to the primary endpoint.</span></span> <span data-ttu-id="654d4-213">Если произойдет такой сбой, служба маршрутизации попытается передать сообщение в конечную точку, содержащуюся в первой записи списка резервных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="654d4-213">If such a failure occurs, the Routing Service attempts to transmit the message to the first entry in the backup endpoint list.</span></span> <span data-ttu-id="654d4-214">Если при этом также возникнет сбой, служба попытается использовать следующую конечную точку в списке.</span><span class="sxs-lookup"><span data-stu-id="654d4-214">If this send attempt also encounters a transmission failure, the next endpoint in the backup list is tried.</span></span> <span data-ttu-id="654d4-215">Служба маршрутизации продолжит отправлять сообщения в каждую конечную точку списка до тех пор, пока не будет выполнено одно из следующих условий: сообщение успешно получено, все точки возвратили ошибку передачи, конечная точка возвратила сбой, не связанный с сетью или доступом.</span><span class="sxs-lookup"><span data-stu-id="654d4-215">The Routing Service continues sending the message to each endpoint in the list until the message is successfully received, all endpoints return a transmission failure, or a non-transmission failure is returned by an endpoint.</span></span>  
  
 <span data-ttu-id="654d4-216">В следующих примерах выполняется настройка службы маршрутизации для использования резервного списка.</span><span class="sxs-lookup"><span data-stu-id="654d4-216">The following examples configure the Routing Service to use a backup list.</span></span>  
  
```xml  
<routing>  
  <filters>  
    <!-- Create a MatchAll filter that catches all messages -->  
    <filter name="MatchAllFilter1" filterType="MatchAll" />  
  </filters>  
  <filterTables>  
    <!-- Set up the Routing Service's Message Filter Table -->  
    <filterTable name="filterTable1">  
        <!-- Add an entry that maps the MatchAllMessageFilter to the dead destination -->  
        <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
        <!-- Listed in the backupEndpointList -->  
        <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
    </filterTable>  
  </filterTables>  
  <!-- Create the backup endpoint list -->  
  <backupLists>  
    <!-- Add an endpoint list that contains the backup destinations -->  
    <backupList name="backupEndpointList">  
      <add endpointName="realDestination" />  
      <add endpointName="backupDestination" />  
    </backupList>  
  </backupLists>  
</routing>  
```  
  
```csharp  
//create the endpoint list that contains the service endpoints we want to route to  
List<ServiceEndpoint> backupList = new List<ServiceEndpoint>();  
//add the endpoints in the order that the Routing Service should contact them  
//first add the endpoint that we know is down  
//clearly, normally you wouldn't know that this endpoint was down by default  
backupList.Add(fakeDestination);  
//then add the real Destination endpoint  
//the Routing Service attempts to send to this endpoint only if it   
//encounters a TimeOutException or CommunicationException when sending  
//to the previous endpoint in the list.  
backupList.Add(realDestination);  
//add the backupDestination endpoint  
//the Routing Service attempts to send to this endpoint only if it  
//encounters a TimeOutException or CommunicationsException when sending  
//to the previous endpoints in the list  
backupList.Add(backupDestination);  
//create the default RoutingConfiguration option              
RoutingConfiguration rc = new RoutingConfiguration();  
//add a MatchAll filter to the Routing Configuration's filter table  
//map it to the list of endpoints defined above  
//when a message matches this filter, it is sent to the endpoints in the list in order  
//if an endpoint is down or does not respond (which the first endpoint won't  
//since the client does not exist), the Routing Service automatically moves the message  
//to the next endpoint in the list and try again.  
rc.FilterTable.Add(new MatchAllMessageFilter(), backupList);  
```  
  
### <a name="supported-error-patterns"></a><span data-ttu-id="654d4-217">Поддерживаемые шаблоны ошибок</span><span class="sxs-lookup"><span data-stu-id="654d4-217">Supported Error Patterns</span></span>  
 <span data-ttu-id="654d4-218">В следующей таблице описаны шаблоны, совместимые со списком резервных конечных точек, а также приведены более подробные сведения по обработке ошибок для конкретных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="654d4-218">The following table describes the patterns that are compatible with the use of backup endpoint lists, along with notes describing the details of error handling for specific patterns.</span></span>  
  
|<span data-ttu-id="654d4-219">Шаблон</span><span class="sxs-lookup"><span data-stu-id="654d4-219">Pattern</span></span>|<span data-ttu-id="654d4-220">Сеанс</span><span class="sxs-lookup"><span data-stu-id="654d4-220">Session</span></span>|<span data-ttu-id="654d4-221">Транзакция</span><span class="sxs-lookup"><span data-stu-id="654d4-221">Transaction</span></span>|<span data-ttu-id="654d4-222">Контекст получения</span><span class="sxs-lookup"><span data-stu-id="654d4-222">Receive Context</span></span>|<span data-ttu-id="654d4-223">Поддерживаемый резервный список</span><span class="sxs-lookup"><span data-stu-id="654d4-223">Backup List Supported</span></span>|<span data-ttu-id="654d4-224">Примечания</span><span class="sxs-lookup"><span data-stu-id="654d4-224">Notes</span></span>|  
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|  
|<span data-ttu-id="654d4-225">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-225">One-Way</span></span>||||<span data-ttu-id="654d4-226">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-226">Yes</span></span>|<span data-ttu-id="654d4-227">Пытается повторно отправить сообщение резервной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="654d4-227">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="654d4-228">Если сообщение является многоадресным, в резервное назначение перемещается только сообщение, в канале которого произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="654d4-228">If this message is being multicast, only the message on the failed channel is moved to its backup destination.</span></span>|  
|<span data-ttu-id="654d4-229">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-229">One-Way</span></span>||<span data-ttu-id="654d4-230">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-230">✓</span></span>||<span data-ttu-id="654d4-231">Нет</span><span class="sxs-lookup"><span data-stu-id="654d4-231">No</span></span>|<span data-ttu-id="654d4-232">Возникает исключение, и выполняется откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="654d4-232">An exception is thrown and the transaction is rolled back.</span></span>|  
|<span data-ttu-id="654d4-233">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-233">One-Way</span></span>|||<span data-ttu-id="654d4-234">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-234">✓</span></span>|<span data-ttu-id="654d4-235">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-235">Yes</span></span>|<span data-ttu-id="654d4-236">Пытается повторно отправить сообщение резервной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="654d4-236">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="654d4-237">После успешного получения сообщения нужно закрыть все контексты получения.</span><span class="sxs-lookup"><span data-stu-id="654d4-237">After the message is successfully received, complete all receive contexts.</span></span> <span data-ttu-id="654d4-238">Если сообщение не получено любой конечной точкой, завершать контекст получения не нужно.</span><span class="sxs-lookup"><span data-stu-id="654d4-238">If the message is not successfully received by any endpoint, do not complete the receive context.</span></span><br /><br /> <span data-ttu-id="654d4-239">В случае многоадресной рассылки сообщения контекст получения завершается, если сообщение получено хотя бы одной конечной точкой (основной или резервной).</span><span class="sxs-lookup"><span data-stu-id="654d4-239">When this message is being multicast, the receive context is only completed if the message is successfully received by at least one endpoint (primary or backup).</span></span> <span data-ttu-id="654d4-240">Если ни одна из конечных точек многоадресной рассылки не получила сообщение, завершать контекст получения не нужно.</span><span class="sxs-lookup"><span data-stu-id="654d4-240">If none of the endpoints in any of the multicast paths successfully receive the message, do not complete the receive context.</span></span>|  
|<span data-ttu-id="654d4-241">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-241">One-Way</span></span>||<span data-ttu-id="654d4-242">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-242">✓</span></span>|<span data-ttu-id="654d4-243">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-243">✓</span></span>|<span data-ttu-id="654d4-244">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-244">Yes</span></span>|<span data-ttu-id="654d4-245">Отмените предыдущую транзакцию, создайте новую транзакцию и повторно отправьте все сообщения.</span><span class="sxs-lookup"><span data-stu-id="654d4-245">Abort the previous transaction, create a new transaction, and resend all messages.</span></span> <span data-ttu-id="654d4-246">Сообщения, обнаруживающие ошибку, передаются в резервное назначение.</span><span class="sxs-lookup"><span data-stu-id="654d4-246">Messages that encountered an error are transmitted to a backup destination.</span></span><br /><br /> <span data-ttu-id="654d4-247">После создания транзакции, в которой все операции по передаче были успешными, можно завершить контексты получения и зафиксировать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="654d4-247">After a transaction has been created in which all transmissions succeed, complete the receive contexts and commit the transaction.</span></span>|  
|<span data-ttu-id="654d4-248">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-248">One-Way</span></span>|<span data-ttu-id="654d4-249">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-249">✓</span></span>|||<span data-ttu-id="654d4-250">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-250">Yes</span></span>|<span data-ttu-id="654d4-251">Пытается повторно отправить сообщение резервной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="654d4-251">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="654d4-252">В случае многоадресного сценария в резервные назначения повторно отправляются только сообщения, в сеансах которых обнаружена ошибка или сбой при закрытии.</span><span class="sxs-lookup"><span data-stu-id="654d4-252">In a multicast scenario only the messages in a session that encountered an error or in a session whose session close failed are resent to backup destinations.</span></span>|  
|<span data-ttu-id="654d4-253">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-253">One-Way</span></span>|<span data-ttu-id="654d4-254">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-254">✓</span></span>|<span data-ttu-id="654d4-255">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-255">✓</span></span>||<span data-ttu-id="654d4-256">Нет</span><span class="sxs-lookup"><span data-stu-id="654d4-256">No</span></span>|<span data-ttu-id="654d4-257">Возникает исключение, и выполняется откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="654d4-257">An exception is thrown and the transaction is rolled back.</span></span>|  
|<span data-ttu-id="654d4-258">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-258">One-Way</span></span>|<span data-ttu-id="654d4-259">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-259">✓</span></span>||<span data-ttu-id="654d4-260">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-260">✓</span></span>|<span data-ttu-id="654d4-261">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-261">Yes</span></span>|<span data-ttu-id="654d4-262">Пытается повторно отправить сообщение резервной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="654d4-262">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="654d4-263">После того как все сообщения отправлены без ошибок, сеанс указывает на то, что сообщений не осталось, служба маршрутизации закрывает все исходящие каналы сеанса, завершаются все контексты получения, а затем закрывается входящий канал сеанса.</span><span class="sxs-lookup"><span data-stu-id="654d4-263">After all message sends complete without error, the session indicates no more messages and the Routing Service successfully closes all outbound session channel(s), all receive contexts are completed, and the inbound session channel is closed.</span></span>|  
|<span data-ttu-id="654d4-264">Одностороннее взаимодействие</span><span class="sxs-lookup"><span data-stu-id="654d4-264">One-Way</span></span>|<span data-ttu-id="654d4-265">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-265">✓</span></span>|<span data-ttu-id="654d4-266">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-266">✓</span></span>|<span data-ttu-id="654d4-267">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-267">✓</span></span>|<span data-ttu-id="654d4-268">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-268">Yes</span></span>|<span data-ttu-id="654d4-269">Отмена текущей транзакции и создание новой.</span><span class="sxs-lookup"><span data-stu-id="654d4-269">Abort the current transaction and create a new one.</span></span> <span data-ttu-id="654d4-270">Повторная отправка всех предыдущих сообщений в сеансе.</span><span class="sxs-lookup"><span data-stu-id="654d4-270">Resend all previous messages in the session.</span></span> <span data-ttu-id="654d4-271">После создания транзакции, в которой все сообщения отправлены без ошибок, а также после того, как сеанс указывает на то, что сообщений не осталось, закрываются все исходящие каналы сеанса, завершаются все контексты получения, закрывается входящий канал и происходит фиксация транзакции.</span><span class="sxs-lookup"><span data-stu-id="654d4-271">After a transaction has been created in which all messages have been successfully sent and the session indicates no more messages, all the outbound session channels are closed, receive contexts are all completed with the transaction, the inbound session channel is closed, and the transaction is committed.</span></span><br /><br /> <span data-ttu-id="654d4-272">Если в сеансах использовалась многоадресная рассылка, сообщения без ошибок повторно отправляются в то же назначение, а сообщения с ошибками - в резервное назначение.</span><span class="sxs-lookup"><span data-stu-id="654d4-272">When the sessions are being multicast the messages that had no error are resent to the same destination as before, and messages that encountered an error are sent to backup destinations.</span></span>|  
|<span data-ttu-id="654d4-273">Двусторонний</span><span class="sxs-lookup"><span data-stu-id="654d4-273">Two-Way</span></span>||||<span data-ttu-id="654d4-274">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-274">Yes</span></span>|<span data-ttu-id="654d4-275">Отправьте резервному назначению.</span><span class="sxs-lookup"><span data-stu-id="654d4-275">Send to a backup destination.</span></span>  <span data-ttu-id="654d4-276">После того как канал вернет ответное сообщение, верните ответ исходному клиенту.</span><span class="sxs-lookup"><span data-stu-id="654d4-276">After a channel returns a response message, return the response to the original client.</span></span>|  
|<span data-ttu-id="654d4-277">Двусторонний</span><span class="sxs-lookup"><span data-stu-id="654d4-277">Two-Way</span></span>|<span data-ttu-id="654d4-278">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-278">✓</span></span>|||<span data-ttu-id="654d4-279">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-279">Yes</span></span>|<span data-ttu-id="654d4-280">Отправка всех сообщений в канале в резервное назначение.</span><span class="sxs-lookup"><span data-stu-id="654d4-280">Send all messages on the channel to a backup destination.</span></span>  <span data-ttu-id="654d4-281">После того как канал вернет ответное сообщение, верните ответ исходному клиенту.</span><span class="sxs-lookup"><span data-stu-id="654d4-281">After a channel returns a response message, return the response to the original client.</span></span>|  
|<span data-ttu-id="654d4-282">Двусторонний</span><span class="sxs-lookup"><span data-stu-id="654d4-282">Two-Way</span></span>||<span data-ttu-id="654d4-283">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-283">✓</span></span>||<span data-ttu-id="654d4-284">Нет</span><span class="sxs-lookup"><span data-stu-id="654d4-284">No</span></span>|<span data-ttu-id="654d4-285">Возникает исключение, и выполняется откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="654d4-285">An exception is thrown and the transaction is rolled back.</span></span>|  
|<span data-ttu-id="654d4-286">Двусторонний</span><span class="sxs-lookup"><span data-stu-id="654d4-286">Two-Way</span></span>|<span data-ttu-id="654d4-287">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-287">✓</span></span>|<span data-ttu-id="654d4-288">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-288">✓</span></span>||<span data-ttu-id="654d4-289">Нет</span><span class="sxs-lookup"><span data-stu-id="654d4-289">No</span></span>|<span data-ttu-id="654d4-290">Возникает исключение, и выполняется откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="654d4-290">An exception is thrown and the transaction is rolled back.</span></span>|  
|<span data-ttu-id="654d4-291">Дуплекс</span><span class="sxs-lookup"><span data-stu-id="654d4-291">Duplex</span></span>||||<span data-ttu-id="654d4-292">Нет</span><span class="sxs-lookup"><span data-stu-id="654d4-292">No</span></span>|<span data-ttu-id="654d4-293">В настоящий момент дуплексная связь вне сеанса не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="654d4-293">Non-session duplex communication is not currently supported.</span></span>|  
|<span data-ttu-id="654d4-294">Дуплекс</span><span class="sxs-lookup"><span data-stu-id="654d4-294">Duplex</span></span>|<span data-ttu-id="654d4-295">✓</span><span class="sxs-lookup"><span data-stu-id="654d4-295">✓</span></span>|||<span data-ttu-id="654d4-296">Да</span><span class="sxs-lookup"><span data-stu-id="654d4-296">Yes</span></span>|<span data-ttu-id="654d4-297">Отправьте резервному назначению.</span><span class="sxs-lookup"><span data-stu-id="654d4-297">Send to a backup destination.</span></span>|  
  
## <a name="hosting"></a><span data-ttu-id="654d4-298">Размещение</span><span class="sxs-lookup"><span data-stu-id="654d4-298">Hosting</span></span>  
 <span data-ttu-id="654d4-299">Служба маршрутизация реализована как служба WCF, поэтому она должна размещаться в приложении или в службах IIS или WAS.</span><span class="sxs-lookup"><span data-stu-id="654d4-299">Because the Routing Service is implemented as a WCF service, it must be either self-hosted within an application or hosted by IIS or WAS.</span></span> <span data-ttu-id="654d4-300">Рекомендуется, чтобы служба маршрутизации размещалась в служебном приложении Windows, IIS или WAS. В этом случае будут доступны преимущества этих сред размещения - автоматический запуск и управление жизненным циклом.</span><span class="sxs-lookup"><span data-stu-id="654d4-300">It is recommended that the Routing Service be hosted in either IIS, WAS, or a Windows Service application to take advantage of the automatic start and life-cycle management features available in these hosting environments.</span></span>  
  
 <span data-ttu-id="654d4-301">В следующем примере показано размещение службы маршрутизации в приложении.</span><span class="sxs-lookup"><span data-stu-id="654d4-301">The following example demonstrates hosting the Routing Service in an application.</span></span>  
  
```csharp  
using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
```  
  
 <span data-ttu-id="654d4-302">Чтобы разместить службу маршрутизации в службах IIS или WAS, нужно создать файл службы (SVC) или использовать основанную на конфигурации активацию службы.</span><span class="sxs-lookup"><span data-stu-id="654d4-302">To host the Routing Service within IIS or WAS, you must either create a service file (.svc) or use configuration-based activation of the service.</span></span> <span data-ttu-id="654d4-303">При использовании файла службы нужно задать <xref:System.ServiceModel.Routing.RoutingService>, используя параметр Service.</span><span class="sxs-lookup"><span data-stu-id="654d4-303">When using a service file, you must specify the <xref:System.ServiceModel.Routing.RoutingService> using the Service parameter.</span></span> <span data-ttu-id="654d4-304">В следующем примере приведен образец файла службы, который можно использовать для размещения службы маршрутизации с помощью служб IIS или WAS.</span><span class="sxs-lookup"><span data-stu-id="654d4-304">The following example contains a sample service file that can be used to host the Routing Service with IIS or WAS.</span></span>  
  
```  
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,   
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,   
     PublicKeyToken=31bf3856ad364e35" %>  
```  
  
## <a name="routing-service-and-impersonation"></a><span data-ttu-id="654d4-305">Служба маршрутизации и олицетворение</span><span class="sxs-lookup"><span data-stu-id="654d4-305">Routing Service and Impersonation</span></span>  
 <span data-ttu-id="654d4-306">Службу маршрутизации WCF можно использовать с олицетворением как для отправки, так и для получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="654d4-306">The WCF Routing Service can be used with impersonation for both sending and receiving messages.</span></span> <span data-ttu-id="654d4-307">Применяются все стандартные ограничения Windows для процесса олицетворения.</span><span class="sxs-lookup"><span data-stu-id="654d4-307">All of the usual Windows constraints of impersonation apply.</span></span> <span data-ttu-id="654d4-308">Если при написании собственной службы для использования олицетворения необходимо было настроить некоторые разрешения учетной записи или службы, то такие же шаги необходимо выполнить и для использования олицетворения в службе маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-308">If you would have needed to set up service or account permissions to use impersonation when writing your own service, then you’ll have to do those same steps to use impersonation with the routing service.</span></span> <span data-ttu-id="654d4-309">Дополнительные сведения см. в разделе [делегирование и олицетворение](delegation-and-impersonation-with-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="654d4-309">For more information, see [Delegation and Impersonation](delegation-and-impersonation-with-wcf.md).</span></span>  
  
 <span data-ttu-id="654d4-310">Олицетворение в службе маршрутизации требует использования олицетворения средствами ASP.NET в режиме совместимости с ASP.NET или использования учетных данных Windows, для которых олицетворение разрешено.</span><span class="sxs-lookup"><span data-stu-id="654d4-310">Impersonation with the routing service requires either the use of ASP.NET impersonation while in ASP.NET compatibility mode or the use of Windows credentials that have been configured to allow impersonation.</span></span> <span data-ttu-id="654d4-311">Дополнительные сведения о режиме совместимости с ASP.NET, см. в разделе [службы WCF и ASP.NET](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="654d4-311">For more information about ASP.NET compatibility mode, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="654d4-312">Служба маршрутизации WCF не поддерживает олицетворение с обычной проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="654d4-312">The WCF Routing Service does not support impersonation with basic authentication.</span></span>  
  
 <span data-ttu-id="654d4-313">Для использования олицетворения ASP.NET со службой маршрутизации включите режим совместимости с ASP.NET в рабочей среде размещения службы.</span><span class="sxs-lookup"><span data-stu-id="654d4-313">To use ASP.NET impersonation with the routing service, enable ASP.NET compatibility mode on the service hosting environment.</span></span> <span data-ttu-id="654d4-314">Для службы маршрутизации уже выставлено разрешение использования режима совместимости с ASP.NET и функции олицетворения будут включены автоматически.</span><span class="sxs-lookup"><span data-stu-id="654d4-314">The routing service has already been marked as allowing ASP.NET compatibility mode and impersonation will automatically be enabled.</span></span> <span data-ttu-id="654d4-315">Олицетворение - единственная поддерживаемая функция интеграции ASP.NET со службой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="654d4-315">Impersonation is the only supported use of ASP.NET integration with the routing service.</span></span>  
  
 <span data-ttu-id="654d4-316">Чтобы использовать олицетворение с помощью учетных данных Windows в службе маршрутизации, необходимо соответствующим образом настроить и службу, и учетные данные.</span><span class="sxs-lookup"><span data-stu-id="654d4-316">To use Windows credential impersonation with the routing service you need to configure both the credentials and the service.</span></span> <span data-ttu-id="654d4-317">Объект пользовательских учетных данных клиента (<xref:System.ServiceModel.Security.WindowsClientCredential>, доступный из фабрики <xref:System.ServiceModel.ChannelFactory>) определяет свойство <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>, которое должно быть задано, чтобы разрешить использование олицетворения.</span><span class="sxs-lookup"><span data-stu-id="654d4-317">The client credentials object (<xref:System.ServiceModel.Security.WindowsClientCredential>, accessable from the <xref:System.ServiceModel.ChannelFactory>) defines an <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property that must be set to permit impersonation.</span></span> <span data-ttu-id="654d4-318">Наконец, в службе требуется настроить поведение <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> для установки свойства `ImpersonateCallerForAllOperations` в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="654d4-318">Finally, on the service you need to configure the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> behavior to set `ImpersonateCallerForAllOperations` to `true`.</span></span> <span data-ttu-id="654d4-319">Служба маршрутизации использует этот флаг, чтобы определить, следует ли создавать клиентов для направления сообщений с олицетворением пользователей.</span><span class="sxs-lookup"><span data-stu-id="654d4-319">The routing service uses this flag to decide whether to create the clients for forwarding messages with impersonation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="654d4-320">См. также</span><span class="sxs-lookup"><span data-stu-id="654d4-320">See also</span></span>

- [<span data-ttu-id="654d4-321">Фильтры сообщений</span><span class="sxs-lookup"><span data-stu-id="654d4-321">Message Filters</span></span>](message-filters.md)
- [<span data-ttu-id="654d4-322">Контракты маршрутизации</span><span class="sxs-lookup"><span data-stu-id="654d4-322">Routing Contracts</span></span>](routing-contracts.md)
- [<span data-ttu-id="654d4-323">Выбор фильтра</span><span class="sxs-lookup"><span data-stu-id="654d4-323">Choosing a Filter</span></span>](choosing-a-filter.md)
