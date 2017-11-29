---
title: "Метод IHostMAlloc::Free"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc.Free
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ac361f939a134aa6d2bc8b215c5d447b352466e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="60a62-102">Метод IHostMAlloc::Free</span><span class="sxs-lookup"><span data-stu-id="60a62-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="60a62-103">Освобождает память, выделенную с помощью [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) функции.</span><span class="sxs-lookup"><span data-stu-id="60a62-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a62-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60a62-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60a62-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="60a62-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="60a62-106">[in] Указатель на область памяти, освобождаемой.</span><span class="sxs-lookup"><span data-stu-id="60a62-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60a62-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="60a62-107">Return Value</span></span>  
  
|<span data-ttu-id="60a62-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60a62-108">HRESULT</span></span>|<span data-ttu-id="60a62-109">Описание</span><span class="sxs-lookup"><span data-stu-id="60a62-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60a62-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="60a62-110">S_OK</span></span>|<span data-ttu-id="60a62-111">`Free`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="60a62-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="60a62-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="60a62-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60a62-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="60a62-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60a62-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60a62-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60a62-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="60a62-115">The call timed out.</span></span>|  
|<span data-ttu-id="60a62-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60a62-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60a62-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="60a62-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60a62-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60a62-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60a62-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="60a62-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60a62-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60a62-120">E_FAIL</span></span>|<span data-ttu-id="60a62-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="60a62-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60a62-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="60a62-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60a62-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="60a62-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="60a62-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="60a62-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="60a62-125">Была предпринята попытка освободить память, выделенная не через узел.</span><span class="sxs-lookup"><span data-stu-id="60a62-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60a62-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="60a62-126">Remarks</span></span>  
 <span data-ttu-id="60a62-127">Если `pMem` параметр ссылается на область памяти, который не был выделен с помощью вызова `Alloc`, основное приложение должно возвратить значение HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="60a62-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60a62-128">Требования</span><span class="sxs-lookup"><span data-stu-id="60a62-128">Requirements</span></span>  
 <span data-ttu-id="60a62-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60a62-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60a62-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60a62-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60a62-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60a62-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60a62-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60a62-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a62-133">См. также</span><span class="sxs-lookup"><span data-stu-id="60a62-133">See Also</span></span>  
 [<span data-ttu-id="60a62-134">IHostMemoryManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="60a62-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="60a62-135">IHostMalloc-интерфейс</span><span class="sxs-lookup"><span data-stu-id="60a62-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
