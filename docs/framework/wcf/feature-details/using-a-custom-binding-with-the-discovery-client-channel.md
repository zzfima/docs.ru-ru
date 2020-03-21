---
title: Использование пользовательской привязки для клиентского канала обнаружения
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: 5f3f5fe24d1f19ce503b793d9aad870d882c7971
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184291"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a>Использование пользовательской привязки для клиентского канала обнаружения
При использовании пользовательской привязки к <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> необходимо определить поставщик <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>, который будет создавать экземпляры <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.  
  
## <a name="creating-a-discoveryendpointprovider"></a>Создание DiscoveryEndpointProvider  
 Отвечает <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> за создание <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> экземпляров по требованию. Чтобы определить поставщика конечной точки обнаружения, создайте класс из <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>, переопределив метод <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>, а затем вернув новую конечную точку обнаружения. В следующем примере показан процесс создания поставщика конечной точки обнаружения.  
  
```csharp
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 После того как поставщик конечной точки обнаружения определен, можно создать пользовательскую привязку и добавить <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, который содержит ссылки на поставщик конечной точки обнаружения, как показано в следующем примере.  
  
```csharp
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 Для получения дополнительной информации об использовании канала клиента обнаружения [см.](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Использование клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
