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
ms.openlocfilehash: e3ce303e8bcf33d192dbc7e2447ea6737577dcc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554885"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="16da0-102">Метод IHostMAlloc::DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="16da0-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="16da0-103">Запрашивает, что узел выделить указанный объем памяти из кучи и Кроме того, отслеживать, где была выделена память.</span><span class="sxs-lookup"><span data-stu-id="16da0-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16da0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16da0-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16da0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16da0-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="16da0-106">[in] Размер в байтах, выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="16da0-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="16da0-107">[in] Один из [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) значения, указывающие влияние ошибки выделения.</span><span class="sxs-lookup"><span data-stu-id="16da0-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="16da0-108">[in] В файл кода отлаживаемому исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="16da0-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="16da0-109">[in] Номер строки в `pszFileName` которой была запрошена операция выделения.</span><span class="sxs-lookup"><span data-stu-id="16da0-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="16da0-110">[out] Указатель на выделенную память, или значение null, если не удалось выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="16da0-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16da0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="16da0-111">Return Value</span></span>  
  
|<span data-ttu-id="16da0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16da0-112">HRESULT</span></span>|<span data-ttu-id="16da0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="16da0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16da0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="16da0-114">S_OK</span></span>|<span data-ttu-id="16da0-115">`DebugAlloc` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="16da0-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="16da0-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16da0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16da0-117">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="16da0-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16da0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16da0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16da0-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="16da0-119">The call timed out.</span></span>|  
|<span data-ttu-id="16da0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16da0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16da0-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="16da0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16da0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16da0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16da0-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="16da0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16da0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16da0-124">E_FAIL</span></span>|<span data-ttu-id="16da0-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="16da0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16da0-126">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="16da0-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16da0-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="16da0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="16da0-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="16da0-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="16da0-129">Недостаточно памяти, доступного для выполнения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="16da0-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16da0-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="16da0-130">Remarks</span></span>  
 <span data-ttu-id="16da0-131">Среда CLR получает указатель интерфейса на [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) экземпляра путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="16da0-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="16da0-132">`DebugAlloc` позволяет среде выполнения получить сведения о файле кода для использования во время отладки.</span><span class="sxs-lookup"><span data-stu-id="16da0-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16da0-133">Требования</span><span class="sxs-lookup"><span data-stu-id="16da0-133">Requirements</span></span>  
 <span data-ttu-id="16da0-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16da0-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16da0-135">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16da0-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16da0-136">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16da0-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16da0-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16da0-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16da0-138">См. также</span><span class="sxs-lookup"><span data-stu-id="16da0-138">See also</span></span>
- [<span data-ttu-id="16da0-139">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="16da0-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="16da0-140">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="16da0-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
