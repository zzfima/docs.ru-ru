---
title: Использование NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 5090cfdfeb068acda1e1092e408f3cd747c574c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121021"
---
# <a name="using-the-nethttpbinding"></a>Использование NetHttpBinding
<xref:System.ServiceModel.NetHttpBinding> привязка, предназначенная для работы со службами HTTP или WebSocket и использует по умолчанию двоичное кодирование. <xref:System.ServiceModel.NetHttpBinding> Определяет, используется ли он с помощью контракта типа запрос ответ или дуплексного контракта и изменить его поведение в соответствии с-для дуплексных контрактов HTTP будет использоваться для контрактов типа запрос ответ и WebSockets. Данное поведение можно переопределить с помощью параметра <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:.  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> -Это обеспечивает использование службы WebSockets даже для контрактов типа запрос ответ.  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> -Это предотвращает использование WebSockets. Попытка использования дуплексного контракта с этим параметром приведет к возникновению исключения.  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> -Это значение по умолчанию и ведет себя так, как описано выше.  
  
 <xref:System.ServiceModel.NetHttpBinding> поддерживает надежные сеансы в режиме HTTP, так и в режиме WebSocket. В режиме WebSocket сеансы предоставляются транспортом.  
  
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
    ...
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

- [Настройка привязок для служб](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)
- [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Дуплексные службы](../../../../docs/framework/wcf/feature-details/duplex-services.md)
