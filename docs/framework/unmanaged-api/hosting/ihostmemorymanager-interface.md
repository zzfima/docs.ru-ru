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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f34ed1796f6fa411d31fca83baeff693f85d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137362"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="b054d-102">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="b054d-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="b054d-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для выполнения запросов виртуальной памяти через узел, вместо использования стандартных функций Win32 виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="b054d-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b054d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b054d-104">Methods</span></span>  
  
|<span data-ttu-id="b054d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b054d-105">Method</span></span>|<span data-ttu-id="b054d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b054d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b054d-107">Метод AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="b054d-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="b054d-108">Уведомляет основное приложение, что общеязыковая среда выполнения (CLR) получила указанную память от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b054d-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="b054d-109">Метод CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="b054d-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="b054d-110">Получает указатель интерфейса на [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) экземпляр, который используется для запроса выделения памяти из кучи, созданной приложением.</span><span class="sxs-lookup"><span data-stu-id="b054d-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="b054d-111">Метод GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="b054d-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="b054d-112">Получает объем физической памяти, используемой в настоящее время, сообщаемое приложением.</span><span class="sxs-lookup"><span data-stu-id="b054d-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="b054d-113">Метод NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="b054d-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="b054d-114">Уведомляет основное приложение, что среда CLR будет пытаться использовать указанный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="b054d-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="b054d-115">Метод RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="b054d-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="b054d-116">Регистрирует указатель на функцию обратного вызова, основное приложение вызывает для уведомления среды CLR текущую загрузку памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b054d-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="b054d-117">Метод ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="b054d-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="b054d-118">Уведомляет основное приложение завершение среды CLR с помощью указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="b054d-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="b054d-119">Метод VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="b054d-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="b054d-120">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая резервирует или фиксирует диапазон страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="b054d-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="b054d-121">Метод VirtualFree</span><span class="sxs-lookup"><span data-stu-id="b054d-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="b054d-122">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая освобождает, разблокирует или освобождает и разблокирует диапазон страниц в пространстве виртуальных адресов вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="b054d-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="b054d-123">Метод VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="b054d-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="b054d-124">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая изменяет защиту на области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="b054d-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="b054d-125">Метод VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="b054d-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="b054d-126">Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая получает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="b054d-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b054d-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="b054d-127">Remarks</span></span>  
 `IHostMemoryManager` <span data-ttu-id="b054d-128">также предоставляет методы для среды CLR для получения указателя в которых можно осуществлять запросы памяти в куче, а также получить уровень нехватки памяти в процессе, согласно данным узлом.</span><span class="sxs-lookup"><span data-stu-id="b054d-128">also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b054d-129">Требования</span><span class="sxs-lookup"><span data-stu-id="b054d-129">Requirements</span></span>  
 <span data-ttu-id="b054d-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b054d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b054d-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b054d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b054d-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b054d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b054d-133">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b054d-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b054d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b054d-134">See also</span></span>

- [<span data-ttu-id="b054d-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="b054d-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="b054d-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b054d-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
