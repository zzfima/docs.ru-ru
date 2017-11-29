---
title: "Интерфейс IHostMemoryManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 415539be0dbed8e0cf3f9d6e5c79bf4cfac09fe2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="fc3b5-102">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="fc3b5-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="fc3b5-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), чтобы запросы виртуальной памяти через узел, вместо использования стандартных функций Win32 виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc3b5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fc3b5-104">Methods</span></span>  
  
|<span data-ttu-id="fc3b5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-105">Method</span></span>|<span data-ttu-id="fc3b5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fc3b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc3b5-107">Acquiredvirtualaddressspace-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="fc3b5-108">Уведомляет узел, что общеязыковой среды выполнения (CLR) получила указанную память от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="fc3b5-109">Метод CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="fc3b5-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="fc3b5-110">Возвращает указатель интерфейса [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) экземпляр, используемый для запроса выделения памяти из кучи, созданные узлом.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="fc3b5-111">Getmemoryload-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="fc3b5-112">Возвращает объем физической памяти, используемой в данный момент, о котором сообщает узла.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="fc3b5-113">NeedsVirtualAddressSpace-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="fc3b5-114">Уведомляет основное приложение, среда CLR будет пытаться использовать указанный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="fc3b5-115">Registermemorynotificationcallback-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="fc3b5-116">Регистрирует указатель на функцию обратного вызова, который основное приложение вызывает для уведомления среды CLR о текущей загруженности памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="fc3b5-117">Releasedvirtualaddressspace-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="fc3b5-118">Уведомляет узел, что среда CLR завершила использование указанной памяти.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="fc3b5-119">VirtualAlloc-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="fc3b5-120">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая резервирует или фиксирует диапазон страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="fc3b5-121">VirtualFree-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="fc3b5-122">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая освобождает, разблокирует или освобождает и разблокирует диапазон страниц в пределах виртуального адресного пространства вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="fc3b5-123">VirtualProtect-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="fc3b5-124">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая изменяет защиту в области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="fc3b5-125">VirtualQuery-метод</span><span class="sxs-lookup"><span data-stu-id="fc3b5-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="fc3b5-126">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая получает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc3b5-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc3b5-127">Remarks</span></span>  
 <span data-ttu-id="fc3b5-128">`IHostMemoryManager`также предоставляет методы для среды CLR получить указатель, посредством которого можно осуществлять запросы памяти в куче и получать уровень нехватки памяти в процессе, предоставленным узлом.</span><span class="sxs-lookup"><span data-stu-id="fc3b5-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc3b5-129">Требования</span><span class="sxs-lookup"><span data-stu-id="fc3b5-129">Requirements</span></span>  
 <span data-ttu-id="fc3b5-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc3b5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc3b5-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc3b5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc3b5-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc3b5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc3b5-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc3b5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3b5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fc3b5-134">See Also</span></span>  
 [<span data-ttu-id="fc3b5-135">IHostMalloc-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fc3b5-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="fc3b5-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="fc3b5-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
