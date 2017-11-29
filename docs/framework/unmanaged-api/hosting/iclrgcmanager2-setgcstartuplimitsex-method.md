---
title: "Метод ICLRGCManager2::SetGCStartupLimitsEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73f5678008354b312964f0cb32d768d36a641fd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="1d141-102">Метод ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="1d141-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="1d141-103">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="1d141-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d141-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d141-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d141-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d141-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="1d141-106">[in] Указанный размер сегмент сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1d141-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="1d141-107">Минимальный размер сегмента составляет 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="1d141-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="1d141-108">Сегментов можно увеличить с шагом 1 МБ или больше.</span><span class="sxs-lookup"><span data-stu-id="1d141-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="1d141-109">[in] Заданный максимальный размер поколения 0.</span><span class="sxs-lookup"><span data-stu-id="1d141-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="1d141-110">Минимальная поколения 0 размер составляет 64 КБ.</span><span class="sxs-lookup"><span data-stu-id="1d141-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d141-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d141-111">Return Value</span></span>  
  
|<span data-ttu-id="1d141-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d141-112">HRESULT</span></span>|<span data-ttu-id="1d141-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1d141-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d141-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d141-114">S_OK</span></span>|<span data-ttu-id="1d141-115">`SetGCStartupLimitsEx`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1d141-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="1d141-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d141-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d141-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1d141-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d141-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d141-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d141-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="1d141-119">The call timed out.</span></span>|  
|<span data-ttu-id="1d141-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d141-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d141-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="1d141-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d141-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d141-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d141-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="1d141-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d141-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d141-124">E_FAIL</span></span>|<span data-ttu-id="1d141-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="1d141-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d141-126">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1d141-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d141-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d141-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d141-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d141-128">Remarks</span></span>  
 <span data-ttu-id="1d141-129">Значения, `SetGCStartupLimitsEx` наборы можно указать только в том случае, перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="1d141-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="1d141-130">Последующие вызовы `SetGCStartupLimitsEx` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="1d141-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="1d141-131">Чтобы задать один из параметров без влияния на другое, укажите 0 (ноль) для параметра, который вы не хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1d141-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d141-132">Требования</span><span class="sxs-lookup"><span data-stu-id="1d141-132">Requirements</span></span>  
 <span data-ttu-id="1d141-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d141-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d141-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d141-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d141-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d141-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d141-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d141-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d141-137">См. также</span><span class="sxs-lookup"><span data-stu-id="1d141-137">See Also</span></span>  
 [<span data-ttu-id="1d141-138">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="1d141-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="1d141-139">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="1d141-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="1d141-140">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1d141-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="1d141-141">ICLRGCManager2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1d141-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
