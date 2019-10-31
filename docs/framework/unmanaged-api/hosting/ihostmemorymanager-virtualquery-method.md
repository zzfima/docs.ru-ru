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
ms.openlocfilehash: 00ec0b92a9f7151ee9b831c85548c4f61d87af68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192036"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="2af35-102">Метод IHostMemoryManager::VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="2af35-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="2af35-103">Служит логической оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="2af35-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="2af35-104">Реализация `VirtualQuery` Win32 извлекает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="2af35-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af35-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2af35-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2af35-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2af35-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="2af35-107">окне Указатель на адрес в виртуальной памяти для запроса.</span><span class="sxs-lookup"><span data-stu-id="2af35-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="2af35-108">заполняет Указатель на структуру, содержащую сведения о заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="2af35-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="2af35-109">окне Размер (в байтах) буфера, на который `lpBuffer` указывает.</span><span class="sxs-lookup"><span data-stu-id="2af35-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="2af35-110">заполняет Указатель на число байтов, возвращенных информационным буфером.</span><span class="sxs-lookup"><span data-stu-id="2af35-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2af35-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2af35-111">Return Value</span></span>  
  
|<span data-ttu-id="2af35-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2af35-112">HRESULT</span></span>|<span data-ttu-id="2af35-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2af35-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2af35-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2af35-114">S_OK</span></span>|<span data-ttu-id="2af35-115">`VirtualQuery` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2af35-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="2af35-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2af35-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2af35-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2af35-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2af35-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2af35-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2af35-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2af35-119">The call timed out.</span></span>|  
|<span data-ttu-id="2af35-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2af35-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2af35-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2af35-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2af35-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2af35-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2af35-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2af35-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2af35-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2af35-124">E_FAIL</span></span>|<span data-ttu-id="2af35-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2af35-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2af35-126">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2af35-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2af35-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2af35-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2af35-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="2af35-128">Remarks</span></span>  
 <span data-ttu-id="2af35-129">`VirtualQuery` предоставляет сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="2af35-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="2af35-130">Эта реализация задает для параметра `pResult` значение, равное числу байтов, возвращаемых в информационном буфере, и возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2af35-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="2af35-131">В функции `VirtualQuery` Win32 возвращаемое значение является размером буфера.</span><span class="sxs-lookup"><span data-stu-id="2af35-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="2af35-132">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="2af35-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2af35-133">Реализация `VirtualQuery` в операционной системе не вызывает взаимоблокировки и может выполняться до завершения с помощью случайных потоков, приостановленных в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="2af35-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="2af35-134">При реализации размещенной версии этого метода следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="2af35-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2af35-135">Требования</span><span class="sxs-lookup"><span data-stu-id="2af35-135">Requirements</span></span>  
 <span data-ttu-id="2af35-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2af35-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2af35-137">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2af35-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2af35-138">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2af35-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2af35-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2af35-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af35-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2af35-140">See also</span></span>

- [<span data-ttu-id="2af35-141">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="2af35-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
