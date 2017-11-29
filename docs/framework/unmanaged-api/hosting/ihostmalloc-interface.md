---
title: "Интерфейс IHostMalloc"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc
helpviewer_keywords: IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f788456065a5508441b9fec38ad4a7f531f9f303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="c1ec9-102">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="c1ec9-102">IHostMalloc Interface</span></span>
<span data-ttu-id="c1ec9-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для выделения точного количества памяти из кучи посредством узла.</span><span class="sxs-lookup"><span data-stu-id="c1ec9-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1ec9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c1ec9-104">Methods</span></span>  
  
|<span data-ttu-id="c1ec9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c1ec9-105">Method</span></span>|<span data-ttu-id="c1ec9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c1ec9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1ec9-107">Alloc-метод</span><span class="sxs-lookup"><span data-stu-id="c1ec9-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="c1ec9-108">Запрашивает у узла выделение запрошенного объема памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="c1ec9-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="c1ec9-109">DebugAlloc-метод</span><span class="sxs-lookup"><span data-stu-id="c1ec9-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="c1ec9-110">Запрашивает выделение запрошенного объема памяти из кучи основное и дополнительное отслеживание, где была выделена память.</span><span class="sxs-lookup"><span data-stu-id="c1ec9-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="c1ec9-111">Free-метод</span><span class="sxs-lookup"><span data-stu-id="c1ec9-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="c1ec9-112">Освобождает память, выделенную с помощью `Alloc` метод.</span><span class="sxs-lookup"><span data-stu-id="c1ec9-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1ec9-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1ec9-113">Remarks</span></span>  
 <span data-ttu-id="c1ec9-114">Среда CLR возвращает указатель интерфейса `IHostMalloc` экземпляр путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c1ec9-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ec9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c1ec9-115">Requirements</span></span>  
 <span data-ttu-id="c1ec9-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ec9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ec9-117">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1ec9-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1ec9-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1ec9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ec9-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ec9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ec9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c1ec9-120">See Also</span></span>  
 [<span data-ttu-id="c1ec9-121">IHostMemoryManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c1ec9-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="c1ec9-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c1ec9-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
