---
title: "&lt;samlSecurityTokenRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;samlSecurityTokenRequirement&gt;
Предоставляет конфигурацию для класса <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> или производного класса из этих классов.  Представленный классом <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>.  
  
## Синтаксис  
  
```  
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
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|mapToWindows|Указывает, должен ли обработчик токена сопоставления маркер проверки для учетной записи Windows с помощью входящего утверждения имени участника\-пользователя.  Значение по умолчанию \- "false".|  
|issuerCertificateRevocationMode|Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>, указывающее режим отзыва для сертификата X.509.  Значение по умолчанию "подключения".|  
|issuerCertificateValidationMode|Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode>, которое указывает режим, используемый для проверки сертификата X.509.  Значение по умолчанию "PeerOrChainTrust".|  
|issuerCertificateTrustedStoreLocation|Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation>, определяющее хранилище сертификатов X.509.  Значение по умолчанию \-LocalMachine".|  
|issuerCertificateValidator|Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  Если атрибут `issuerCertificateValidationMode` "custom", то экземпляр этого типа используется для проверки сертификата издателя.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<nameClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|Задает тип утверждения, которое указывает свойство <xref:System.Security.Principal.IIdentity.Name%2A>.|  
|[\<roleClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|Определяет утверждение, указывающее роль утверждений типа в коллекции объектов <xref:System.Security.Claims.ClaimsIdentity>, возвращаемых методом <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> обработчика токена.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков токена.|  
  
## Заметки  
 Элемент `<samlSecurityTokenRequirement>` представленный классом <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектной модели и используется для настройки свойства `SamlSecurityTokenRequirement` на <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> или <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.  
  
## Пример  
  
```  
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