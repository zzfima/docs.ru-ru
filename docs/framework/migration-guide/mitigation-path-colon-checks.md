---
title: "Устранение рисков. Проверки двоеточий в путях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a976e4491924f91e97f01a9b98db945699655196
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="30342-102">Устранение рисков. Проверки двоеточий в путях</span><span class="sxs-lookup"><span data-stu-id="30342-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="30342-103">Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], выполнен ряд изменений для поддержки ранее не поддерживаемых путей (с точки зрения и длины, и формата).</span><span class="sxs-lookup"><span data-stu-id="30342-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="30342-104">В частности, усовершенствованы проверки правильности синтаксиса разделителя диска (двоеточия).</span><span class="sxs-lookup"><span data-stu-id="30342-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="30342-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="30342-105">Impact</span></span>  
 <span data-ttu-id="30342-106">Эти изменения блокируют некоторые пути URI, которые ранее поддерживались методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="30342-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="30342-107">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="30342-107">Mitigation</span></span>  
 <span data-ttu-id="30342-108">Чтобы обойти проблему с ранее допустимым путем, который больше не поддерживается методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="30342-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
-   <span data-ttu-id="30342-109">Вручную удалить схему из URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="30342-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="30342-110">Например, удалить `file://` из URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="30342-110">For example, remove `file://` from a URL.</span></span>  
  
-   <span data-ttu-id="30342-111">передать код URI в конструктор <xref:System.Uri> и получить значение свойства <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>;</span><span class="sxs-lookup"><span data-stu-id="30342-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
-   <span data-ttu-id="30342-112">отказаться от новой нормализации путей, установив для параметра `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="30342-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="30342-113">См. также</span><span class="sxs-lookup"><span data-stu-id="30342-113">See Also</span></span>  
 [<span data-ttu-id="30342-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="30342-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
