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
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="a2947-102">Использование пользовательской привязки для клиентского канала обнаружения</span><span class="sxs-lookup"><span data-stu-id="a2947-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="a2947-103">При использовании пользовательской привязки к <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> необходимо определить поставщик <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>, который будет создавать экземпляры <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="a2947-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="a2947-104">Создание DiscoveryEndpointProvider</span><span class="sxs-lookup"><span data-stu-id="a2947-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="a2947-105">Отвечает <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> за создание <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> экземпляров по требованию.</span><span class="sxs-lookup"><span data-stu-id="a2947-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="a2947-106">Чтобы определить поставщика конечной точки обнаружения, создайте класс из <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>, переопределив метод <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>, а затем вернув новую конечную точку обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a2947-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="a2947-107">В следующем примере показан процесс создания поставщика конечной точки обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a2947-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
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
  
 <span data-ttu-id="a2947-108">После того как поставщик конечной точки обнаружения определен, можно создать пользовательскую привязку и добавить <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, который содержит ссылки на поставщик конечной точки обнаружения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a2947-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="a2947-109">Для получения дополнительной информации об использовании канала клиента обнаружения [см.](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)</span><span class="sxs-lookup"><span data-stu-id="a2947-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a2947-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a2947-110">See also</span></span>

- [<span data-ttu-id="a2947-111">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="a2947-111">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="a2947-112">Использование клиентского канала обнаружения</span><span class="sxs-lookup"><span data-stu-id="a2947-112">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
