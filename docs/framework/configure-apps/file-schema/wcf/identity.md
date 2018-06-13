---
title: '&lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 9cfd1d6cc7c278fd7e95c13df0a6f801cfabbc33
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749170"
---
# <a name="ltidentitygt"></a>&lt;identity&gt;
Элемент identity позволяет разработчику клиента указать во время разработки ожидаемое удостоверение службы. Во время процесса подтверждения между клиентом и службой инфраструктуру Windows Communication Foundation (WCF) обеспечит удостоверения ожидаемой службы совпадений значения этого элемента и таким образом могут проходить проверку подлинности. Дополнительные сведения см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<система. ServiceModel >  
\<Клиент >  
\<Конечная точка >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|certificate|Задает параметры сертификата X.509. Это элемент типа <xref:System.ServiceModel.Configuration.CertificateElement>. Он содержит атрибут `encodedValue`, являющийся строкой, указывающей значение, зашифрованное с помощью этого сертификата.|  
|certificateReference|Задает параметры для проверки сертификата X.509. Это элемент типа <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Задает службу DNS-сертификата X.509, используемого для проверки подлинности службы. Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.|  
|rsa|Задает значение поля RSA сертификата X.509, используемое для проверки подлинности службы для клиента. Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.|  
|servicePrincipalName|Задает удостоверение имени участника-сервера, являющегося именем участника, используемым клиентом для уникальной идентификации экземпляра службы. Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника. Это элемент типа <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Задает удостоверение имени участника-пользователя, являющегося именем входа пользователя в сеть. Имя участника-пользователя состоит из имени объекта пользователя, используемого в Active Directory, за которым следует символ (@), а затем обычно следует родительский домен службы доменных имен. Например, у Джефа в дереве домена Fabrikam.com может быть имя участника-пользователя [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника. Это элемент типа <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<custom>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|Задает настраиваемый одноранговый распознаватель для netPeerTcpBinding.|  
|[\<Конечная точка >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)|Настраивает разные типы конечных точек.|  
|[\<issuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|Задает службу маркеров безопасности для федеративной службы.|  
|[\<issuerMetadata >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|Задает конечную точку метаданных для службы маркеров безопасности федеративной службы.|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Задает параметры для выданного маркера в настраиваемой привязке.|  
|[\<localIssuer >](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Задает локальную службу маркеров безопасности.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Конечные точки: адреса, привязки и контракты](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
