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
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136779"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="a90de-102">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="a90de-102">IHostMalloc Interface</span></span>
<span data-ttu-id="a90de-103">Предоставляет методы, позволяющие среде CLR запрашивать детализированные выделения из кучи через узел.</span><span class="sxs-lookup"><span data-stu-id="a90de-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a90de-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a90de-104">Methods</span></span>  
  
|<span data-ttu-id="a90de-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a90de-105">Method</span></span>|<span data-ttu-id="a90de-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a90de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a90de-107">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="a90de-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="a90de-108">Запрашивает у узла выделение запрошенного объема памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="a90de-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="a90de-109">Метод DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="a90de-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="a90de-110">Запрашивает, что узел выделяет запрошенный объем памяти из кучи, и дополнительно следит за местом выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="a90de-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="a90de-111">Метод Free</span><span class="sxs-lookup"><span data-stu-id="a90de-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="a90de-112">Освобождает память, выделенную с помощью метода `Alloc`.</span><span class="sxs-lookup"><span data-stu-id="a90de-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a90de-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="a90de-113">Remarks</span></span>  
 <span data-ttu-id="a90de-114">Среда CLR получает указатель интерфейса на экземпляр `IHostMalloc`, вызывая метод [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a90de-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a90de-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a90de-115">Requirements</span></span>  
 <span data-ttu-id="a90de-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a90de-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a90de-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a90de-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a90de-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a90de-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a90de-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a90de-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90de-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a90de-120">See also</span></span>

- [<span data-ttu-id="a90de-121">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="a90de-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="a90de-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a90de-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
