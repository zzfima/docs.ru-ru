---
title: "Использование пользовательской привязки для клиентского канала обнаружения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Использование пользовательской привязки для клиентского канала обнаружения
При использовании пользовательской привязки к <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> необходимо определить поставщик <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>, который будет создавать экземпляры <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.  
  
## Создание DiscoveryEndpointProvider  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> отвечает за создание [T:System:ServiceModel.Discovery.DiscoveryEndpoints](assetId:///T:System:ServiceModel.Discovery.DiscoveryEndpoints?qualifyHint=False&amp;autoUpgrade=True) по запросу.Чтобы определить поставщика конечной точки обнаружения, создайте класс из <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>, переопределив метод <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>, а затем вернув новую конечную точку обнаружения.В следующем примере показан процесс создания поставщика конечной точки обнаружения.  
  
```  
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
  
 После того как поставщик конечной точки обнаружения определен, вы можете создать пользовательскую привязку и добавить <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, который содержит ссылки на поставщик конечной точки обнаружения, как показано в следующем примере.  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] об использовании клиентского канала обнаружения см. в разделе [Использование клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).Пример полного кода см. в разделе [Образец элемента привязки для обнаружения](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md).  
  
## См. также  
 [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [Использование клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)   
 [Образец элемента привязки для обнаружения](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)