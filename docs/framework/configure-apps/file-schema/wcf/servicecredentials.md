---
title: '&lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: a3d63e3d01c009834717a80a9ed9536fd1bdf838
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750405"
---
# <a name="ltservicecredentialsgt"></a>&lt;serviceCredentials&gt;
Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.  
  
 \<система. ServiceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceCredentials >  
  
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
|[\<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|Задает сертификат для использования, когда сертификат клиента доступен внештатно. Этот элемент также задает параметры проверки сертификата клиента. Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.|  
|[\<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|Задает для этой службы текущий выданный маркер. Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.|  
|[\<Одноранговый >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Задает текущие учетные данные для однорангового узла. Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<secureConversationAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|Задает текущие учетные данные для безопасного сеанса. Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|Задает сертификат, используемый службой для своей идентификации. Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.|  
|[\<userNameAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|Задает параметры для проверки имени пользователя и пароля. Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.|  
|[\<windowsAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|Задает параметры для проверки учетных данных ОС Windows. Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
