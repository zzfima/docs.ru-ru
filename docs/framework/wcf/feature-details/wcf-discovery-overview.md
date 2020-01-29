---
title: Общие сведения об обнаружении WCF
ms.date: 03/30/2017
ms.assetid: 84fad0e4-23b1-45b5-a2d4-c9cdf90bbb22
ms.openlocfilehash: 46092c3bce87d426f4d465367e99a9ebb6dc37fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737491"
---
# <a name="wcf-discovery-overview"></a>Общие сведения об обнаружении WCF
API обнаружения предоставляют унифицированную модель программирования для динамичной публикации и обнаружения веб-служб с использованием протокола WS-Discovery. Эти API позволяют службам публиковать себя, а также позволяют клиентам находить опубликованные службы. После того как служба была включена для обнаружения, она получает возможность отправлять объявляющие сообщения, а также прослушивать и отвечать на запросы обнаружения. Службы, доступные для обнаружения, могут отправлять сообщения Hello для оповещения о своем появлении в сети и сообщения Bye для оповещения об уходе из сети. Для нахождения службы клиенты отправляют запрос `Probe`, содержащий заданные критерии, например тип контракта службы, ключевые слова и область в сети. Службы получают запрос `Probe` и определяют, соответствуют ли они критериям. Если служба им соответствует, она отвечает, отправляя клиенту сообщение `ProbeMatch`, содержащее сведения, необходимые для установки связи со службой. Клиенты также могут отправлять запросы `Resolve`, позволяющие им находить службы, изменившие адрес конечной точки. Соответствующие службы отвечают на запросы `Resolve`, отправляя клиенту сообщение `ResolveMatch`.  
  
## <a name="ad-hoc-and-managed-modes"></a>Нерегламентированный и управляемый режимы  
 API обнаружения поддерживают два режима: управляемый и нерегламентированный. В управляемом режиме существует централизованный сервер, называемый прокси-сервером обнаружения, содержащий сведения о доступных службах. Этот прокси-сервер обнаружения может быть наполнен сведениями о службах несколькими способами. Например, службы могут отправлять при запуске сообщения объявления прокси-серверу обнаружения или же прокси-сервер может считывать данные из базы данных или файла конфигурации для определения доступных служб. Метод заполнения прокси-сервера обнаружения определяется разработчиком. Клиенты используют прокси-сервер обнаружения для получения сведений о доступных службах. Когда клиент выполняет поиск службы, он отправляет сообщение `Probe` прокси-серверу обнаружения, а тот определяет, соответствуют ли известные ему службы той службе, которую ищет клиент. Если совпадения присутствуют, прокси-сервер обнаружения отправляет клиенту ответ `ProbeMatch`. Затем клиент может связаться со службой напрямую, используя сведения о службе, возвращенные прокси-сервером. Основной принцип управляемого режима - отправка запросов обнаружения в одноадресном режиме одному прокси-серверу обнаружения. Платформа .NET Framework содержит ключевые компоненты, позволяющие создавать собственные прокси-серверы. Клиенты и службы могут находить прокси-сервер несколькими способами.  
  
- Прокси-сервер может отвечать на нерегламентированные сообщения.  
  
- Прокси-сервер может отправлять сообщение объявления при запуске.  
  
- Клиенты и службы могут быть настроены на поиск определенной известной конечной точки.  
  
 В нерегламентированном режиме централизованного сервера не существует. Все сообщения обнаружения, например объявления служб и запросы клиентов, отправляются многоканально. По умолчанию платформа .NET Framework поддерживает нерегламентированное обнаружение по протоколу UDP. Например, если служба настроена на отправку объявления «Hello» при запуске, она отправит его по известному множеству адресов с использованием протокола UDP. Клиенты должны активно прослушивать данные объявления и проводить их обработку необходимым образом. Если клиент отправляет сообщение `Probe` службе, то оно отправляется по сети с использованием многоканального протокола. Каждая получившая запрос служба определяет, соответствует ли она критериям в сообщении `Probe`, и напрямую отвечает клиенту сообщением `ProbeMatch` в случае, если служба соответствует критериям из сообщения `Probe`.  
  
