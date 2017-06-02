---
title: "&lt;tokenReplayDetection&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;tokenReplayDetection&gt;
Включает обнаружение воспроизведения токена и определяет время окончания срока действия для маркеров.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Тип  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|enabled|Значение, указывающее, разрешено ли обнаружение воспроизведения токена. «true» включить обнаружение воспроизведения токена.|  
|expirationPeriod|<xref:System.TimeSpan>, который указывает максимальное количество времени перед элементом считается expired и удаляется из кэша.  Дополнительные сведения о способах указания значений <xref:System.TimeSpan> см. в разделе [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Задает параметры идентификатора уровня обслуживания.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию коллекции обработчиков маркера безопасности.|  
  
## Заметки  
 Элемент `<tokenReplayDetection>` можно определить на уровне службы под элементом `<identityConfiguration>` или в коллекцию обработчиков маркеров безопасности уровня под элементом `<securityTokenHandlerConfiguration>`.  Параметры в коллекции обработчика токена переопределяют те, определенной в службе.  
  
 Тип кэша воспроизведения токена определяется [\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элементом.