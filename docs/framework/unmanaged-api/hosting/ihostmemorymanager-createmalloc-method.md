---
title: "Метод IHostMemoryManager::CreateMAlloc"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.CreateMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b4f8a23d03b3d839aeab5d2f571cb4f98f1ec5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="3e291-102">Метод IHostMemoryManager::CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="3e291-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="3e291-103">Возвращает указатель интерфейса [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) экземпляр, используемый для запроса выделения памяти из кучи, созданные узлом.</span><span class="sxs-lookup"><span data-stu-id="3e291-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e291-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e291-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e291-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e291-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="3e291-106">[in] Сочетание [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) флагов, определяющих характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="3e291-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="3e291-107">[out] Указатель на адрес `IHostMAlloc` экземпляра, предоставленный средой размещения.</span><span class="sxs-lookup"><span data-stu-id="3e291-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e291-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e291-108">Return Value</span></span>  
  
|<span data-ttu-id="3e291-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e291-109">HRESULT</span></span>|<span data-ttu-id="3e291-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3e291-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e291-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e291-111">S_OK</span></span>|<span data-ttu-id="3e291-112">`CreateMAlloc`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3e291-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="3e291-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e291-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e291-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3e291-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e291-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e291-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e291-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3e291-116">The call timed out.</span></span>|  
|<span data-ttu-id="3e291-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e291-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e291-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3e291-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e291-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e291-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e291-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3e291-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e291-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e291-121">E_FAIL</span></span>|<span data-ttu-id="3e291-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="3e291-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e291-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3e291-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e291-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e291-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3e291-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3e291-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3e291-126">Не хватает физической памяти была доступна для выполнения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="3e291-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e291-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e291-127">Remarks</span></span>  
 <span data-ttu-id="3e291-128">`CreateMAlloc`Возвращает объект, который позволяет среде CLR для распределения запросов через узел вместо использования стандартных функций Win32.</span><span class="sxs-lookup"><span data-stu-id="3e291-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e291-129">Требования</span><span class="sxs-lookup"><span data-stu-id="3e291-129">Requirements</span></span>  
 <span data-ttu-id="3e291-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e291-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e291-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e291-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e291-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e291-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e291-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e291-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e291-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3e291-134">See Also</span></span>  
 [<span data-ttu-id="3e291-135">IHostMalloc-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3e291-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="3e291-136">IHostMemoryManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3e291-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
