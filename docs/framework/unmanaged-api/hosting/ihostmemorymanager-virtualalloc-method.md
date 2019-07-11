---
title: Метод IHostMemoryManager::VirtualAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a0764cb212a95412a4dcf9455b7648ee863951e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767667"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="2e948-102">Метод IHostMemoryManager::VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="2e948-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="2e948-103">Служит в качестве логической программой-оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="2e948-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="2e948-104">Реализация Win32 `VirtualAlloc` резервирует или фиксирует диапазон страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="2e948-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e948-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e948-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e948-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e948-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="2e948-107">[in] Указатель на начальный адрес области, чтобы выделить.</span><span class="sxs-lookup"><span data-stu-id="2e948-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="2e948-108">[in] Размер в байтах, области.</span><span class="sxs-lookup"><span data-stu-id="2e948-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="2e948-109">[in] Тип выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="2e948-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="2e948-110">[in] Защита памяти для области страниц, которые должны быть выделены.</span><span class="sxs-lookup"><span data-stu-id="2e948-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="2e948-111">[in] [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) значение, указывающее влияние ошибки выделения.</span><span class="sxs-lookup"><span data-stu-id="2e948-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="2e948-112">[out] Указатель на начальный адрес в памяти, или значение null, если запрос не может быть удовлетворен.</span><span class="sxs-lookup"><span data-stu-id="2e948-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e948-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2e948-113">Return Value</span></span>  
  
|<span data-ttu-id="2e948-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e948-114">HRESULT</span></span>|<span data-ttu-id="2e948-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2e948-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e948-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e948-116">S_OK</span></span>|<span data-ttu-id="2e948-117">`VirtualAlloc` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2e948-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="2e948-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e948-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e948-119">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2e948-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e948-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e948-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e948-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2e948-121">The call timed out.</span></span>|  
|<span data-ttu-id="2e948-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e948-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e948-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2e948-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e948-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e948-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e948-125">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2e948-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e948-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e948-126">E_FAIL</span></span>|<span data-ttu-id="2e948-127">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="2e948-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e948-128">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2e948-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e948-129">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2e948-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2e948-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2e948-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2e948-131">Не хватает памяти была доступна для выполнения запроса на выделение</span><span class="sxs-lookup"><span data-stu-id="2e948-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e948-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e948-132">Remarks</span></span>  
 <span data-ttu-id="2e948-133">Для резервирования области в адресном пространстве процесса путем вызова `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="2e948-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="2e948-134">`pAddress` Параметр содержит начальный адрес блока памяти, который вы хотите.</span><span class="sxs-lookup"><span data-stu-id="2e948-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="2e948-135">Этот параметр обычно задается значение null.</span><span class="sxs-lookup"><span data-stu-id="2e948-135">This parameter is typically set to null.</span></span> <span data-ttu-id="2e948-136">Операционная система хранит запись о диапазонах свободных адресов, доступных для процесса.</span><span class="sxs-lookup"><span data-stu-id="2e948-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="2e948-137">Объект `pAddress` значение null предписывает системе резервирования считает нужным.</span><span class="sxs-lookup"><span data-stu-id="2e948-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="2e948-138">Кроме того можно предоставить конкретных начальный адрес для блока памяти.</span><span class="sxs-lookup"><span data-stu-id="2e948-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="2e948-139">В обоих случаях выходной параметр `ppMem` возвращается как указатель на выделенную память.</span><span class="sxs-lookup"><span data-stu-id="2e948-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="2e948-140">Сама функция возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2e948-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="2e948-141">Win32 `VirtualAlloc` функция не имеет `ppMem` параметра и вместо этого возвращает указатель на выделенную память.</span><span class="sxs-lookup"><span data-stu-id="2e948-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="2e948-142">Дополнительные сведения см. в документации платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="2e948-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e948-143">Требования</span><span class="sxs-lookup"><span data-stu-id="2e948-143">Requirements</span></span>  
 <span data-ttu-id="2e948-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e948-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e948-145">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e948-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e948-146">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e948-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e948-147">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e948-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e948-148">См. также</span><span class="sxs-lookup"><span data-stu-id="2e948-148">See also</span></span>

- [<span data-ttu-id="2e948-149">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="2e948-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
