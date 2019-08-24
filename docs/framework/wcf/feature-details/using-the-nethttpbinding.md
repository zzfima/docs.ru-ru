---
title: Использование NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 0f908361c5f9152d333daaf5e3ee90de3b1b89e9
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988631"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="876c2-102">Использование NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="876c2-102">Using the NetHttpBinding</span></span>
<span data-ttu-id="876c2-103"><xref:System.ServiceModel.NetHttpBinding> - это привязка, предназначенная для использования служб HTTP или WebSocket и использующая по умолчанию двоичное кодирование.</span><span class="sxs-lookup"><span data-stu-id="876c2-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="876c2-104"><xref:System.ServiceModel.NetHttpBinding> определит, будет ли она использоваться с дуплексным контрактом и контрактом типа «запрос-ответ» и изменит ли свое поведение для соответствия контракту. HTTP будет использоваться для контрактов типа «запрос-ответ», и WebSockets - для дуплексных контрактов.</span><span class="sxs-lookup"><span data-stu-id="876c2-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="876c2-105">Данное поведение можно переопределить с помощью параметра <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:.</span><span class="sxs-lookup"><span data-stu-id="876c2-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <span data-ttu-id="876c2-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always>— Заставляет использовать WebSockets даже для контрактов "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="876c2-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <span data-ttu-id="876c2-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never>— Предотвращается использование WebSockets.</span><span class="sxs-lookup"><span data-stu-id="876c2-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> - This prevents WebSockets from being used.</span></span> <span data-ttu-id="876c2-108">Попытка использования дуплексного контракта с этим параметром приведет к возникновению исключения.</span><span class="sxs-lookup"><span data-stu-id="876c2-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <span data-ttu-id="876c2-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex>— Это значение по умолчанию, которое ведет себя, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="876c2-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="876c2-110"><xref:System.ServiceModel.NetHttpBinding> поддерживает надежные сеансы как в режиме HTTP, так и в режиме WebSocket.</span><span class="sxs-lookup"><span data-stu-id="876c2-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="876c2-111">В режиме WebSocket сеансы предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="876c2-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="876c2-112">При использовании <xref:System.ServiceModel.NetHttpBinding> и в тех случаях, когда TransferMode привязки имеет значение TransferMode.Streamed, большие потоки могут привести к взаимоблокировке, в результате чего будет превышено время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="876c2-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="876c2-113">Чтобы избежать этой проблемы, отправляйте меньшие сообщения или используйте TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="876c2-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="876c2-114">Настройка службы на использование NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="876c2-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="876c2-115">Привязку <xref:System.ServiceModel.NetHttpBinding> можно настроить так же, как и любые другие привязки.</span><span class="sxs-lookup"><span data-stu-id="876c2-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="876c2-116">В следующем фрагменте конфигурации показано, как настроить службу WCF с <xref:System.ServiceModel.NetHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="876c2-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
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
  
 <span data-ttu-id="876c2-117">В следующем фрагменте кода показано, как добавить <xref:System.ServiceModel.NetHttpBinding> в коде.</span><span class="sxs-lookup"><span data-stu-id="876c2-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="876c2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="876c2-118">See also</span></span>

- [<span data-ttu-id="876c2-119">Настройка привязок для служб</span><span class="sxs-lookup"><span data-stu-id="876c2-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="876c2-120">Привязки</span><span class="sxs-lookup"><span data-stu-id="876c2-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)
- [<span data-ttu-id="876c2-121">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="876c2-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="876c2-122">Дуплексные службы</span><span class="sxs-lookup"><span data-stu-id="876c2-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
