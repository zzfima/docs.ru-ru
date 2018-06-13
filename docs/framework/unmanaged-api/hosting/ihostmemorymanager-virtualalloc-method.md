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
ms.openlocfilehash: fe54aed47d240be37ab9dbc5381235c4e962f1f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440318"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="58b0c-102">Метод IHostMemoryManager::VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="58b0c-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="58b0c-103">Служит в качестве логической программой-оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="58b0c-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="58b0c-104">Реализация Win32 `VirtualAlloc` резервирует или фиксирует диапазон страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="58b0c-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b0c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58b0c-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58b0c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="58b0c-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="58b0c-107">[in] Указатель на начальный адрес области, чтобы выделить.</span><span class="sxs-lookup"><span data-stu-id="58b0c-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="58b0c-108">[in] Размер в байтах, области.</span><span class="sxs-lookup"><span data-stu-id="58b0c-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="58b0c-109">[in] Тип выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="58b0c-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="58b0c-110">[in] Защита памяти для области страницы должен быть выделен.</span><span class="sxs-lookup"><span data-stu-id="58b0c-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="58b0c-111">[in] [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) значение, указывающее влияние ошибки выделения.</span><span class="sxs-lookup"><span data-stu-id="58b0c-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="58b0c-112">[out] Указатель на начальный адрес памяти или значение null, если запрос не может быть удовлетворен.</span><span class="sxs-lookup"><span data-stu-id="58b0c-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58b0c-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="58b0c-113">Return Value</span></span>  
  
|<span data-ttu-id="58b0c-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58b0c-114">HRESULT</span></span>|<span data-ttu-id="58b0c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="58b0c-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58b0c-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="58b0c-116">S_OK</span></span>|<span data-ttu-id="58b0c-117">`VirtualAlloc` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="58b0c-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="58b0c-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58b0c-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58b0c-119">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="58b0c-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58b0c-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58b0c-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58b0c-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="58b0c-121">The call timed out.</span></span>|  
|<span data-ttu-id="58b0c-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58b0c-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58b0c-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="58b0c-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58b0c-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58b0c-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58b0c-125">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="58b0c-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58b0c-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58b0c-126">E_FAIL</span></span>|<span data-ttu-id="58b0c-127">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="58b0c-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58b0c-128">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="58b0c-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58b0c-129">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="58b0c-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="58b0c-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="58b0c-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="58b0c-131">Не хватает памяти была доступна для выполнения запроса на выделение</span><span class="sxs-lookup"><span data-stu-id="58b0c-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58b0c-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="58b0c-132">Remarks</span></span>  
 <span data-ttu-id="58b0c-133">Для резервирования области в адресном пространстве процесса путем вызова `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="58b0c-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="58b0c-134">`pAddress` Параметр содержит начальный адрес блока памяти, требуется.</span><span class="sxs-lookup"><span data-stu-id="58b0c-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="58b0c-135">Этот параметр обычно устанавливается в значение null.</span><span class="sxs-lookup"><span data-stu-id="58b0c-135">This parameter is typically set to null.</span></span> <span data-ttu-id="58b0c-136">Операционная система хранит запись о диапазонах свободных адресов, доступных для процесса.</span><span class="sxs-lookup"><span data-stu-id="58b0c-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="58b0c-137">Объект `pAddress` значение null предписывает системе резервирования размера.</span><span class="sxs-lookup"><span data-stu-id="58b0c-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="58b0c-138">Кроме того можно предоставить определенный адрес, начиная для блока памяти.</span><span class="sxs-lookup"><span data-stu-id="58b0c-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="58b0c-139">В обоих случаях выходной параметр `ppMem` возвращается как указатель на выделенную память.</span><span class="sxs-lookup"><span data-stu-id="58b0c-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="58b0c-140">Сама функция возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="58b0c-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="58b0c-141">Win32 `VirtualAlloc` функция не имеет `ppMem` параметра и вместо этого возвращает указатель на выделенную память.</span><span class="sxs-lookup"><span data-stu-id="58b0c-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="58b0c-142">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="58b0c-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58b0c-143">Требования</span><span class="sxs-lookup"><span data-stu-id="58b0c-143">Requirements</span></span>  
 <span data-ttu-id="58b0c-144">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b0c-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b0c-145">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58b0c-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58b0c-146">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58b0c-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58b0c-147">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b0c-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b0c-148">См. также</span><span class="sxs-lookup"><span data-stu-id="58b0c-148">See Also</span></span>  
 [<span data-ttu-id="58b0c-149">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="58b0c-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
