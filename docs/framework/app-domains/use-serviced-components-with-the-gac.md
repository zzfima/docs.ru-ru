---
title: Использование обслуживаемых компонентов с глобальным кэшем сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 703e71661c7a679b85e60726f53b275fce1a4d6a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="f2d10-102">Использование обслуживаемых компонентов с глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="f2d10-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="f2d10-103">Обслуживаемые компоненты (компоненты управляемого кода COM+) следует помещать в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="f2d10-103">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="f2d10-104">В некоторых ситуациях среда CLR и службы COM+ могут обрабатывать обслуживаемые компоненты, не входящие в глобальный кэш сборок; в других сценариях это невозможно.</span><span class="sxs-lookup"><span data-stu-id="f2d10-104">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="f2d10-105">Это иллюстрируется в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="f2d10-105">The following scenarios illustrate this:</span></span>  
  
-   <span data-ttu-id="f2d10-106">Для обслуживаемых компонентов в серверном приложении COM+ сборка, содержащая компоненты, должна находиться в глобальном кэше сборок, так как Dllhost.exe не может выполняться в том же каталоге, в котором содержатся обслуживаемые компоненты.</span><span class="sxs-lookup"><span data-stu-id="f2d10-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
-   <span data-ttu-id="f2d10-107">Для обслуживаемых компонентов в приложении библиотеки COM+ среда выполнения и службы COM+ могут разрешать ссылку на сборку, содержащую компоненты, путем поиска в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f2d10-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="f2d10-108">В этом случае сборка может не находиться в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="f2d10-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="f2d10-109">Ситуация отличается для обслуживаемых компонентов в приложении ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f2d10-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="f2d10-110">Если поместить сборку, содержащую обслуживаемые компоненты, в каталог bin базовой папки приложения и использовать регистрацию по требованию, будет выполняться теневое копирование сборки в кэш загрузки, так как ASP.NET использует возможности теневого копирования среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f2d10-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d10-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f2d10-111">See Also</span></span>  
 [<span data-ttu-id="f2d10-112">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="f2d10-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="f2d10-113">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="f2d10-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
