---
title: '&lt;add&gt; для &lt;issuerChannelBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 072e3f4e961f6bf45e7c8b48c64cda36d385cf2b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149544"
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;add&gt; для &lt;issuerChannelBehaviors&gt;
Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.  
  
> [!NOTE]
>  Если все поведения конечной точки содержит [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент, будет создано исключение.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
раздел endpointBehaviors  
\<поведение >  
\<clientCredentials >  
\<issuedToken >  
\<issuerChannelBehaviors > элемент  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|issuerAddress|Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.|  
|behaviorConfiguration|Имя поведения конечной точки, определенное в том же файле конфигурации.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с заданными службами маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 `issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными. `behaviorConfiguration` Указывает поведение конечной точки, приложение использует в каналах, созданных в Windows Communication Foundation (WCF) для получения маркеров, выданных из службы маркеров безопасности.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)  
 [Практическое руководство. Создание федеративного клиента](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Практическое руководство. Настройка локального издателя](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
