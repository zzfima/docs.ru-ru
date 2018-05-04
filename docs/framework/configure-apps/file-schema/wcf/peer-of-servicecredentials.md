---
title: '&lt;peer&gt;’ для &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: f50c192639df7b7ed35e863821d5b7a8d62f29bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a>&lt;peer&gt;’ для &lt;serviceCredentials&gt;
Задает текущие учетные данные для однорангового узла.  
  
 \<система. ServiceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceCredentials >  
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
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<сертификат >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|Задает сертификат X.509, используемый для подписи и шифрования сообщений для служб одноранговых сетей. .|  
|[\<messageSenderAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|Задает параметры проверки подлинности для отправителей сообщений.|  
|[\<peerAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|Задает параметры проверки подлинности для одноранговых служб.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Проверка подлинности сообщения одноранговых каналов](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Нестандартная проверка подлинности одноранговых каналов](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