## <a name="benefits-of-using-wcf-discovery"></a>Преимущества использования обнаружения WCF  
 Поскольку обнаружение WCF реализуется с использованием протокола WS-Discovery, оно может взаимодействовать с другими клиентами, службами и прокси-серверами, которые также реализуют протокол WS-Discovery. Обнаружение WCF построено на основе существующих API WCF, что облегчает добавление функциональных возможностей обнаружения в существующие службы и клиенты. Возможность обнаружения служб может быть легко добавлена через настройки конфигурации приложения. Кроме того, обнаружение WCF также поддерживает использование протокола обнаружения с другими видами транспорта, такими как одноранговая сеть, перекрытие имен и HTTP. Обнаружение WCF поддерживает использование управляемого режима работы с использованием прокси-сервера обнаружения. Это может снизить сетевой трафик, поскольку сообщения отправляются напрямую на прокси-сервер обнаружения, а не рассылаются многоканально по всей сети. Обнаружение WCF также обеспечивает большую гибкость при работе с веб-службами. Например, можно изменить адрес службы без изменения настройки клиента или службы. Если клиент должен получить доступ к службе, он может отправить сообщение `Probe` с помощью запроса `Find`, при этом служба вышлет ответ на его текущий адрес. Обнаружение WCF позволяет клиентам выполнять поиск служб, основываясь на различных критериях, включая типы контрактов, элементы привязки, пространство имен, область, ключевые слова и номера версий. Обнаружение WCF позволяет выполнять обнаружение во время разработки и во время выполнения. Добавленное в приложение обнаружение может быть использовано для включения других сценариев, например отказоустойчивости или автоматической настройки.  
  
## <a name="service-publication"></a>Публикация службы  
 Чтобы сделать службу доступной для обнаружения, необходимо добавить объект <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> в узел службы, а также добавить конечную точку обнаружения для указания того, где следует прослушивать сообщения обнаружения. В следующем примере кода показано, как можно изменить резидентную службу, сделав ее доступной для обнаружения.  
  
