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
ms.openlocfilehash: 0d881c71d4725e1a73d743aa098aecc053182947
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918609"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="dcce5-102">Метод ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="dcce5-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="dcce5-103">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="dcce5-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcce5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcce5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcce5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dcce5-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="dcce5-106">окне Указанный размер сегмента сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="dcce5-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="dcce5-107">Минимальный размер сегмента — 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="dcce5-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="dcce5-108">Размер сегментов можно увеличить с шагом в 1 МБ или больше.</span><span class="sxs-lookup"><span data-stu-id="dcce5-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="dcce5-109">окне Указанный максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="dcce5-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="dcce5-110">Минимальный размер поколения 0 — 64 КБ.</span><span class="sxs-lookup"><span data-stu-id="dcce5-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcce5-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dcce5-111">Return Value</span></span>  
  
|<span data-ttu-id="dcce5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dcce5-112">HRESULT</span></span>|<span data-ttu-id="dcce5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="dcce5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dcce5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="dcce5-114">S_OK</span></span>|<span data-ttu-id="dcce5-115">`SetGCStartupLimitsEx`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="dcce5-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="dcce5-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dcce5-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dcce5-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dcce5-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dcce5-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dcce5-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dcce5-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="dcce5-119">The call timed out.</span></span>|  
|<span data-ttu-id="dcce5-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dcce5-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dcce5-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="dcce5-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dcce5-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dcce5-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dcce5-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="dcce5-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dcce5-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dcce5-124">E_FAIL</span></span>|<span data-ttu-id="dcce5-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="dcce5-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dcce5-126">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dcce5-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dcce5-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dcce5-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcce5-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="dcce5-128">Remarks</span></span>  
 <span data-ttu-id="dcce5-129">Значения, которые `SetGCStartupLimitsEx` задаются, можно указать только перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="dcce5-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="dcce5-130">Последующие вызовы метода `SetGCStartupLimitsEx` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="dcce5-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="dcce5-131">Чтобы задать любой параметр, не влияя на другой, укажите 0 (нуль) для параметра, который не нужно изменять.</span><span class="sxs-lookup"><span data-stu-id="dcce5-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcce5-132">Требования</span><span class="sxs-lookup"><span data-stu-id="dcce5-132">Requirements</span></span>  
 <span data-ttu-id="dcce5-133">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcce5-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcce5-134">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dcce5-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dcce5-135">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dcce5-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcce5-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcce5-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcce5-137">См. также</span><span class="sxs-lookup"><span data-stu-id="dcce5-137">See also</span></span>

- [<span data-ttu-id="dcce5-138">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="dcce5-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="dcce5-139">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="dcce5-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="dcce5-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="dcce5-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="dcce5-141">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="dcce5-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
