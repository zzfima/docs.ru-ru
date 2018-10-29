---
title: Расположение сборки
ms.date: 03/30/2017
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19c4b030e8b44bed5377827d016127b4a574f5ee
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50183754"
---
# <a name="assembly-location"></a><span data-ttu-id="5d82d-102">Расположение сборки</span><span class="sxs-lookup"><span data-stu-id="5d82d-102">Assembly Location</span></span>
<span data-ttu-id="5d82d-103">От места расположения сборки зависит, сможет ли среда CLR найти сборку по ссылке на нее. Это расположение также определяет возможность совместного использования сборки вместе с другими сборками.</span><span class="sxs-lookup"><span data-stu-id="5d82d-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="5d82d-104">Для развертывания сборки можно использовать следующие расположения.</span><span class="sxs-lookup"><span data-stu-id="5d82d-104">You can deploy an assembly in the following locations:</span></span>  
  
-   <span data-ttu-id="5d82d-105">Каталог приложения или его подкаталоги</span><span class="sxs-lookup"><span data-stu-id="5d82d-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="5d82d-106">Это наиболее часто используемое место развертывания сборок.</span><span class="sxs-lookup"><span data-stu-id="5d82d-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="5d82d-107">Структура подкаталогов корневого каталога приложения может зависеть от языка или региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="5d82d-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="5d82d-108">Если в атрибутах сборки также задан язык и региональные параметры, то она должна располагаться в подкаталоге каталога приложения, название которого соответствует этому языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="5d82d-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
-   <span data-ttu-id="5d82d-109">Глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="5d82d-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="5d82d-110">Это кэш кода уровня компьютера, который имеется на любом компьютере с установленной средой CLR.</span><span class="sxs-lookup"><span data-stu-id="5d82d-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="5d82d-111">В большинстве случаев при необходимости совместного использования сборки в нескольких приложениях ее следует расположить в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="5d82d-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="5d82d-112">На HTTP-сервере.</span><span class="sxs-lookup"><span data-stu-id="5d82d-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="5d82d-113">Сборка, развернутая на HTTP-сервере, должна иметь строгое имя; в разделе базы кода файла конфигурации приложения должно присутствовать указание на сборку.</span><span class="sxs-lookup"><span data-stu-id="5d82d-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d82d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5d82d-114">See Also</span></span>  
- [<span data-ttu-id="5d82d-115">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="5d82d-115">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
- [<span data-ttu-id="5d82d-116">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="5d82d-116">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
- [<span data-ttu-id="5d82d-117">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="5d82d-117">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
- [<span data-ttu-id="5d82d-118">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="5d82d-118">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
