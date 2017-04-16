---
title: "Решение проблемы: метод X509CertificiateClaimSet.FindClaims | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Решение проблемы: метод X509CertificiateClaimSet.FindClaims
Начиная с приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> пытается сопоставить аргумент `claimType` со всеми записями DNS в поле SAN.  
  
## Последствия  
 Это изменение затрагивает только приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 В приложениях, предназначенных для предыдущих версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> пытается сопоставить аргумент `claimType` только с последней записью DNS.  
  
## Уменьшение  
 Если это изменение нежелательно, его можно отключить для приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], добавив в раздел [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" /> </runtime>  
  
```  
  
 Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Для этого добавьте в раздел [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" /> </runtime>  
  
```  
  
## См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)