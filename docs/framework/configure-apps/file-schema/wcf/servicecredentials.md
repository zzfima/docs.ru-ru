---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399661"
---
# <a name="servicecredentials"></a>\<serviceCredentials >
Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCredentials >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`type`|Строка, задающая тип данного элемента конфигурации.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCertificate >](clientcertificate-of-servicecredentials.md)|Задает сертификат для использования, когда сертификат клиента доступен внештатно. Этот элемент также задает параметры проверки сертификата клиента. Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.|  
|[\<Иссуедтокенаусентикатион >](issuedtokenauthentication-of-servicecredentials.md)|Задает для этой службы текущий выданный маркер. Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.|  
|[\<Одноранговые >](peer-of-servicecredentials.md)|Задает текущие учетные данные для однорангового узла. Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<Секуреконверсатионаусентикатион >](secureconversationauthentication-of-servicecredential.md)|Задает текущие учетные данные для безопасного сеанса. Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.|  
|[\<serviceCertificate >](servicecertificate-of-servicecredentials.md)|Задает сертификат, используемый службой для своей идентификации. Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.|  
|[\<Усернамеаусентикатион >](usernameauthentication.md)|Задает параметры для проверки имени пользователя и пароля. Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.|  
|[\<windowsAuthentication >](windowsauthentication-of-servicecredentials.md)|Задает параметры для проверки учетных данных ОС Windows. Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> поведения](behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
