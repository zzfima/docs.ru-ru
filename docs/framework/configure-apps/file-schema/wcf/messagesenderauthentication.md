---
title: '&lt;messageSenderAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 656543ee1908c8fa332e373863aa4dc7ddecaba7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagesenderauthenticationgt"></a>&lt;messageSenderAuthentication&gt;
Задает параметры проверки подлинности для однорангового сертификата, используемого отправителем сообщения.  
  
 \<система. ServiceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceCredentials >  
\<Одноранговый >  
\<messageSenderAuthentication >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`certificateValidationMode`|Необязательное перечисление. Задает один из пяти режимов для проверки учетных данных. Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.|  
|`customCertificateValidatorType`|Необязательная строка. Задает тип и сборку, используемые для проверки пользовательского типа. Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`. Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) предоставляет используемый по умолчанию сертификат проверки, проверит, этот сертификат в хранилище доверенных лиц. Он также проверяет цепочку сертификатов вплоть до действительного корня. Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.|  
|`revocationMode`|Необязательное перечисление. Задает режим отзыва сертификатов. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов. Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва. Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.|  
|`trustedStoreLocation`|Необязательное перечисление. Задает расположение доверенного хранилища, где одноранговый сертификат проверяется системой безопасности [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Одноранговый >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Задает текущие учетные данные для однорангового узла.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения. Для вывода каналов, каждое сообщение подписывается с помощью сертификата, предоставляемого [ \<сертификата >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md). Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента. Модуль проверки может принять или отклонить учетные данные.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Проверка подлинности сообщения одноранговых каналов](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Нестандартная проверка подлинности одноранговых каналов](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
