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
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="4e290-102">Устранение рисков: метод X509CertificateClaimSet.FindClaims</span><span class="sxs-lookup"><span data-stu-id="4e290-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>
<span data-ttu-id="4e290-103">Начиная с приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> пытается сопоставить аргумент `claimType` со всеми записями DNS в поле SAN.</span><span class="sxs-lookup"><span data-stu-id="4e290-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)],  the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="4e290-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="4e290-104">Impact</span></span>  
 <span data-ttu-id="4e290-105">Это изменение затрагивает только приложения, предназначенные для .NET Framework, начиная с версии [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e290-105">This change only affects apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="4e290-106">В приложениях, предназначенных для более ранних версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> пытается сопоставить аргумент `claimType` только с последней записью DNS.</span><span class="sxs-lookup"><span data-stu-id="4e290-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="4e290-107">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="4e290-107">Mitigation</span></span>  
 <span data-ttu-id="4e290-108">Если это изменение нежелательно, его можно отключить для приложений, предназначенных для версий .NET Framework, начиная с [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], добавив в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="4e290-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 <span data-ttu-id="4e290-109">Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более поздних версий. Для этого добавьте в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="4e290-109">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e290-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4e290-110">See Also</span></span>  
 [<span data-ttu-id="4e290-111">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="4e290-111">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

