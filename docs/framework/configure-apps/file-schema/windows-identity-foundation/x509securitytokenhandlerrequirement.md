---
title: "&lt;x509SecurityTokenHandlerRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# &lt;x509SecurityTokenHandlerRequirement&gt;
Предоставляет дополнительную конфигурацию для класса или производных классов <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
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
|certificateValidationMode|Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode>, которое указывает режим, используемый для проверки сертификата X.509.  Значение по умолчанию "PeerOrChainTrust".|  
|mapToWindows|Указывает, должен ли обработчик токена сопоставления маркер проверки для учетной записи Windows с помощью входящего утверждения имени участника\-пользователя.  Значение по умолчанию \- "false".|  
|revocationMode|Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>, указывающее режим отзыва для сертификата X.509.  Значение по умолчанию "подключения".|  
|trustedStoreLocation|Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation>, определяющее хранилище сертификатов X.509.  Значение по умолчанию \-LocalMachine".|  
|certificateValidator|Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  Если атрибут `certificateValidationMode` "custom", то экземпляр этого типа используется для проверки сертификата издателя.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков токена.|  
  
## Пример  
  
```  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```