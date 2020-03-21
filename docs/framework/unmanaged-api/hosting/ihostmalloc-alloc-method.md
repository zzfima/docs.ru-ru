---
title: Метод IHostMAlloc::Alloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176309"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="b87eb-102">Метод IHostMAlloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="b87eb-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="b87eb-103">Запросы, чтобы хост выделил указанное количество памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="b87eb-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b87eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b87eb-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b87eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b87eb-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="b87eb-106">(в) Размер в байтах текущего запроса распределения памяти.</span><span class="sxs-lookup"><span data-stu-id="b87eb-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="b87eb-107">(в) Одно из значений [EMemoryCriticalLevel,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) указывающее на последствия сбоя выделения.</span><span class="sxs-lookup"><span data-stu-id="b87eb-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="b87eb-108">(ваут) Указатель на выделенную память или null, если запрос не может быть завершен.</span><span class="sxs-lookup"><span data-stu-id="b87eb-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b87eb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b87eb-109">Return Value</span></span>  
  
|<span data-ttu-id="b87eb-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b87eb-110">HRESULT</span></span>|<span data-ttu-id="b87eb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b87eb-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b87eb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b87eb-112">S_OK</span></span>|<span data-ttu-id="b87eb-113">`Alloc`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="b87eb-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="b87eb-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b87eb-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b87eb-115">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b87eb-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b87eb-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b87eb-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b87eb-117">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="b87eb-117">The call timed out.</span></span>|  
|<span data-ttu-id="b87eb-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b87eb-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b87eb-119">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="b87eb-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b87eb-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b87eb-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b87eb-121">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="b87eb-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b87eb-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b87eb-122">E_FAIL</span></span>|<span data-ttu-id="b87eb-123">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="b87eb-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b87eb-124">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="b87eb-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b87eb-125">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b87eb-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b87eb-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b87eb-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b87eb-127">Недостаточно памяти было доступно для завершения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="b87eb-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b87eb-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="b87eb-128">Remarks</span></span>  
 <span data-ttu-id="b87eb-129">CLR получает указатель интерфейса `IHostMalloc` к экземпляру, позвонив в метод [IHostMemoryManager::CreateMalloc.](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)</span><span class="sxs-lookup"><span data-stu-id="b87eb-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b87eb-130">Требования</span><span class="sxs-lookup"><span data-stu-id="b87eb-130">Requirements</span></span>  
 <span data-ttu-id="b87eb-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b87eb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b87eb-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b87eb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b87eb-133">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b87eb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b87eb-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b87eb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b87eb-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b87eb-135">See also</span></span>

- [<span data-ttu-id="b87eb-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="b87eb-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="b87eb-137">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="b87eb-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
