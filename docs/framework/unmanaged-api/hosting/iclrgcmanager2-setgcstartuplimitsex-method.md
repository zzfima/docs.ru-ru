---
title: Метод ICLRGCManager2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 708dd1e13fd999f9a3a11ce36248e82c15000bfc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479055"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="95b78-102">Метод ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="95b78-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="95b78-103">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="95b78-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95b78-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95b78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95b78-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="95b78-106">[in] Указанный размер сегмент сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="95b78-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="95b78-107">Минимальный размер сегмента составляет 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="95b78-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="95b78-108">Сегменты можно увеличить с шагом 1 МБ или больше.</span><span class="sxs-lookup"><span data-stu-id="95b78-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="95b78-109">[in] Заданный максимальный размер поколения 0.</span><span class="sxs-lookup"><span data-stu-id="95b78-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="95b78-110">Минимальное поколения 0 размер составляет 64 КБ.</span><span class="sxs-lookup"><span data-stu-id="95b78-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95b78-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="95b78-111">Return Value</span></span>  
  
|<span data-ttu-id="95b78-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95b78-112">HRESULT</span></span>|<span data-ttu-id="95b78-113">Описание</span><span class="sxs-lookup"><span data-stu-id="95b78-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95b78-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="95b78-114">S_OK</span></span>|<span data-ttu-id="95b78-115">`SetGCStartupLimitsEx` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="95b78-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="95b78-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95b78-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95b78-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="95b78-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95b78-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95b78-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95b78-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="95b78-119">The call timed out.</span></span>|  
|<span data-ttu-id="95b78-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95b78-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95b78-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="95b78-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95b78-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95b78-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95b78-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="95b78-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95b78-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95b78-124">E_FAIL</span></span>|<span data-ttu-id="95b78-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="95b78-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95b78-126">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="95b78-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95b78-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="95b78-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95b78-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="95b78-128">Remarks</span></span>  
 <span data-ttu-id="95b78-129">Значения, `SetGCStartupLimitsEx` множества могут быть заданы только в том случае, перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="95b78-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="95b78-130">Последующие вызовы `SetGCStartupLimitsEx` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="95b78-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="95b78-131">Чтобы задать один из параметров без влияния на другую, укажите 0 (ноль) для параметра, который вы не хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="95b78-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95b78-132">Требования</span><span class="sxs-lookup"><span data-stu-id="95b78-132">Requirements</span></span>  
 <span data-ttu-id="95b78-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95b78-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95b78-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95b78-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95b78-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95b78-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95b78-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95b78-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b78-137">См. также</span><span class="sxs-lookup"><span data-stu-id="95b78-137">See also</span></span>
- [<span data-ttu-id="95b78-138">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="95b78-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="95b78-139">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="95b78-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="95b78-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="95b78-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="95b78-141">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="95b78-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
