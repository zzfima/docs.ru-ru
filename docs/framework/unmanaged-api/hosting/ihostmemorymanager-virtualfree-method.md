---
title: "Метод IHostMemoryManager::VirtualFree"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualFree
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 468228101403c7ce3c123401e906e3ccbe301e28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="cd4ef-102">Метод IHostMemoryManager::VirtualFree</span><span class="sxs-lookup"><span data-stu-id="cd4ef-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="cd4ef-103">Служит в качестве логической программой-оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="cd4ef-104">Реализация Win32 `VirtualFree` освобождает, разблокирует или освобождает и разблокирует диапазон страниц в пределах виртуального адресного пространства вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4ef-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd4ef-105">Syntax</span></span>  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd4ef-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd4ef-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="cd4ef-107">[in] Указатель на базовый адрес для освобождения страниц виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="cd4ef-108">[in] Размер в байтах, области, чтобы освободить.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="cd4ef-109">[in] Тип операции освобождения.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd4ef-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cd4ef-110">Return Value</span></span>  
  
|<span data-ttu-id="cd4ef-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd4ef-111">HRESULT</span></span>|<span data-ttu-id="cd4ef-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cd4ef-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd4ef-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd4ef-113">S_OK</span></span>|<span data-ttu-id="cd4ef-114">`VirtualFree`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="cd4ef-115">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd4ef-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd4ef-116">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd4ef-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd4ef-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd4ef-118">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-118">The call timed out.</span></span>|  
|<span data-ttu-id="cd4ef-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd4ef-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd4ef-120">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd4ef-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd4ef-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd4ef-122">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd4ef-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd4ef-123">E_FAIL</span></span>|<span data-ttu-id="cd4ef-124">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd4ef-125">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd4ef-126">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cd4ef-127">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="cd4ef-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="cd4ef-128">Была предпринята попытка освободить память, выделенная не через узел.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd4ef-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd4ef-129">Remarks</span></span>  
 <span data-ttu-id="cd4ef-130">`VirtualFree`Освобождает страницы виртуальной памяти, связанные с `lpAddress` параметр по предыдущим вызовом [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) функции.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="cd4ef-131">Пытается освободить память, выделенная через узел не должен возвращать значение HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="cd4ef-132">Семантика идентична реализация Win32 `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="cd4ef-133">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="cd4ef-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd4ef-134">Требования</span><span class="sxs-lookup"><span data-stu-id="cd4ef-134">Requirements</span></span>  
 <span data-ttu-id="cd4ef-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd4ef-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4ef-136">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd4ef-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd4ef-137">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd4ef-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd4ef-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4ef-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4ef-139">См. также</span><span class="sxs-lookup"><span data-stu-id="cd4ef-139">See Also</span></span>  
 [<span data-ttu-id="cd4ef-140">IHostMemoryManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="cd4ef-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="cd4ef-141">IHostMalloc-интерфейс</span><span class="sxs-lookup"><span data-stu-id="cd4ef-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