```csharp  
Uri baseAddress = new Uri($"http://{System.Net.Dns.GetHostName()}:8000/discovery/scenarios/calculatorservice/{Guid.NewGuid().ToString()}/");

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
 Чтобы сделать службу доступной для обнаружения, необходимо добавить экземпляр <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> в описание службы. В узел службы нужно добавить экземпляр <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>, чтобы сообщить службе, где следует выполнять прослушивание запросов обнаружения. В данном примере добавляется объект <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (производный от <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>), используемый для настройки службы на прослушивание запросов обнаружения через многоканальный транспорт UDP. При использовании нерегламентированного обнаружения используется <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, поскольку все сообщения отправляются многоканально.  
  
## <a name="announcement"></a>Замечание  
 По умолчанию при публикации службы сообщения оповещения не рассылаются. Службу нужно настроить для отправки сообщений оповещения. Это предоставляет разработчикам служб дополнительную гибкость, поскольку можно объявить службу отдельно от прослушивания сообщений обнаружения. Объявления служб также могут быть использованы в качестве механизма регистрации служб на прокси-сервере обнаружения или в других службах. В следующем коде показывается, как можно настроить службу для отправки сообщений с объявлениями по привязке UDP.  
  
```csharp  
Uri baseAddress = new Uri($"http://{System.Net.Dns.GetHostName()}:8000/discovery/scenarios/calculatorservice/{Guid.NewGuid().ToString()}/");

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    ServiceDiscoveryBehavior discoveryBehavior = new ServiceDiscoveryBehavior();
    serviceHost.Description.Behaviors.Add(discoveryBehavior);

    // Send announcements on UDP multicast transport
    discoveryBehavior.AnnouncementEndpoints.Add(
      new UdpAnnouncementEndpoint());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.Description.Endpoints.Add(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
## <a name="service-discovery"></a>Обнаружение служб  
 Клиентское приложение может использовать класс <xref:System.ServiceModel.Discovery.DiscoveryClient> для поиска служб. Разработчик создает экземпляр класса <xref:System.ServiceModel.Discovery.DiscoveryClient>, передающего конечную точку обнаружения, указывающую, куда следует отправлять сообщения `Probe` или `Resolve`. После этого клиент вызывает метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, задающий критерии поиска в экземпляре <xref:System.ServiceModel.Discovery.FindCriteria>. Если соответствующие службы найдены, метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> возвращает коллекцию <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>. В следующем примере кода показывается, как вызвать метод `Find` и установить соединение с найденной службой.  
  
```csharp  
class Client
{
    static EndpointAddress serviceAddress;
  
    static void Main()
    {  
        if (FindService()) 
        {
            InvokeService();
        }
    }  
  
    // ** DISCOVERY ** //  
    static bool FindService()  
    {  
        Console.WriteLine("\nFinding Calculator Service ..");  
        DiscoveryClient discoveryClient =   
            new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
        Collection<EndpointDiscoveryMetadata> calculatorServices =   
            (Collection<EndpointDiscoveryMetadata>)discoveryClient.Find(new FindCriteria(typeof(ICalculator))).Endpoints;  
  
        discoveryClient.Close();  
  
        if (calculatorServices.Count == 0)  
        {  
            Console.WriteLine("\nNo services are found.");  
            return false;  
        }  
        else  
        {  
            serviceAddress = calculatorServices[0].Address;  
            return true;  
        }  
    }  
  
    static void InvokeService()  
    {  
        Console.WriteLine("\nInvoking Calculator Service at {0}\n", serviceAddress);  
  
        // Create a client  
        CalculatorClient client = new CalculatorClient();  
        client.Endpoint.Address = serviceAddress;  
        client.Add(10,3);  
    }
}  
```  
  
## <a name="discovery-and-message-level-security"></a>Обнаружение и безопасность на уровне сообщения  
 При использовании безопасности на уровне сообщения необходимо указать идентификатор <xref:System.ServiceModel.EndpointIdentity> конечной точки обнаружения службы и соответствующий идентификатор <xref:System.ServiceModel.EndpointIdentity> конечной точки обнаружения клиента. Дополнительные сведения о безопасности на уровне сообщений см. в разделе [безопасность сообщений](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
## <a name="discovery-and-web-hosted-services"></a>Обнаружение и службы, размещенные на веб-сайтах  
 Чтобы службы WCF могли быть обнаружены, они должны выполняться. Службы WCF, размещенные на серверах IIS и WAS, не выполняются, пока сервер IIS/WAS не получит сообщение, привязанное к службе, и, следовательно, не могут быть обнаружены по умолчанию.  Сделать службы, размещаемые на веб-сайтах, обнаруживаемыми можно двумя способами:  
  
1. С помощью возможности автозапуска фабрики приложений Windows Server  
  
2. С помощью прокси-сервера обнаружения для установления связи от имени службы  
  
 В фабрике приложений Windows Server имеется возможность автозапуска, которая позволяет службе запускаться до получения сообщений. С помощью параметра автозапуска службу, размещенную в службах IIS/WAS, можно настроить для обнаружения. Дополнительные сведения о функции автоматического запуска см. в разделе [функция автоматического запуска Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677260(v=azure.10)). Одновременно с включением возможности автозапуска необходимо настроить службу для обнаружения. Дополнительные сведения см. в разделе [как программно добавить возможность обнаружения в службу WCF и клиент](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[Настройка обнаружения в файле конфигурации](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md).  
  
 Прокси-сервер обнаружения может использоваться для связи от имени службы WCF, когда служба не выполняется. Прокси-сервер может прослушивать входящие сообщения или сообщения разрешения и отвечать клиенту. Клиент может затем отправлять сообщения непосредственно службе. При отправке клиентом сообщения службе она будет запущена для ответа на сообщение. Дополнительные сведения о реализации прокси-сервера обнаружения см. в разделе [Реализация прокси-сервера обнаружения](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md).  
  
> [!NOTE]
> Для правильной работы обнаружения WCF все сетевые карты (контроллер сетевого интерфейса) должны иметь только один IP-адрес.
