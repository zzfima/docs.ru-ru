---
title: <peer> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933778"
---
# <a name="peer-of-servicecredentials"></a>\<Одноранговая \<> > ServiceCredentials
Задает текущие учетные данные для однорангового узла.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<serviceCredentials >  
\<Одноранговые >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> сертификата](certificate-of-peer.md)|Задает сертификат X.509, используемый для подписи и шифрования сообщений для служб одноранговых сетей. .|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|Задает параметры проверки подлинности для отправителей сообщений.|  
|[\<peerAuthentication>](peerauthentication.md)|Задает параметры проверки подлинности для одноранговых служб.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCredentials >](servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [Одноранговая сеть](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
