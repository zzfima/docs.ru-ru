---
title: Метод IHostMemoryManager::VirtualQuery
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16d146766786f129d6da38bde1126ce8afe5e70f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963696"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="f4ee0-102">Метод IHostMemoryManager::VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="f4ee0-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="f4ee0-103">Служит логической оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="f4ee0-104">Реализация `VirtualQuery` Win32 извлекает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4ee0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4ee0-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4ee0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4ee0-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="f4ee0-107">окне Указатель на адрес в виртуальной памяти для запроса.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="f4ee0-108">заполняет Указатель на структуру, содержащую сведения о заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f4ee0-109">окне Размер (в байтах) буфера, на который `lpBuffer` указывает.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="f4ee0-110">заполняет Указатель на число байтов, возвращенных информационным буфером.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4ee0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f4ee0-111">Return Value</span></span>  
  
|<span data-ttu-id="f4ee0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4ee0-112">HRESULT</span></span>|<span data-ttu-id="f4ee0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f4ee0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4ee0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4ee0-114">S_OK</span></span>|<span data-ttu-id="f4ee0-115">`VirtualQuery`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="f4ee0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4ee0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4ee0-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4ee0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4ee0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4ee0-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-119">The call timed out.</span></span>|  
|<span data-ttu-id="f4ee0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4ee0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4ee0-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4ee0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4ee0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4ee0-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4ee0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4ee0-124">E_FAIL</span></span>|<span data-ttu-id="f4ee0-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4ee0-126">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4ee0-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4ee0-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4ee0-128">Remarks</span></span>  
 <span data-ttu-id="f4ee0-129">`VirtualQuery`предоставляет сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="f4ee0-130">Эта реализация задает для `pResult` параметра значение, равное числу байтов, возвращаемых в информационном буфере, и возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="f4ee0-131">В функции Win32 `VirtualQuery` возвращаемое значение — это размер буфера.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="f4ee0-132">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f4ee0-133">Реализация `VirtualQuery` операционной системы не вызывает взаимоблокировок и может выполняться до завершения с помощью случайных потоков, приостановленных в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="f4ee0-134">При реализации размещенной версии этого метода следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="f4ee0-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4ee0-135">Требования</span><span class="sxs-lookup"><span data-stu-id="f4ee0-135">Requirements</span></span>  
 <span data-ttu-id="f4ee0-136">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4ee0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4ee0-137">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4ee0-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4ee0-138">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4ee0-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4ee0-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4ee0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ee0-140">См. также</span><span class="sxs-lookup"><span data-stu-id="f4ee0-140">See also</span></span>

- [<span data-ttu-id="f4ee0-141">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="f4ee0-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
