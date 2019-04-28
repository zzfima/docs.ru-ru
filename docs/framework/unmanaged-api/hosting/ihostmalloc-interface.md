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
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757642"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="c578c-102">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="c578c-102">IHostMalloc Interface</span></span>
<span data-ttu-id="c578c-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для выделения точного количества памяти из кучи через узел.</span><span class="sxs-lookup"><span data-stu-id="c578c-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c578c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c578c-104">Methods</span></span>  
  
|<span data-ttu-id="c578c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c578c-105">Method</span></span>|<span data-ttu-id="c578c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c578c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c578c-107">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="c578c-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="c578c-108">Запрашивает выделение узла запрошенного объема памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="c578c-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="c578c-109">Метод DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="c578c-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="c578c-110">Запрашивает, что узел выделение запрошенного объема памяти из кучи и Кроме того, отслеживать, где была выделена память.</span><span class="sxs-lookup"><span data-stu-id="c578c-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="c578c-111">Метод Free</span><span class="sxs-lookup"><span data-stu-id="c578c-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="c578c-112">Освобождает память, выделенную с помощью `Alloc` метод.</span><span class="sxs-lookup"><span data-stu-id="c578c-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c578c-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c578c-113">Remarks</span></span>  
 <span data-ttu-id="c578c-114">Среда CLR получает указатель интерфейса на `IHostMalloc` экземпляра путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c578c-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c578c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c578c-115">Requirements</span></span>  
 <span data-ttu-id="c578c-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c578c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c578c-117">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c578c-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c578c-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c578c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c578c-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c578c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c578c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c578c-120">See also</span></span>

- [<span data-ttu-id="c578c-121">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c578c-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="c578c-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c578c-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
