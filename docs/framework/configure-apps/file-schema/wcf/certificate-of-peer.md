---
title: "&lt;certificate&gt; для &lt;peer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1449bab5d585183d73da5ca0d2234857d9d92151
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltcertificategt-of-ltpeergt"></a>&lt;certificate&gt; для &lt;peer&gt;
Задает сертификат, используемый одноранговым узлом.  
  
 \<system.ServiceModel>  
\<поведения >  
\<serviceBehaviors>  
\<поведение >  
\<serviceCredentials>  
\<Одноранговый >  
\<сертификат >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509. Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`. Значение по умолчанию - пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла. Допустимы следующие значения:<br /><br /> -LocalMachine: хранилище сертификатов, назначенные на локальном компьютере.<br />-CurrentUser: хранилище сертификатов, назначенные текущему пользователю.<br /><br /> Значение по умолчанию - LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509. Допустимы следующие значения:<br /><br /> -AddressBook: Хранилище сертификатов для других пользователей.<br />-AuthRoot: Хранилище сертификатов для сторонних центров сертификации (ЦС).<br />-CertificateAuthority: Хранилище сертификатов для промежуточных центров сертификации (ЦС).<br />-Disallowed: Хранилище сертификатов для отозванных сертификатов.<br />-My: Хранилище сертификатов для личных сертификатов.<br />-Root: Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).<br />-TrustedPeople: Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-TrustedPublisher: Хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию - My.|  
|`X509FindType`|Определяет тип поиска сертификата X.509. Допустимы следующие значения:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Задает текущие учетные данные для однорангового узла.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации содержит экземпляр `X509Certificate2`, используемый при проверке подлинности соседей в сетке узлов.  
  
 Дополнительные сведения о программировании одноранговая сеть см. в разделе [-одноранговые сети](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Проверка подлинности сообщения одноранговых каналов](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Нестандартная проверка подлинности одноранговых каналов](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
