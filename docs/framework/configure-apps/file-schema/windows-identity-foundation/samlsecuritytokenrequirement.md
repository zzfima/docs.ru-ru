---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942492"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurityTokenRequirement>
Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов. Представляется <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
\<samlSecurityTokenRequirement>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|mapToWindows|Указывает, должен ли обработчик маркера сопоставлять проверяющий токен с учетной записью Windows, используя входящее утверждение имени участника-пользователя. Значение по умолчанию — false.|  
|иссуерцертификатеревокатионмоде|Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> типа, указывающее режим отзыва, используемый для сертификата X. 509. Значение по умолчанию — "Online".|  
|иссуерцертификатевалидатионмоде|Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode> типа, указывающее режим проверки, используемый для сертификата X. 509. Значение по умолчанию — "PeerOrChainTrust".|  
|иссуерцертификатетрустедсторелокатион|Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> типа, указывающее хранилище сертификатов X. 509. Значение по умолчанию — LocalMachine.|  
|иссуерцертификатевалидатор|Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>. `issuerCertificateValidationMode` Если атрибут имеет значение Custom, для проверки сертификата издателя используется экземпляр этого типа.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Намеклаимтипе >](nameclaimtype.md)|Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.|  
|[\<Ролеклаимтипе >](roleclaimtype.md)|Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add.md)|Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> `SamlSecurityTokenRequirement` Элемент представлен <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом в объектной модели и используется для настройки свойства в или. `<samlSecurityTokenRequirement>`  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
