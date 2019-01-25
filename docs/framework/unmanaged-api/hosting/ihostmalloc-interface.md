---
title: Интерфейс IHostMalloc
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea3656fa00e84291ff7b2bdb65f9300cd7933c0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571786"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="ff27d-102">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="ff27d-102">IHostMalloc Interface</span></span>
<span data-ttu-id="ff27d-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для выделения точного количества памяти из кучи через узел.</span><span class="sxs-lookup"><span data-stu-id="ff27d-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff27d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ff27d-104">Methods</span></span>  
  
|<span data-ttu-id="ff27d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ff27d-105">Method</span></span>|<span data-ttu-id="ff27d-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="ff27d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff27d-107">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="ff27d-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="ff27d-108">Запрашивает выделение узла запрошенного объема памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="ff27d-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="ff27d-109">Метод DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="ff27d-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="ff27d-110">Запрашивает, что узел выделение запрошенного объема памяти из кучи и Кроме того, отслеживать, где была выделена память.</span><span class="sxs-lookup"><span data-stu-id="ff27d-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="ff27d-111">Метод Free</span><span class="sxs-lookup"><span data-stu-id="ff27d-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="ff27d-112">Освобождает память, выделенную с помощью `Alloc` метод.</span><span class="sxs-lookup"><span data-stu-id="ff27d-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff27d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff27d-113">Remarks</span></span>  
 <span data-ttu-id="ff27d-114">Среда CLR получает указатель интерфейса на `IHostMalloc` экземпляра путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ff27d-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff27d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ff27d-115">Requirements</span></span>  
 <span data-ttu-id="ff27d-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff27d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff27d-117">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff27d-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff27d-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff27d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff27d-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff27d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff27d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ff27d-120">See also</span></span>
- [<span data-ttu-id="ff27d-121">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="ff27d-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="ff27d-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ff27d-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
