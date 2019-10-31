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
ms.openlocfilehash: d39ad45e143026f40ffcf1339e923837f9e812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195849"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="fe17f-102">Метод IHostMemoryManager::VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="fe17f-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="fe17f-103">Служит логической оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="fe17f-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="fe17f-104">Реализация `VirtualProtect` в Win32 изменяет защиту в области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="fe17f-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe17f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe17f-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe17f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe17f-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="fe17f-107">окне Указатель на базовый адрес виртуальной памяти, атрибуты защиты которой должны быть изменены.</span><span class="sxs-lookup"><span data-stu-id="fe17f-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="fe17f-108">окне Размер (в байтах) области изменяемых страниц памяти.</span><span class="sxs-lookup"><span data-stu-id="fe17f-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="fe17f-109">окне Тип применяемой защиты памяти.</span><span class="sxs-lookup"><span data-stu-id="fe17f-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="fe17f-110">заполняет Указатель на предыдущее значение защиты памяти.</span><span class="sxs-lookup"><span data-stu-id="fe17f-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe17f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe17f-111">Return Value</span></span>  
  
|<span data-ttu-id="fe17f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe17f-112">HRESULT</span></span>|<span data-ttu-id="fe17f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fe17f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe17f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe17f-114">S_OK</span></span>|<span data-ttu-id="fe17f-115">`VirtualProtect` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fe17f-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="fe17f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe17f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe17f-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fe17f-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe17f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe17f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe17f-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fe17f-119">The call timed out.</span></span>|  
|<span data-ttu-id="fe17f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe17f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe17f-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fe17f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe17f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe17f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe17f-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fe17f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe17f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe17f-124">E_FAIL</span></span>|<span data-ttu-id="fe17f-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fe17f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe17f-126">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fe17f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe17f-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fe17f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe17f-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="fe17f-128">Remarks</span></span>  
 <span data-ttu-id="fe17f-129">Эта реализация `VirtualProtect` возвращает значение HRESULT, в то время как реализация Win32 возвращает ненулевое значение, указывающее на успешное выполнение, и нулевое значение для обозначения сбоя.</span><span class="sxs-lookup"><span data-stu-id="fe17f-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="fe17f-130">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="fe17f-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe17f-131">Требования</span><span class="sxs-lookup"><span data-stu-id="fe17f-131">Requirements</span></span>  
 <span data-ttu-id="fe17f-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe17f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe17f-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fe17f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe17f-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe17f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe17f-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe17f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe17f-136">См. также</span><span class="sxs-lookup"><span data-stu-id="fe17f-136">See also</span></span>

- [<span data-ttu-id="fe17f-137">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="fe17f-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
