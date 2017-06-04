---
title: "&lt;localIssuer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;localIssuer&gt;
Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.  
  
## Синтаксис  
  
```  
  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|address|Обязательная строка.  Указывает универсальный код ресурса \(URI\) локального издателя.|  
|привязка|Необязательная строка.  Одна из привязок, предоставляемых системой.  Список см. в разделе [Привязки, предоставляемые системой](../../../../../docs/framework/wcf/system-provided-bindings.md).|  
|bindingConfiguration|Необязательная строка.  Указывает конфигурацию привязки в файле конфигурации.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Указывает идентификационные данные для локального издателя.|  
|[\<верхние колонтитулы\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю.  Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<issuedToken\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.|  
  
## Заметки  
 При получении маркера от службы маркеров безопасности \(STS\) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS.  Если <xref:System.ServiceModel.WSFederationHttpBinding> не предоставляет URL\-адрес для службы маркеров безопасности или адрес издателя федеративной привязки \- http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous или `null`, канал [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] клиента использует для обмена данными с STS и получения маркера значения, указанные параметрами `address` и `binding`.  Дополнительные сведения о настройке локального издателя см. в разделе [Как настраивать локальный издатель](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## Пример  
 В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.  
  
```  
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
  
## См. также  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>   
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Как настраивать локальный издатель](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)   
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Как создавать федеративный клиент](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)