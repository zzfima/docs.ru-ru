---
title: "&lt;certificateValidation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateValidation&gt;
Отслеживает параметры, обработчики токена используется для проверки сертификатов.  Эти параметры переопределяются если определенный обработчик настроен с собственным проверяющим элементом управления.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|certificateValidationMode|Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode>, которое указывает режим, используемый для проверки сертификата X.509.  Значение по умолчанию «PeerOrChainTrust».  Чтобы указать настраиваемый проверяющий элемент управления, установите для этого атрибута значение «custom» и задайте проверяющий элемент управления [\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) с использованием элемента.  Необязательный.|  
|revocationMode|Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>, указывающее режим отзыва для сертификата X.509.  Значение по умолчанию «подключения».  Необязательный.|  
|trustedStoreLocation|Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation>, определяющее хранилище сертификатов X.509.  Значение по умолчанию \-LocalMachine».  Необязательный.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|Определяет тип пользователя для проверки сертификата.  Этот тип используется, только если атрибут `certificateValidationMode` [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) элемента имеет значение «custom».|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Задает параметры идентификатора уровня обслуживания.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию коллекции обработчиков маркера безопасности.|  
  
## Заметки  
 Элемент `<certificateValidation>` можно определить на уровне службы под элементом `<identityConfiguration>` или в коллекцию обработчиков маркеров безопасности уровня под элементом `<securityTokenHandlerConfiguration>`.  Параметры в коллекции обработчика токена переопределяют те, определенной в службе.  Некоторые обработчики токена позволяют задать параметры проверки сертификата в конфигурации.  Параметры переопределяют те, для отдельных обработчиков токена и на уровне службы и на коллекцию обработчиков маркера безопасности.  
  
## Пример  
  
```  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```