---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 0f5eace346fd0ed2c0532fb602585c4593d97291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220361"
---
# <a name="identity"></a>\<удостоверение >
Элемент identity позволяет разработчику клиента указать во время разработки ожидаемое удостоверение службы. Во время процесса подтверждения между клиентом и службой инфраструктуре Windows Communication Foundation (WCF) гарантирует, что удостоверение соответствует ожидаемой службы значения этого элемента и таким образом могут проходить проверку подлинности. Дополнительные сведения см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<system.ServiceModel>  
\<Клиент >  
\<endpoint>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <usePrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|сертификат|Задает параметры сертификата X.509. Это элемент типа <xref:System.ServiceModel.Configuration.CertificateElement>. Он содержит атрибут `encodedValue`, являющийся строкой, указывающей значение, зашифрованное с помощью этого сертификата.|  
|certificateReference|Задает параметры для проверки сертификата X.509. Это элемент типа <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Задает службу DNS-сертификата X.509, используемого для проверки подлинности службы. Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.|  
|rsa|Задает значение поля RSA сертификата X.509, используемое для проверки подлинности службы для клиента. Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.|  
|servicePrincipalName|Задает удостоверение имени участника-сервера, являющегося именем участника, используемым клиентом для уникальной идентификации экземпляра службы. Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника. Это элемент типа <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Задает удостоверение имени участника-пользователя, являющегося именем входа пользователя в сеть. Имя участника-пользователя состоит из имени объекта пользователя, используемого в Active Directory, за которым следует символ at (\@) и затем, как правило, доменных имен родительского домена. Например, у Джефа в дереве домена Fabrikam.com может быть имя участника-пользователя [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника. Это элемент типа <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<пользовательские >](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|Задает настраиваемый одноранговый распознаватель для netPeerTcpBinding.|  
|[\<endpoint>](endpoint-element.md)|Настраивает конечные точки службы.|  
|[\<Конечная точка > из \<клиента >](endpoint-of-client.md)|Настраивает конечными точками канала.|  
|[\<issuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|Задает службу маркеров безопасности для федеративной службы.|  
|[\<issuerMetadata>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|Задает конечную точку метаданных для службы маркеров безопасности федеративной службы.|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Задает параметры для выданного маркера в настраиваемой привязке.|  
|[\<localIssuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Задает локальную службу маркеров безопасности.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Конечные точки: адреса, привязки и контракты](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
