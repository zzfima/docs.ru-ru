---
title: "&lt;caches&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;caches&gt;
Регистрирует кэши для обнаружения маркеров преобразования и маркеров сеансов.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
 None  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<sessionSecurityTokenCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|Регистрирует кэша маркеров сеанса службы или коллекции обработчик маркеров безопасности.|  
|[\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|Регистрирует маркер воспроизведения кэша службы или коллекции обработчик маркеров безопасности.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Задает параметры уровня службы удостоверений.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Содержит настройки для коллекции безопасности обработчиков маркеров.|  
  
## Заметки  
 A `<caches>` элемент задается на уровне службы под `<identityConfiguration>` элемент или на уровне коллекции обработчик маркеров безопасности под `<securityTokenHandlerConfiguration>` элемент.  Параметры в коллекции маркеров обработчик переопределения указанных служб.  
  
 `<caches>` Представленного элементом <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> класса.  Настроенные кэшей, представленные <xref:System.IdentityModel.Configuration.IdentityModelCaches> класса.  
  
## Пример  
 Следующий XML показывает конфигурацию пользовательского кэша для хранения сеанса маркеров безопасности \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  Конфигурация берется из `ClaimsAwareWebFarm` образца.  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```