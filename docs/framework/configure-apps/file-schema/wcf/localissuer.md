---
title: '&lt;localIssuer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8836d9e57dd7c4d9cfdc20c5e4856e384e6d67b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltlocalissuergt"></a>&lt;localIssuer&gt;
Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.  
  
 \<система. ServiceModel >  
\<поведения >  
раздел endpointBehaviors  
\<поведение >  
\<clientCredentials >  
\<issuedToken >  
\<localIssuer >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|address|Обязательная строка. Указывает универсальный код ресурса (URI) локального издателя.|  
|привязка|Необязательная строка. Одна из привязок, предоставляемых системой. Список см. в разделе [привязка, предоставляемая системой](../../../../../docs/framework/wcf/system-provided-bindings.md).|  
|bindingConfiguration|Необязательная строка. Указывает конфигурацию привязки в файле конфигурации.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Указывает идентификационные данные для локального издателя.|  
|[\<заголовки >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю. Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<issuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 При получении маркера от службы маркеров безопасности (STS) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS. Если <xref:System.ServiceModel.WSFederationHttpBinding> не предоставляет URL-адрес для службы маркеров безопасности или адрес издателя федеративной привязки - http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous или `null`, канал [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] клиента использует для обмена данными с STS и получения маркера значения, указанные параметрами `address` и `binding`. Дополнительные сведения о настройке локального издателя см. в разделе [как: Настройка локального издателя](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="example"></a>Пример  
 В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Как: Настройка локального издателя](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)  
 [Как: создание федеративного клиента](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
