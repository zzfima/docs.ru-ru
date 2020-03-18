---
title: 'Устранение рисков: метод X509CertificateClaimSet.FindClaims'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: f94a5f685a5aa94332bf2e15e5d5eb0def02d7ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398667"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Устранение рисков: метод X509CertificateClaimSet.FindClaims
Начиная с приложений, предназначенных для .NET Framework 4.6.1, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> пытается сопоставить аргумент `claimType` со всеми записями DNS в поле SAN.  
  
## <a name="impact"></a>Последствия  
 Это изменение затрагивает только приложения, предназначенные для .NET Framework, начиная с версии .NET Framework 4.6.1.  
  
 В приложениях, предназначенных для более ранних версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> пытается сопоставить аргумент `claimType` только с последней записью DNS.  
  
## <a name="mitigation"></a>Меры по снижению риска  
 Если это изменение нежелательно, его можно отключить для приложений, предназначенных для версий .NET Framework, начиная с .NET Framework 4.6.1, добавив в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением .NET Framework 4.6.1 и более поздних версий. Для этого добавьте в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Совместимость приложений](application-compatibility.md)
