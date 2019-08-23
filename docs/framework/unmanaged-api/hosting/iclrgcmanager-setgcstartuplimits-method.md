---
title: Метод ICLRGCManager::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29311f00f5ac4b61380b57cdd9fda07ec7de1b23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966202"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="df492-102">Метод ICLRGCManager::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="df492-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="df492-103">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="df492-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="df492-104">Начиная с .NET Framework 4,5 можно задать размер сегмента и максимальный размер поколения 0 в значениях `DWORD` , превышающих использование метода [ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="df492-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df492-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df492-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df492-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="df492-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="df492-107">окне Указанный размер сегмента сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="df492-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="df492-108">Минимальный размер сегмента — 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="df492-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="df492-109">Размер сегментов можно увеличить с шагом в 1 МБ или больше.</span><span class="sxs-lookup"><span data-stu-id="df492-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="df492-110">окне Указанный максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="df492-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="df492-111">Минимальный размер поколения 0 — 64 КБ.</span><span class="sxs-lookup"><span data-stu-id="df492-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df492-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df492-112">Return Value</span></span>  
  
|<span data-ttu-id="df492-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df492-113">HRESULT</span></span>|<span data-ttu-id="df492-114">Описание</span><span class="sxs-lookup"><span data-stu-id="df492-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df492-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="df492-115">S_OK</span></span>|<span data-ttu-id="df492-116">`SetGCStartupLimits`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="df492-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="df492-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df492-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df492-118">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="df492-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df492-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df492-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df492-120">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="df492-120">The call timed out.</span></span>|  
|<span data-ttu-id="df492-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df492-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df492-122">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="df492-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df492-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df492-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df492-124">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="df492-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df492-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df492-125">E_FAIL</span></span>|<span data-ttu-id="df492-126">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="df492-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df492-127">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="df492-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df492-128">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df492-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df492-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="df492-129">Remarks</span></span>  
 <span data-ttu-id="df492-130">Значения, которые `SetGCStartupLimits` задаются, можно указать только один раз.</span><span class="sxs-lookup"><span data-stu-id="df492-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="df492-131">Последующие вызовы метода `SetGCStartupLimits` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="df492-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df492-132">Требования</span><span class="sxs-lookup"><span data-stu-id="df492-132">Requirements</span></span>  
 <span data-ttu-id="df492-133">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df492-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df492-134">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df492-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df492-135">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="df492-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df492-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df492-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df492-137">См. также</span><span class="sxs-lookup"><span data-stu-id="df492-137">See also</span></span>

- [<span data-ttu-id="df492-138">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="df492-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="df492-139">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="df492-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="df492-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="df492-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="df492-141">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="df492-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
