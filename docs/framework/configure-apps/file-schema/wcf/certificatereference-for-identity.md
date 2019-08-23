---
title: <certificateReference> для <identity>
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 49c731b2637c15e0b968d8c2523c51c8e138e7bf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926174"
---
# <a name="certificatereference-for-identity"></a>\<> certificateReference для \<> удостоверений
Задает параметры для проверки сертификата X.509. Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, проверяет, что утверждения, представленные сервером, содержат утверждение удостоверения, используемое для создания этого удостоверения.  
  
 \<> удостоверений  
\<certificateReference >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<certificateReference findValue="String"
                      isChainIncluded="Boolean"
                      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                      storeLocation="LocalMachine/CurrentUser"
                      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier">
</certificateReference>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|findValue|Задает значение для поиска в хранилище сертификатов X.509. Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `X509FindType`. Значение по умолчанию — пустая строка.|  
|isChainIncluded|Логическое значение, определяющее, выполнена ли проверка с использованием цепочки сертификатов.|  
|storeLocation|Задает расположение хранилища сертификатов, которое клиент может использовать для проверки сертификата сервера.<br /><br /> Допустимы следующие значения:<br /><br /> LocalMachine Хранилище сертификатов, назначенное локальному компьютеру.<br />CurrentUser Хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию - LocalMachine.<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Задает имя открываемого хранилища сертификатов X.509.<br /><br /> Допустимы следующие значения:<br /><br /> AddressBook Хранилище сертификатов для других пользователей.<br />-Аусрут: Хранилище сертификатов для сторонних центров сертификации (ЦС).<br />CertificateAuthority Хранилище сертификатов для промежуточных ЦС.<br />Запрещено Хранилище сертификатов для отозванных сертификатов.<br />Мне Хранилище сертификатов для личных сертификатов.<br />Корневой Хранилище сертификатов для доверенных корневых центров сертификации.<br />TrustedPeople Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-Трустедпублишер: Хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию - «My».<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Определяет тип выполняемого поиска X.509. Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Допустимы следующие значения:<br /><br /> -(FindByThumbprint<br />-FindBySubjectName<br />-Финдбисубжектдистингуишеднаме<br />-Финдбиссуернаме<br />-Финдбиссуердистингуишеднаме<br />-Финдбисериалнумбер<br />-Финдбитимевалид<br />-Финдбитименотетвалид<br />-Финдбитемплатенаме<br />-Финдбяппликатионполици<br />-Финдбицертификатеполици<br />-Финдбекстенсион<br />-Финдбикэйусаже<br />-Финдбисубжекткэйидентифиер<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName.<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> удостоверений](identity.md)|Задает параметры, которые обеспечивают проверку подлинности конечной точки другими конечными точками, с которыми происходит обмен сообщениями.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
