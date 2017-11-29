---
title: "Использование NetHttpBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 56528078895ea7c624afaf716e9a26eabe335d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-nethttpbinding"></a>Использование NetHttpBinding
<xref:System.ServiceModel.NetHttpBinding> - это привязка, предназначенная для использования служб HTTP или WebSocket и использующая по умолчанию двоичное кодирование. <xref:System.ServiceModel.NetHttpBinding> определит, будет ли она использоваться с дуплексным контрактом и контрактом типа «запрос-ответ» и изменит ли свое поведение для соответствия контракту. HTTP будет использоваться для контрактов типа «запрос-ответ», и WebSockets - для дуплексных контрактов. Это поведение можно переопределить с помощью <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` параметр:  
  
1.  Always - это обеспечивает использование службы WebSockets даже для контрактов типа «запрос-ответ».  
  
2.  Never - это исключает использование службы WebSockets. Попытка использования дуплексного контракта с этим параметром приведет к возникновению исключения.  
  
3.  WhenDuplex - это значение по умолчанию, данное поведение работает способом, описанным выше.  
  
 <xref:System.ServiceModel.NetHttpBinding> поддерживает надежные сеансы как в режиме HTTP, так и в режиме WebSocket. В режиме WebSocket сеансы предоставляются транспортом.  
  
> [!WARNING]
>  При использовании <xref:System.ServiceModel.NetHttpBinding> и в тех случаях, когда TransferMode привязки имеет значение TransferMode.Streamed, большие потоки могут привести к взаимоблокировке, в результате чего будет превышено время ожидания вызова. Чтобы избежать этой проблемы, отправляйте меньшие сообщения или используйте TransferMode.Buffered.  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a>Настройка службы на использование NetHttpBinding  
 Привязку <xref:System.ServiceModel.NetHttpBinding> можно настроить так же, как и любые другие привязки. В следующем фрагменте конфигурации показано, как настроить службу WCF с <xref:System.ServiceModel.NetHttpBinding>.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    <!- ... -->   
  </system.serviceModel>  
```  
  
 В следующем фрагменте кода показано, как добавить <xref:System.ServiceModel.NetHttpBinding> в коде.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a>См. также  
 [Настройка привязок для служб](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Дуплексные службы](../../../../docs/framework/wcf/feature-details/duplex-services.md)
