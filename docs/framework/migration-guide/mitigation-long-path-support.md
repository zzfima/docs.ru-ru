---
title: "Устранение рисков. Поддержка длинных путей"
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
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 138e96c3d45b79ccf30f6a3d39f0af26a48c0117
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-long-path-support"></a><span data-ttu-id="e4536-102">Устранение рисков. Поддержка длинных путей</span><span class="sxs-lookup"><span data-stu-id="e4536-102">Mitigation: Long Path Support</span></span>
<span data-ttu-id="e4536-103">Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], методы ввода-вывода файловой системы не будут автоматически создавать исключение <xref:System.IO.PathTooLongException>, когда длина пути или полного имени файла превышает 260 (или `MAX_PATH`) символов.</span><span class="sxs-lookup"><span data-stu-id="e4536-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)],  file system I/O methods not longer automatically throw a <xref:System.IO.PathTooLongException> if a path or fully qualified file name exceeds 260 (or `MAX_PATH`) characters.</span></span> <span data-ttu-id="e4536-104">Вместо этого поддерживаются длинные пути до 32 тыс. символов.</span><span class="sxs-lookup"><span data-stu-id="e4536-104">Instead, long paths of up to 32K characters are supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e4536-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="e4536-105">Impact</span></span>  
 <span data-ttu-id="e4536-106">Приложения, перекомпилированные для нацеливания на платформу [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], которые ранее автоматически создавали исключение <xref:System.IO.PathTooLongException>, когда длина пути превышает 260 символов, теперь будут создавать <xref:System.IO.PathTooLongException> только при выполнении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="e4536-106">Apps recompiled to target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] and that previously threw a <xref:System.IO.PathTooLongException> automatically because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException> only under the following conditions:</span></span>  
  
-   <span data-ttu-id="e4536-107">Длина пути превышает <xref:System.Int16.MaxValue?displayProperty=fullName> (32 767) символов.</span><span class="sxs-lookup"><span data-stu-id="e4536-107">The length of the path is greater than  <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) characters.</span></span>  
  
-   <span data-ttu-id="e4536-108">операционная система возвращает `COR_E_PATHTOOLONG` или его эквивалент;</span><span class="sxs-lookup"><span data-stu-id="e4536-108">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>  
  
 <span data-ttu-id="e4536-109">Для приложений, нацеливаемых на [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранние версии, сохраняется прежнее поведение, то есть среда выполнения автоматически создает исключение <xref:System.IO.PathTooLongException> всякий раз, когда длина пути превышает 260 символов.</span><span class="sxs-lookup"><span data-stu-id="e4536-109">The legacy behavior for apps that target the[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier is that the runtime automatically throws a <xref:System.IO.PathTooLongException> whenever a path exceeds 260 characters.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e4536-110">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="e4536-110">Mitigation</span></span>  
 <span data-ttu-id="e4536-111">Для приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], можно отказаться от поддержки длинных путей, если это нежелательно, добавив следующую строку в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:</span><span class="sxs-lookup"><span data-stu-id="e4536-111">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], you can opt out of long path support if it is not desirable by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 <span data-ttu-id="e4536-112">Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, можно включить поддержку длинных путей, добавив следующую строку в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:</span><span class="sxs-lookup"><span data-stu-id="e4536-112">For apps that target earlier versions of the .NET Framework but run on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later., you can opt in to long path support by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4536-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e4536-113">See Also</span></span>  
 [<span data-ttu-id="e4536-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e4536-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

