---
title: '&lt;endpointExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 3883a23c679abc83d7cfe9011b7cdb7e4154adfe
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146450"
---
# <a name="ltendpointextensionsgt"></a><span data-ttu-id="d0281-102">&lt;endpointExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="d0281-102">&lt;endpointExtensions&gt;</span></span>
<span data-ttu-id="d0281-103">Этот раздел регистрирует новую стандартную конечную точку в разделе расширений файла конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="d0281-103">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="d0281-104">Добавить стандартную конечную точку в эту коллекцию можно, используя ключевое слово `add`, а также присвоив атрибуту `type` элемента значение, соответствующее типу конечной точки, а атрибуту `name` - имя стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d0281-104">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="d0281-105">В следующем примере элемент `add` и атрибут `name` используются для добавления стандартной конечной точки в раздел `<endpointExtensions>` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d0281-105">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="d0281-106">После регистрации стандартной конечной точки ее можно использовать, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d0281-106">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="d0281-107">В [ \<конечной точки >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент, `kind` атрибут указывает тип стандартной конечной точки, зарегистрированной в `<endpointExtensions>` разделе.</span><span class="sxs-lookup"><span data-stu-id="d0281-107">In the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="d0281-108">`endpointConfiguration` Атрибут будет идентична `name` атрибута элемента конфигурации стандартной конечной точки в `<standardEndpoints>` разделе.</span><span class="sxs-lookup"><span data-stu-id="d0281-108">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
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
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
