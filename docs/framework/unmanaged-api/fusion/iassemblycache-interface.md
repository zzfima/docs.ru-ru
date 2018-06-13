---
title: Интерфейс IAssemblyCache
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430587"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="76c38-102">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="76c38-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="76c38-103">Представляет глобальный кэш сборок для использования технологией fusion.</span><span class="sxs-lookup"><span data-stu-id="76c38-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76c38-104">Методы</span><span class="sxs-lookup"><span data-stu-id="76c38-104">Methods</span></span>  
  
|<span data-ttu-id="76c38-105">Метод</span><span class="sxs-lookup"><span data-stu-id="76c38-105">Method</span></span>|<span data-ttu-id="76c38-106">Описание</span><span class="sxs-lookup"><span data-stu-id="76c38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76c38-107">Метод CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="76c38-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="76c38-108">Возвращает ссылку на новый [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="76c38-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="76c38-109">Метод CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="76c38-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="76c38-110">Зарезервировано для внутреннего использования технологией fusion.</span><span class="sxs-lookup"><span data-stu-id="76c38-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="76c38-111">Метод InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="76c38-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="76c38-112">Устанавливает указанную сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="76c38-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="76c38-113">Метод QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="76c38-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="76c38-114">Возвращает запрашиваемые данные об указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="76c38-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="76c38-115">Метод UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="76c38-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="76c38-116">Удаляет указанную сборку из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="76c38-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76c38-117">Требования</span><span class="sxs-lookup"><span data-stu-id="76c38-117">Requirements</span></span>  
 <span data-ttu-id="76c38-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76c38-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76c38-119">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="76c38-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="76c38-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76c38-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76c38-121">См. также</span><span class="sxs-lookup"><span data-stu-id="76c38-121">See Also</span></span>  
 [<span data-ttu-id="76c38-122">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="76c38-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="76c38-123">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="76c38-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
