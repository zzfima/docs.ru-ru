---
title: "Устранение рисков: метод X509CertificateClaimSet.FindClaims"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d19bf73e36061729c0c57439f4e4144669787d1a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Устранение рисков: метод X509CertificateClaimSet.FindClaims
Начиная с приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> пытается сопоставить аргумент `claimType` со всеми записями DNS в поле SAN.  
  
## <a name="impact"></a>Последствия  
 Это изменение затрагивает только приложения, предназначенные для .NET Framework, начиная с версии [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 В приложениях, предназначенных для более ранних версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> пытается сопоставить аргумент `claimType` только с последней записью DNS.  
  
## <a name="mitigation"></a>Уменьшение  
 Если это изменение нежелательно, его можно отключить для приложений, предназначенных для версий .NET Framework, начиная с [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], добавив в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более поздних версий. Для этого добавьте в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

