---
title: Метод IHostMemoryManager::VirtualFree
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a60d954cf4331d46a4667afba1e9dee0d214f0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767679"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="b9b9c-102">Метод IHostMemoryManager::VirtualFree</span><span class="sxs-lookup"><span data-stu-id="b9b9c-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="b9b9c-103">Служит в качестве логической программой-оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="b9b9c-104">Реализация Win32 `VirtualFree` освобождает, разблокирует или освобождает и разблокирует диапазон страниц в пространстве виртуальных адресов вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b9c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9b9c-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9b9c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9b9c-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="b9b9c-107">[in] Указатель на базовый адрес страниц виртуальной памяти, который требуется освободить.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="b9b9c-108">[in] Размер в байтах, области, который требуется освободить.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="b9b9c-109">[in] Тип операции освобождения.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9b9c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9b9c-110">Return Value</span></span>  
  
|<span data-ttu-id="b9b9c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9b9c-111">HRESULT</span></span>|<span data-ttu-id="b9b9c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b9b9c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9b9c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9b9c-113">S_OK</span></span>|<span data-ttu-id="b9b9c-114">`VirtualFree` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="b9b9c-115">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9b9c-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9b9c-116">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9b9c-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9b9c-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9b9c-118">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-118">The call timed out.</span></span>|  
|<span data-ttu-id="b9b9c-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9b9c-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9b9c-120">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9b9c-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9b9c-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9b9c-122">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9b9c-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9b9c-123">E_FAIL</span></span>|<span data-ttu-id="b9b9c-124">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9b9c-125">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9b9c-126">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b9b9c-127">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="b9b9c-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="b9b9c-128">Для освобождения памяти, который не был выделен через узел была предпринята.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9b9c-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9b9c-129">Remarks</span></span>  
 <span data-ttu-id="b9b9c-130">`VirtualFree` Освобождает страницы виртуальной памяти, связанные с `lpAddress` параметры с помощью предыдущего вызова [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) функции.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="b9b9c-131">Пытается освободить память, выделенную через узел не должен возвращать значение HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="b9b9c-132">Семантика идентична семантике реализация Win32 `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="b9b9c-133">Дополнительные сведения см. в документации платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="b9b9c-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b9c-134">Требования</span><span class="sxs-lookup"><span data-stu-id="b9b9c-134">Requirements</span></span>  
 <span data-ttu-id="b9b9c-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b9c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b9c-136">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9b9c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9b9c-137">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9b9c-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9b9c-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b9c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b9c-139">См. также</span><span class="sxs-lookup"><span data-stu-id="b9b9c-139">See also</span></span>

- [<span data-ttu-id="b9b9c-140">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="b9b9c-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="b9b9c-141">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="b9b9c-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
