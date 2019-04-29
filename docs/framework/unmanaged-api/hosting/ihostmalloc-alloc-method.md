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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32499e74e8af9a865347bd800d3db4c303a7344c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796738"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="7dd70-102">Метод IHostMAlloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="7dd70-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="7dd70-103">Запросы, что узел выделить указанный объем памяти из кучи.</span><span class="sxs-lookup"><span data-stu-id="7dd70-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dd70-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dd70-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7dd70-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="7dd70-106">[in] Размер в байтах, выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="7dd70-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="7dd70-107">[in] Один из [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) значения, указывающие влияние ошибки выделения.</span><span class="sxs-lookup"><span data-stu-id="7dd70-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="7dd70-108">[out] Указатель на выделенную память, или значение null, если не удалось выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="7dd70-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7dd70-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7dd70-109">Return Value</span></span>  
  
|<span data-ttu-id="7dd70-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7dd70-110">HRESULT</span></span>|<span data-ttu-id="7dd70-111">Описание</span><span class="sxs-lookup"><span data-stu-id="7dd70-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7dd70-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7dd70-112">S_OK</span></span>|<span data-ttu-id="7dd70-113">`Alloc` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7dd70-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="7dd70-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7dd70-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7dd70-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7dd70-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7dd70-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7dd70-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7dd70-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7dd70-117">The call timed out.</span></span>|  
|<span data-ttu-id="7dd70-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7dd70-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7dd70-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7dd70-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7dd70-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7dd70-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7dd70-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7dd70-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7dd70-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7dd70-122">E_FAIL</span></span>|<span data-ttu-id="7dd70-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="7dd70-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7dd70-124">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7dd70-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7dd70-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7dd70-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7dd70-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7dd70-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7dd70-127">Недостаточно памяти, доступного для выполнения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="7dd70-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dd70-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="7dd70-128">Remarks</span></span>  
 <span data-ttu-id="7dd70-129">Среда CLR получает указатель интерфейса на `IHostMalloc` экземпляра путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7dd70-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dd70-130">Требования</span><span class="sxs-lookup"><span data-stu-id="7dd70-130">Requirements</span></span>  
 <span data-ttu-id="7dd70-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dd70-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dd70-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7dd70-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7dd70-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7dd70-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7dd70-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dd70-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd70-135">См. также</span><span class="sxs-lookup"><span data-stu-id="7dd70-135">See also</span></span>

- [<span data-ttu-id="7dd70-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="7dd70-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="7dd70-137">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="7dd70-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
