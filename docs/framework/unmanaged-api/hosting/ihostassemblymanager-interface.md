---
title: Интерфейс IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e300d4645939a131ceb8206999d95056b96a678
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118954"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="87cd6-102">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="87cd6-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="87cd6-103">Предоставляет методы, которые позволяют ведущему приложению задать набор сборок, которые должны быть загружены с общеязыковой среды выполнения (CLR) или узлом.</span><span class="sxs-lookup"><span data-stu-id="87cd6-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87cd6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="87cd6-104">Methods</span></span>  
  
|<span data-ttu-id="87cd6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="87cd6-105">Method</span></span>|<span data-ttu-id="87cd6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="87cd6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87cd6-107">Метод GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="87cd6-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="87cd6-108">Получает указатель интерфейса на [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , представляющий список сборок, загруженных приложением.</span><span class="sxs-lookup"><span data-stu-id="87cd6-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="87cd6-109">Метод GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="87cd6-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="87cd6-110">Получает указатель интерфейса на [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые, среда CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="87cd6-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87cd6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="87cd6-111">Remarks</span></span>  
 <span data-ttu-id="87cd6-112">Узел не нужно реализовать `IHostAssemblyManager` или `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="87cd6-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="87cd6-113">Если узел реализует `IHostAssemblyManager`, он также должен реализовать `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="87cd6-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="87cd6-114">Среда выполнения запрашивает `IHostAssemblyManager` путем вызова [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) при инициализации с `IID` из IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="87cd6-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87cd6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="87cd6-115">Requirements</span></span>  
 <span data-ttu-id="87cd6-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87cd6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87cd6-117">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87cd6-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87cd6-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87cd6-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="87cd6-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="87cd6-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="87cd6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="87cd6-120">See also</span></span>

- [<span data-ttu-id="87cd6-121">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="87cd6-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="87cd6-122">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="87cd6-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="87cd6-123">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="87cd6-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="87cd6-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="87cd6-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
