---
title: Метод IHostMAlloc::DebugAlloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e089d133374f112dea13e91f9bd571bd2b5af07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796725"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="58c95-102">Метод IHostMAlloc::DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="58c95-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="58c95-103">Запрашивает, что узел выделить указанный объем памяти из кучи и Кроме того, отслеживать, где была выделена память.</span><span class="sxs-lookup"><span data-stu-id="58c95-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58c95-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c95-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="58c95-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="58c95-106">[in] Размер в байтах, выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="58c95-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="58c95-107">[in] Один из [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) значения, указывающие влияние ошибки выделения.</span><span class="sxs-lookup"><span data-stu-id="58c95-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="58c95-108">[in] В файл кода отлаживаемому исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="58c95-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="58c95-109">[in] Номер строки в `pszFileName` которой была запрошена операция выделения.</span><span class="sxs-lookup"><span data-stu-id="58c95-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="58c95-110">[out] Указатель на выделенную память, или значение null, если не удалось выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="58c95-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58c95-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="58c95-111">Return Value</span></span>  
  
|<span data-ttu-id="58c95-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58c95-112">HRESULT</span></span>|<span data-ttu-id="58c95-113">Описание</span><span class="sxs-lookup"><span data-stu-id="58c95-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58c95-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="58c95-114">S_OK</span></span>|<span data-ttu-id="58c95-115">`DebugAlloc` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="58c95-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="58c95-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58c95-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58c95-117">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="58c95-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58c95-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58c95-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58c95-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="58c95-119">The call timed out.</span></span>|  
|<span data-ttu-id="58c95-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58c95-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58c95-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="58c95-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58c95-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58c95-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58c95-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="58c95-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58c95-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58c95-124">E_FAIL</span></span>|<span data-ttu-id="58c95-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="58c95-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58c95-126">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="58c95-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58c95-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="58c95-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="58c95-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="58c95-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="58c95-129">Недостаточно памяти, доступного для выполнения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="58c95-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58c95-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="58c95-130">Remarks</span></span>  
 <span data-ttu-id="58c95-131">Среда CLR получает указатель интерфейса на [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) экземпляра путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="58c95-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="58c95-132">`DebugAlloc` позволяет среде выполнения получить сведения о файле кода для использования во время отладки.</span><span class="sxs-lookup"><span data-stu-id="58c95-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c95-133">Требования</span><span class="sxs-lookup"><span data-stu-id="58c95-133">Requirements</span></span>  
 <span data-ttu-id="58c95-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58c95-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c95-135">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58c95-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58c95-136">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58c95-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58c95-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c95-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c95-138">См. также</span><span class="sxs-lookup"><span data-stu-id="58c95-138">See also</span></span>

- [<span data-ttu-id="58c95-139">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="58c95-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="58c95-140">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="58c95-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
