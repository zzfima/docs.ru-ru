---
title: "Метод ICLRGCManager::Collect"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96f99855654a3a86873ca4623d8617f74030938b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="b7774-102">Метод ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="b7774-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="b7774-103">Принудительная сборка мусора для заданного поколения.</span><span class="sxs-lookup"><span data-stu-id="b7774-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7774-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7774-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7774-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7774-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="b7774-106">[in] Поколение, для сбора.</span><span class="sxs-lookup"><span data-stu-id="b7774-106">[in] The generation to collect.</span></span> <span data-ttu-id="b7774-107">Значение -1 принудительно мусора для всех поколений.</span><span class="sxs-lookup"><span data-stu-id="b7774-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7774-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b7774-108">Return Value</span></span>  
  
|<span data-ttu-id="b7774-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7774-109">HRESULT</span></span>|<span data-ttu-id="b7774-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b7774-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7774-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7774-111">S_OK</span></span>|<span data-ttu-id="b7774-112">`Collect`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b7774-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="b7774-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7774-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7774-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b7774-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7774-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7774-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7774-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b7774-116">The call timed out.</span></span>|  
|<span data-ttu-id="b7774-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7774-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7774-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b7774-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7774-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7774-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7774-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b7774-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7774-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7774-121">E_FAIL</span></span>|<span data-ttu-id="b7774-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="b7774-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7774-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b7774-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7774-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b7774-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7774-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7774-125">Remarks</span></span>  
 <span data-ttu-id="b7774-126">`Collect` Метод вынуждает сборщик мусора среды CLR для выполнения сбора, независимо от его текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="b7774-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7774-127">Требования</span><span class="sxs-lookup"><span data-stu-id="b7774-127">Requirements</span></span>  
 <span data-ttu-id="b7774-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7774-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7774-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7774-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7774-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7774-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7774-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7774-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7774-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b7774-132">See Also</span></span>  
 [<span data-ttu-id="b7774-133">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="b7774-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="b7774-134">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="b7774-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="b7774-135">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b7774-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="b7774-136">Iclrgcmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b7774-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="b7774-137">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b7774-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="b7774-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b7774-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="b7774-139">Размещение</span><span class="sxs-lookup"><span data-stu-id="b7774-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
