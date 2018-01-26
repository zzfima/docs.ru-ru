---
title: '&lt;endpointExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47aad13591e3a35433cafea3e49fff7fa6e7b7c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltendpointextensionsgt"></a>&lt;endpointExtensions&gt;
Этот раздел регистрирует новую стандартную конечную точку в разделе расширений файла конфигурации компьютера или приложения. Добавить стандартную конечную точку в эту коллекцию можно, используя ключевое слово `add`, а также присвоив атрибуту `type` элемента значение, соответствующее типу конечной точки, а атрибуту `name` - имя стандартной конечной точки.  
  
 В следующем примере элемент `add` и атрибут `name` используются для добавления стандартной конечной точки в раздел `<endpointExtensions>` файла конфигурации.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <endpointExtensions>  
           <add name="udpDiscoveryEndpoint"  
                type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
        </endpointExtensions>   
    </extensions>  
</system.serviceModel>  
```  
  
 После регистрации стандартной конечной точки ее можно использовать, как показано в следующем примере. В [ \<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент, `kind` атрибут указывает тип стандартной конечной точки, который был зарегистрирован в `<endpointExtensions>` раздела. `endpointConfiguration` Атрибут будет идентична `name` атрибута элемента конфигурации стандартной конечной точки в `<standardEndpoints>` раздела.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Service1">  
        <endpoint kind="udpDiscoveryEndpoint"  
                  endpointConfiguration="udpConfig" />  
      </service>  
    </services>  
    <standardEndpoints>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
                  name="udpConfig"  
                  multicastAddress="soap.udp://239.255.255.250:3703"  
                  ... />  
      </udpDiscoveryEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```
