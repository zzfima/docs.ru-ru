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
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124508"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="ab44a-102">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="ab44a-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="ab44a-103">Предоставляет методы, позволяющие узлу указывать наборы сборок, которые должны быть загружены средой CLR или узлом.</span><span class="sxs-lookup"><span data-stu-id="ab44a-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab44a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ab44a-104">Methods</span></span>  
  
|<span data-ttu-id="ab44a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ab44a-105">Method</span></span>|<span data-ttu-id="ab44a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ab44a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab44a-107">Метод GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ab44a-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="ab44a-108">Возвращает указатель интерфейса на объект [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , представляющий список сборок, загруженных узлом.</span><span class="sxs-lookup"><span data-stu-id="ab44a-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="ab44a-109">Метод GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="ab44a-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="ab44a-110">Возвращает указатель интерфейса на объект [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые узел загружает в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="ab44a-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab44a-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="ab44a-111">Remarks</span></span>  
 <span data-ttu-id="ab44a-112">Узел не требуется для реализации `IHostAssemblyManager` или `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="ab44a-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="ab44a-113">Если узел реализует `IHostAssemblyManager`, он также должен реализовывать `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="ab44a-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="ab44a-114">Среда выполнения запрашивает `IHostAssemblyManager` путем вызова [IHostControl:: жесостманажер](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) при инициализации с `IID` IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="ab44a-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab44a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ab44a-115">Requirements</span></span>  
 <span data-ttu-id="ab44a-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab44a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab44a-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ab44a-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab44a-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ab44a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab44a-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab44a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab44a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ab44a-120">See also</span></span>

- [<span data-ttu-id="ab44a-121">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ab44a-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ab44a-122">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ab44a-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="ab44a-123">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="ab44a-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="ab44a-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ab44a-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
