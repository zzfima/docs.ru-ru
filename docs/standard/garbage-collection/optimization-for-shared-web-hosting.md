---
title: "Оптимизация совместного размещения веб-сайтов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="3e0e1-102">Оптимизация совместного размещения веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="3e0e1-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="3e0e1-103">Если вы являетесь администратором сервера, совместно размещены несколько небольших веб-сайтов, можно оптимизировать производительность и увеличить емкость узла, добавив следующий код `gcTrimCommitOnLowMemory` параметру `runtime` узла в файле Aspnet.config в .NET каталог:</span><span class="sxs-lookup"><span data-stu-id="3e0e1-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="3e0e1-104">Данный параметр рекомендуется только для общих веб-сайта, в сценариях размещения.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="3e0e1-105">Так как сборщик мусора оставляет память для будущих распределений, память может быть больше, чем минимально необходимые.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="3e0e1-106">Можно уменьшить этот объем, чтобы облегчить при высокую нагрузку на системную память.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="3e0e1-107">Уменьшение этого предоставленного объема улучшает производительность и увеличивает емкость для размещения большего количества узлов.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="3e0e1-108">Если `gcTrimCommitOnLowMemory` параметр включен, сборщик мусора оценивает загрузку системной памяти и переходит в режим обрезки когда нагрузка достигает 90%.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="3e0e1-109">Это обеспечивает режим обрезки, пока загрузка не опустится ниже 85%.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="3e0e1-110">Если позволяют условия, сборщик мусора может решить, что `gcTrimCommitOnLowMemory` параметр будет справки текущего приложения и не смогут его пропустить.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e0e1-111">Пример</span><span class="sxs-lookup"><span data-stu-id="3e0e1-111">Example</span></span>  
 <span data-ttu-id="3e0e1-112">В следующем фрагменте XML показано, как включить `gcTrimCommitOnLowMemory` параметр.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="3e0e1-113">Многоточие указывает на другие параметры, которые будут находиться в `runtime` узла.</span><span class="sxs-lookup"><span data-stu-id="3e0e1-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e0e1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3e0e1-114">See Also</span></span>  
 [<span data-ttu-id="3e0e1-115">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="3e0e1-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
