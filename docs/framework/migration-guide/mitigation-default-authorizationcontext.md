---
title: "Устранение рисков. Контекст AuthorizationContext по умолчанию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 48363d0f8e515b703e49761a763379566e217844
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-default-authorizationcontext"></a><span data-ttu-id="8b109-102">Устранение рисков. Контекст AuthorizationContext по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8b109-102">Mitigation: Default AuthorizationContext</span></span>
<span data-ttu-id="8b109-103">В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] изменена реализация контекста <xref:System.IdentityModel.Policy.AuthorizationContext>, возвращаемого при вызове <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> с аргументом `null``authorizationPolicies`.</span><span class="sxs-lookup"><span data-stu-id="8b109-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> with a `null``authorizationPolicies` argument has changed its implementation in the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</span></span>  
  
## <a name="impact"></a><span data-ttu-id="8b109-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="8b109-104">Impact</span></span>  
 <span data-ttu-id="8b109-105">В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении.</span><span class="sxs-lookup"><span data-stu-id="8b109-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="8b109-106">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="8b109-106">Mitigation</span></span>  
 <span data-ttu-id="8b109-107">К прежнему поведению можно вернуться двумя способами.</span><span class="sxs-lookup"><span data-stu-id="8b109-107">You can restore the previous behavior in either of two ways:</span></span>  
  
-   <span data-ttu-id="8b109-108">Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6.</span><span class="sxs-lookup"><span data-stu-id="8b109-108">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="8b109-109">Для служб, размещенных в IIS, используйте элемент `<httpRuntime targetFramework="x.x" />` для выбора более ранней версии .NET Framework в качестве целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="8b109-109">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x" />` element to target an earlier version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="8b109-110">Добавьте следующую строку в раздел `<appSettings>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="8b109-110">Add the following line to the `<appSettings>` section of your app.config file:</span></span>  
  
    ```xml  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8b109-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8b109-111">See Also</span></span>  
 [<span data-ttu-id="8b109-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="8b109-112">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

