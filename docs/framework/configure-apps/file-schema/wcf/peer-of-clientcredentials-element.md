---
title: '&lt;peer&gt; элемент для элемента &lt;clientCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 9d64f682f67dcc7c4f0c0f1600938f8ff9ac0dd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a>&lt;peer&gt; элемент для элемента &lt;clientCredentials&gt;
Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.  
  
 \<система. ServiceModel >  
\<поведения >  
\<endpointBehaviors >  
\<поведение >  
\<clientCredentials >  
\<Одноранговый >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<сертификат >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей. .|  
|[\<peerAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|Задает параметры проверки подлинности для одноранговых клиентов.|  
|[\<messageSenderAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|Задает параметры проверки подлинности для отправителей сообщений.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов. Дополнительные сведения см. в разделе [проверки подлинности сообщения однорангового канала](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) и [защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)  
 [Проверка подлинности сообщения одноранговых каналов](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Нестандартная проверка подлинности одноранговых каналов](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
