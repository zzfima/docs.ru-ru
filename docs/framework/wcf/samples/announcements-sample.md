---
title: Образец замечаний
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: c3824fb0dc7ab4169c309d1a5154127d6bc3b78f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746999"
---
# <a name="announcements-sample"></a>Образец замечаний

Данный образец показывает, как использовать функциональность объявлений возможности обнаружения. Объявления позволяют службам отправлять сообщения объявления, содержащие метаданные службы. По умолчанию отправляется объявление о входе в сеть при запуске службы и объявление о выходе из сети при отключении службы. Эти объявления могут быть многоадресными или отправляться от точки к точке. Этот образец состоит из двух проектов: служба и клиент.

## <a name="service"></a>Служба

Данный проект содержит саморазмещаемую службу калькулятора. В методе `Main` создается узел службы, к которому добавляется конечная точка службы. Далее создается поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>. Чтобы включить объявления, к поведению <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> должна быть добавлена конечная точка объявлений. В случае стандартной конечной точки в качестве конечной точки объявления добавляется многоадресная рассылка UDP. При этом объявления рассылаются через общеизвестный адрес UDP.

```csharp
Uri baseAddress = new Uri("http://localhost:8000/" + Guid.NewGuid().ToString());

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
     serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new WSHttpBinding(), String.Empty);

     ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();

     // Announce the availability of the service over UDP multicast
    serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());

    // Make the service discoverable over UDP multicast.
    serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());
    serviceHost.Open();
    // ...
}
```

## <a name="client"></a>клиент

Обратите внимание, что в данном проекте клиент содержит службу <xref:System.ServiceModel.Discovery.AnnouncementService>. Кроме того, для событий зарегистрировано два делегата. Эти события определяют, что делает клиент при получении объявлений о входе и выходе из сети.

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

Методы `OnOnlineEvent` и `OnOfflineEvent` обслуживают соответственно сообщения объявлений о входе и выходе из сети.

```csharp
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an online announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an offline announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
            PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}
```

#### <a name="to-use-this-sample"></a>Использование этого образца

1. В этом образце используются конечные точки HTTP, и для работы этого образца необходимо добавить соответствующие списки управления доступом по URL-адресу. Дополнительные сведения см. в разделе [Настройка HTTP и HTTPS](../feature-details/configuring-http-and-https.md). Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями. Если команда не работает, следует указать домен и имя пользователя в следующих аргументах. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. Создайте решение.

3. Запустите приложение client.exe.

4. Запустите приложение service.exe. Обратите внимание, что клиент получает объявление о входе в сеть.

5. Закройте приложение service.exe. Обратите внимание, что клиент получает объявление о выходе из сети.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
