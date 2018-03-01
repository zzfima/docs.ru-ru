---
title: "Интерфейс IHostMalloc"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e1690f5fe8f1417e6547ed94db8c71f079ebf5e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="9e9f4-102">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="9e9f4-102">IHostMalloc Interface</span></span>
<span data-ttu-id="9e9f4-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для выделения точного количества памяти из кучи посредством узла.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e9f4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9e9f4-104">Methods</span></span>  
  
|<span data-ttu-id="9e9f4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9e9f4-105">Method</span></span>|<span data-ttu-id="9e9f4-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="9e9f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e9f4-107">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="9e9f4-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="9e9f4-108">Запрашивает у узла выделение запрошенного объема памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="9e9f4-109">Метод DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="9e9f4-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="9e9f4-110">Запрашивает выделение запрошенного объема памяти из кучи основное и дополнительное отслеживание, где была выделена память.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="9e9f4-111">Метод Free</span><span class="sxs-lookup"><span data-stu-id="9e9f4-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="9e9f4-112">Освобождает память, выделенную с помощью `Alloc` метод.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e9f4-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e9f4-113">Remarks</span></span>  
 <span data-ttu-id="9e9f4-114">Среда CLR возвращает указатель интерфейса `IHostMalloc` экземпляр путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9e9f4-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e9f4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9e9f4-115">Requirements</span></span>  
 <span data-ttu-id="9e9f4-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e9f4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e9f4-117">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e9f4-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e9f4-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e9f4-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e9f4-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e9f4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e9f4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9e9f4-120">See Also</span></span>  
 [<span data-ttu-id="9e9f4-121">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="9e9f4-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="9e9f4-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9e9f4-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
