---
title: Метод IHostMemoryManager::CreateMAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 503a7c2056d0a828c65c5b0b81c50ea1e133aeef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="7756b-102">Метод IHostMemoryManager::CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="7756b-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="7756b-103">Возвращает указатель интерфейса [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) экземпляр, используемый для запроса выделения памяти из кучи, созданные узлом.</span><span class="sxs-lookup"><span data-stu-id="7756b-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7756b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7756b-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7756b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7756b-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="7756b-106">[in] Сочетание [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) флагов, определяющих характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="7756b-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="7756b-107">[out] Указатель на адрес `IHostMAlloc` экземпляра, предоставленный средой размещения.</span><span class="sxs-lookup"><span data-stu-id="7756b-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7756b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7756b-108">Return Value</span></span>  
  
|<span data-ttu-id="7756b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7756b-109">HRESULT</span></span>|<span data-ttu-id="7756b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7756b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7756b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7756b-111">S_OK</span></span>|<span data-ttu-id="7756b-112">`CreateMAlloc` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7756b-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="7756b-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7756b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7756b-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7756b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7756b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7756b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7756b-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7756b-116">The call timed out.</span></span>|  
|<span data-ttu-id="7756b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7756b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7756b-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7756b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7756b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7756b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7756b-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7756b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7756b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7756b-121">E_FAIL</span></span>|<span data-ttu-id="7756b-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7756b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7756b-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7756b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7756b-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7756b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7756b-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7756b-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7756b-126">Не хватает физической памяти была доступна для выполнения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="7756b-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7756b-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="7756b-127">Remarks</span></span>  
 <span data-ttu-id="7756b-128">`CreateMAlloc` Возвращает объект, который позволяет среде CLR для распределения запросов через узел вместо использования стандартных функций Win32.</span><span class="sxs-lookup"><span data-stu-id="7756b-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7756b-129">Требования</span><span class="sxs-lookup"><span data-stu-id="7756b-129">Requirements</span></span>  
 <span data-ttu-id="7756b-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7756b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7756b-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7756b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7756b-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7756b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7756b-133">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7756b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7756b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="7756b-134">See Also</span></span>  
 [<span data-ttu-id="7756b-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="7756b-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="7756b-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="7756b-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
