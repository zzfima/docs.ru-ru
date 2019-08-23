---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c1d3662b2ceda83eb32abe99244e926332214698
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931325"
---
# <a name="messagesenderauthentication"></a>\<Мессажесендераусентикатион >
Задает параметры проверки подлинности для однорангового сертификата, используемого отправителем сообщения.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<serviceCredentials >  
\<Одноранговые >  
\<Мессажесендераусентикатион >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`certificateValidationMode`|Необязательное перечисление. Задает один из пяти режимов для проверки учетных данных. Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.|  
|`customCertificateValidatorType`|Необязательная строка. Задает тип и сборку, используемые для проверки пользовательского типа. Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`. Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) предоставляет средство проверки однорангового сертификата по умолчанию, которое проверяет одноранговый сертификат в хранилище доверенных лиц. Он также проверяет цепочку сертификатов вплоть до действительного корня. Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.|  
|`revocationMode`|Необязательное перечисление. Задает режим отзыва сертификатов. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов. Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва. Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.|  
|`trustedStoreLocation`|Необязательное перечисление. Указывает расположение доверенного хранилища, в котором система безопасности WCF проверяет сертификат однорангового узла. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Одноранговые >](peer-of-servicecredentials.md)|Задает текущие учетные данные для однорангового узла.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения. Для выходных каналов каждое сообщение подписывается с помощью сертификата, [ \<](certificate-element.md)предоставленного сертификатом >. Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента. Модуль проверки может принять или отклонить учетные данные.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Одноранговая сеть](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md)
