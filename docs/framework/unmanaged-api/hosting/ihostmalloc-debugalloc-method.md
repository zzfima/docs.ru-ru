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
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178036"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="9c516-102">Метод IHostMAlloc::DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="9c516-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="9c516-103">Просит хост выделить указанное количество памяти из кучи и дополнительно отслеживать, где была выделена память.</span><span class="sxs-lookup"><span data-stu-id="9c516-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c516-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c516-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c516-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c516-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="9c516-106">(в) Размер в байтах текущего запроса распределения памяти.</span><span class="sxs-lookup"><span data-stu-id="9c516-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="9c516-107">(в) Одно из значений [EMemoryCriticalLevel,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) указывающее на последствия сбоя выделения.</span><span class="sxs-lookup"><span data-stu-id="9c516-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="9c516-108">(в) Кодовый файл отладки выполнения.</span><span class="sxs-lookup"><span data-stu-id="9c516-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="9c516-109">(в) Номер строки, в `pszFileName` котором было запрошено распределение.</span><span class="sxs-lookup"><span data-stu-id="9c516-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="9c516-110">(ваут) Указатель на выделенную память или null, если запрос не может быть завершен.</span><span class="sxs-lookup"><span data-stu-id="9c516-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c516-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9c516-111">Return Value</span></span>  
  
|<span data-ttu-id="9c516-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c516-112">HRESULT</span></span>|<span data-ttu-id="9c516-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9c516-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c516-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c516-114">S_OK</span></span>|<span data-ttu-id="9c516-115">`DebugAlloc`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="9c516-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="9c516-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c516-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c516-117">CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9c516-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c516-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c516-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c516-119">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="9c516-119">The call timed out.</span></span>|  
|<span data-ttu-id="9c516-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c516-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c516-121">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="9c516-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c516-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c516-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c516-123">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="9c516-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c516-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c516-124">E_FAIL</span></span>|<span data-ttu-id="9c516-125">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="9c516-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c516-126">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="9c516-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c516-127">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9c516-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9c516-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9c516-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9c516-129">Недостаточно памяти было доступно для завершения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="9c516-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c516-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c516-130">Remarks</span></span>  
 <span data-ttu-id="9c516-131">CLR получает указатель интерфейса на экземпляр [IHostMalloc,](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) позвонив в [iHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9c516-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="9c516-132">`DebugAlloc`позволяет времени выполнения получать информацию о файле кода для использования во время отладки.</span><span class="sxs-lookup"><span data-stu-id="9c516-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c516-133">Требования</span><span class="sxs-lookup"><span data-stu-id="9c516-133">Requirements</span></span>  
 <span data-ttu-id="9c516-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c516-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c516-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9c516-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c516-136">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c516-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c516-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c516-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c516-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9c516-138">See also</span></span>

- [<span data-ttu-id="9c516-139">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="9c516-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="9c516-140">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="9c516-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
