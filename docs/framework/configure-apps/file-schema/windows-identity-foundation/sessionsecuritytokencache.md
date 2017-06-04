---
title: "&lt;sessionSecurityTokenCache&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;sessionSecurityTokenCache&gt;
Регистрирует кэша маркеров сеанса службы или коллекции обработчик маркеров безопасности.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|type|Тип, производный от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса.  Дополнительные сведения об указании пользовательского `type`, см. [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Регистрирует кэшей, службы или коллекции обработчик маркеров безопасности.|  
  
## Пример  
 Следующий XML показывает конфигурацию пользовательского кэша для хранения сеанса маркеров безопасности \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  Конфигурация берется из `ClaimsAwareWebFarm` образца.  Дополнительные сведения об этом примере см. [Индекс образцов кода WIF](../../../../../docs/framework/security/wif-code-sample-index.md).  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## См. также  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>