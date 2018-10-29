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
ms.openlocfilehash: 4fe5edb7c09d0f850b142aba5062a36bfc6d87c1
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184241"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="1fd8b-102">Использование обслуживаемых компонентов с глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="1fd8b-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="1fd8b-103">Обслуживаемые компоненты (компоненты управляемого кода COM+) следует помещать в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-103">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="1fd8b-104">В некоторых ситуациях среда CLR и службы COM+ могут обрабатывать обслуживаемые компоненты, не входящие в глобальный кэш сборок; в других сценариях это невозможно.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-104">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="1fd8b-105">Это иллюстрируется в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-105">The following scenarios illustrate this:</span></span>  
  
-   <span data-ttu-id="1fd8b-106">Для обслуживаемых компонентов в серверном приложении COM+ сборка, содержащая компоненты, должна находиться в глобальном кэше сборок, так как Dllhost.exe не может выполняться в том же каталоге, в котором содержатся обслуживаемые компоненты.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
-   <span data-ttu-id="1fd8b-107">Для обслуживаемых компонентов в приложении библиотеки COM+ среда выполнения и службы COM+ могут разрешать ссылку на сборку, содержащую компоненты, путем поиска в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="1fd8b-108">В этом случае сборка может не находиться в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="1fd8b-109">Ситуация отличается для обслуживаемых компонентов в приложении ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="1fd8b-110">Если поместить сборку, содержащую обслуживаемые компоненты, в каталог bin базовой папки приложения и использовать регистрацию по требованию, будет выполняться теневое копирование сборки в кэш загрузки, так как ASP.NET использует возможности теневого копирования среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1fd8b-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd8b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1fd8b-111">See Also</span></span>  
- [<span data-ttu-id="1fd8b-112">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="1fd8b-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
- [<span data-ttu-id="1fd8b-113">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="1fd8b-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
