---
title: "Образец замечаний"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 045807df433d519b00969812afb0ae2feac94b75
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="announcements-sample"></a>Образец замечаний
Данный образец показывает, как использовать функциональность объявлений возможности обнаружения. Объявления позволяют службам отправлять сообщения объявления, содержащие метаданные службы. По умолчанию отправляется объявление о входе в сеть при запуске службы и объявление о выходе из сети при отключении службы. Эти объявления могут быть многоадресными или отправляться от точки к точке. Этот образец состоит из двух проектов: служба и клиент.  
  
## <a name="service"></a>Служба  
 Данный проект содержит саморазмещаемую службу калькулятора. В методе `Main` создается узел службы, к которому добавляется конечная точка службы. Далее создается поведение <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>. Чтобы включить объявления, к поведению <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> должна быть добавлена конечная точка объявлений. В случае стандартной конечной точки в качестве конечной точки объявления добавляется многоадресная рассылка UDP. При этом объявления рассылаются через общеизвестный адрес UDP.  
  
```  
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
  
## <a name="client"></a>Клиент  
 Обратите внимание, что в данном проекте клиент содержит службу <xref:System.ServiceModel.Discovery.AnnouncementService>. Кроме того, для событий зарегистрировано два делегата. Эти события определяют, что делает клиент при получении объявлений о входе и выходе из сети.  
  
```  
// Create an AnnouncementService instance  
AnnouncementService announcementService = new AnnouncementService();  
  
// Subscribe the announcement events  
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;  
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;  
```  
  
 Методы `OnOnlineEvent` и `OnOfflineEvent` обслуживают соответственно сообщения объявлений о входе и выходе из сети.  
  
```  
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
  
1.  В этом образце используются конечные точки HTTP, и для запуска этого примера, соответствующие URL ACL, необходимо добавить см. в разделе [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) подробные сведения. Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями. Если команда не работает, следует указать домен и имя пользователя в следующих аргументах. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  Постройте решение.  
  
3.  Запустите приложение client.exe.  
  
4.  Запустите приложение service.exe. Обратите внимание, что клиент получает объявление о входе в сеть.  
  
5.  Закройте приложение service.exe. Обратите внимание, что клиент получает объявление о выходе из сети.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`  
  
## <a name="see-also"></a>См. также
