---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152636"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurityTokenRequirement>
Обеспечивает конфигурацию <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> для <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, класса или производного класса любого из этих классов. Представлено классом. <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|mapToWindows|Уточняется, следует ли обработчику маркеров отображения токена проверки в учетную запись Windows с помощью входящего требования UPN. Значение по умолчанию — «false».|  
|эмитентCertificateRevocationMode|Значение, <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> оговариваев режим отзыва для использования для сертификата X.509. Значение по умолчанию "Онлайн".|  
|issuerCertificateValidationMode|Значение, <xref:System.ServiceModel.Security.X509CertificateValidationMode> опознавававававрежим проверки для использования для сертификата X.509. Значение по умолчанию — «PeerOrChainTrust».|  
|issuerCertificateTrustedStoreLocation|Значение, <xref:System.Security.Cryptography.X509Certificates.StoreLocation> опоедая магазин сертификатов X.509. Значение по умолчанию — «LocalMachine».|  
|эмитентCertificateValidator|Пользовательский тип, который <xref:System.IdentityModel.Selectors.X509CertificateValidator>происходит от . Если `issuerCertificateValidationMode` атрибут является "Custom", экземпляр этого типа используется для проверки сертификата эмитента.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|Устанавливает тип претензии, который <xref:System.Security.Principal.IIdentity.Name%2A> определяет свойство.|  
|[\<roleClaimType>](roleclaimtype.md)|Определяет тип претензии, определяющий требования типа роли <xref:System.Security.Claims.ClaimsIdentity> в сборе <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> объектов, возвращенных методом обработчика маркеров.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<добавить>](add.md)|Добавляет указанный обработчик маркеров безопасности в коллекцию обработчика маркеров.|  
  
## <a name="remarks"></a>Remarks  
 Элемент `<samlSecurityTokenRequirement>` представлен <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом в модели объекта и используется для `SamlSecurityTokenRequirement` настройки <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> свойства <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>на или .  
  
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
