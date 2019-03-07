---
title: Метод IHostMemoryManager::VirtualProtect
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b712b7e88e6cb5693c0823799e0980d90e34ff0a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492612"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="e0358-102">Метод IHostMemoryManager::VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="e0358-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="e0358-103">Служит в качестве логической программой-оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="e0358-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="e0358-104">Реализация Win32 `VirtualProtect` изменяет защиту на области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="e0358-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0358-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0358-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0358-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0358-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="e0358-107">[in] Указатель на базовый адрес виртуальной памяти, атрибуты которого защиты должны быть изменены.</span><span class="sxs-lookup"><span data-stu-id="e0358-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="e0358-108">[in] Размер в байтах, области страниц памяти, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e0358-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="e0358-109">[in] Тип защиты памяти, чтобы применить.</span><span class="sxs-lookup"><span data-stu-id="e0358-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="e0358-110">[out] Указатель на предыдущее значение защиты памяти.</span><span class="sxs-lookup"><span data-stu-id="e0358-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0358-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0358-111">Return Value</span></span>  
  
|<span data-ttu-id="e0358-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0358-112">HRESULT</span></span>|<span data-ttu-id="e0358-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e0358-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0358-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0358-114">S_OK</span></span>|<span data-ttu-id="e0358-115">`VirtualProtect` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e0358-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="e0358-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0358-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0358-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e0358-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0358-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0358-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0358-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e0358-119">The call timed out.</span></span>|  
|<span data-ttu-id="e0358-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0358-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0358-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e0358-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0358-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0358-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0358-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e0358-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0358-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0358-124">E_FAIL</span></span>|<span data-ttu-id="e0358-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e0358-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0358-126">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e0358-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0358-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e0358-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0358-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0358-128">Remarks</span></span>  
 <span data-ttu-id="e0358-129">Эта реализация `VirtualProtect` возвращает значение HRESULT, тогда как реализация Win32 возвращает ненулевое значение в случае успеха и нулевое значение, указывающее на ошибку.</span><span class="sxs-lookup"><span data-stu-id="e0358-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="e0358-130">Дополнительные сведения см. в документации платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="e0358-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0358-131">Требования</span><span class="sxs-lookup"><span data-stu-id="e0358-131">Requirements</span></span>  
 <span data-ttu-id="e0358-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0358-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0358-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0358-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0358-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0358-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0358-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0358-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0358-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e0358-136">See also</span></span>
- [<span data-ttu-id="e0358-137">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="e0358-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
