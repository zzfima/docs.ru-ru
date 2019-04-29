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
ms.openlocfilehash: 9fc5f3a3d5bc5699a596bcc648a7153190c130f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697684"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="03ddf-102">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="03ddf-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="03ddf-103">Представляет глобальный кэш сборок для использования технологией fusion.</span><span class="sxs-lookup"><span data-stu-id="03ddf-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03ddf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="03ddf-104">Methods</span></span>  
  
|<span data-ttu-id="03ddf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="03ddf-105">Method</span></span>|<span data-ttu-id="03ddf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="03ddf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03ddf-107">Метод CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="03ddf-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="03ddf-108">Получает ссылку на новый [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="03ddf-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="03ddf-109">Метод CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="03ddf-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="03ddf-110">Зарезервировано для внутреннего использования технологией fusion.</span><span class="sxs-lookup"><span data-stu-id="03ddf-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="03ddf-111">Метод InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="03ddf-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="03ddf-112">Устанавливает указанную сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="03ddf-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="03ddf-113">Метод QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="03ddf-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="03ddf-114">Получает запрашиваемые данные об указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="03ddf-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="03ddf-115">Метод UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="03ddf-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="03ddf-116">Удаляет указанную сборку из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="03ddf-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03ddf-117">Требования</span><span class="sxs-lookup"><span data-stu-id="03ddf-117">Requirements</span></span>  
 <span data-ttu-id="03ddf-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03ddf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03ddf-119">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="03ddf-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="03ddf-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03ddf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ddf-121">См. также</span><span class="sxs-lookup"><span data-stu-id="03ddf-121">See also</span></span>

- [<span data-ttu-id="03ddf-122">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="03ddf-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="03ddf-123">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="03ddf-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
