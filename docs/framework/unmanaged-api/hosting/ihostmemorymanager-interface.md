---
title: Интерфейс IHostMemoryManager
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: bc05d76795f20d28d6d2899d61dc4674ebfdca8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128652"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="d9b88-102">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="d9b88-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="d9b88-103">Предоставляет методы, позволяющие среде CLR выполнять запросы к виртуальной памяти через основное приложение вместо использования стандартных функций виртуальной памяти Win32.</span><span class="sxs-lookup"><span data-stu-id="d9b88-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9b88-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d9b88-104">Methods</span></span>  
  
|<span data-ttu-id="d9b88-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d9b88-105">Method</span></span>|<span data-ttu-id="d9b88-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d9b88-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9b88-107">Метод AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="d9b88-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="d9b88-108">Уведомляет узел о том, что среда CLR получила указанную память из операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d9b88-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="d9b88-109">Метод CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="d9b88-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="d9b88-110">Возвращает указатель интерфейса на экземпляр [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) , который используется для запроса выделения памяти из кучи, созданного узлом.</span><span class="sxs-lookup"><span data-stu-id="d9b88-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="d9b88-111">Метод GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="d9b88-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="d9b88-112">Возвращает объем используемой в данный момент физической памяти, сообщаемой узлом.</span><span class="sxs-lookup"><span data-stu-id="d9b88-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="d9b88-113">Метод NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="d9b88-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="d9b88-114">Уведомляет узел о том, что среда CLR будет пытаться использовать указанную память.</span><span class="sxs-lookup"><span data-stu-id="d9b88-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="d9b88-115">Метод RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="d9b88-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="d9b88-116">Регистрирует указатель на функцию обратного вызова, которая вызывается хостом для уведомления среды CLR о текущей загрузке памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9b88-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="d9b88-117">Метод ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="d9b88-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="d9b88-118">Уведомляет узел о том, что среда CLR завершила работу с заданной памятью.</span><span class="sxs-lookup"><span data-stu-id="d9b88-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="d9b88-119">Метод VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="d9b88-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="d9b88-120">Служит логической оболочкой для соответствующей функции Win32, которая резервирует или фиксирует область страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="d9b88-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="d9b88-121">Метод VirtualFree</span><span class="sxs-lookup"><span data-stu-id="d9b88-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="d9b88-122">Служит логической оболочкой для соответствующей функции Win32, которая выдает, выдает или освобождает и отменяет выделение области страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="d9b88-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="d9b88-123">Метод VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="d9b88-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="d9b88-124">Служит логической оболочкой для соответствующей функции Win32, которая изменяет защиту в области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="d9b88-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="d9b88-125">Метод VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="d9b88-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="d9b88-126">Служит логической оболочкой для соответствующей функции Win32, которая получает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="d9b88-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9b88-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="d9b88-127">Remarks</span></span>  
 <span data-ttu-id="d9b88-128">`IHostMemoryManager` также предоставляет методам среды CLR возможность получить указатель, с помощью которого можно сделать запросы к памяти в куче и получить уровень нехватки памяти в процессе, сообщаемый узлом.</span><span class="sxs-lookup"><span data-stu-id="d9b88-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9b88-129">Требования</span><span class="sxs-lookup"><span data-stu-id="d9b88-129">Requirements</span></span>  
 <span data-ttu-id="d9b88-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9b88-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9b88-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d9b88-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9b88-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d9b88-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9b88-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9b88-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b88-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d9b88-134">See also</span></span>

- [<span data-ttu-id="d9b88-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="d9b88-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="d9b88-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d9b88-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
