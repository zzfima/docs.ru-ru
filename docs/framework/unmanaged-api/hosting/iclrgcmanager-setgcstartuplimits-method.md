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
ms.openlocfilehash: 645b64c8b536029663c350bdcde9a716a715aab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178085"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="d54a4-102">Метод ICLRGCManager::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="d54a4-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="d54a4-103">Устанавливает размер сегмента сбора мусора и максимальный размер поколения 0 системы сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="d54a4-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d54a4-104">Начиная с .NET Framework 4.5, вы можете установить размер сегмента `DWORD` и максимальный размер поколения 0 на значения, превышающее значения с помощью метода [ICLRGCManager2::SetGCStartupLimitsEx.](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)</span><span class="sxs-lookup"><span data-stu-id="d54a4-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d54a4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d54a4-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d54a4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d54a4-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="d54a4-107">(в) Указанный размер сегмента сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="d54a4-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="d54a4-108">Минимальный размер сегмента составляет 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="d54a4-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="d54a4-109">Сегменты могут быть увеличены с шагом 1 МБ или больше.</span><span class="sxs-lookup"><span data-stu-id="d54a4-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="d54a4-110">(в) Указанный максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="d54a4-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="d54a4-111">Минимальный размер поколения 0 составляет 64 кБ.</span><span class="sxs-lookup"><span data-stu-id="d54a4-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d54a4-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d54a4-112">Return Value</span></span>  
  
|<span data-ttu-id="d54a4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d54a4-113">HRESULT</span></span>|<span data-ttu-id="d54a4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d54a4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d54a4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d54a4-115">S_OK</span></span>|<span data-ttu-id="d54a4-116">`SetGCStartupLimits`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="d54a4-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="d54a4-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d54a4-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d54a4-118">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d54a4-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d54a4-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d54a4-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d54a4-120">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="d54a4-120">The call timed out.</span></span>|  
|<span data-ttu-id="d54a4-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d54a4-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d54a4-122">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="d54a4-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d54a4-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d54a4-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d54a4-124">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="d54a4-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d54a4-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d54a4-125">E_FAIL</span></span>|<span data-ttu-id="d54a4-126">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="d54a4-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d54a4-127">После того, как метод возвращается E_FAIL, CLR больше не может быть пригодным к удочку в процессе.</span><span class="sxs-lookup"><span data-stu-id="d54a4-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d54a4-128">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d54a4-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d54a4-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="d54a4-129">Remarks</span></span>  
 <span data-ttu-id="d54a4-130">Значения, которые `SetGCStartupLimits` наборы могут быть указаны только один раз.</span><span class="sxs-lookup"><span data-stu-id="d54a4-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="d54a4-131">Более поздние звонки `SetGCStartupLimits` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="d54a4-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d54a4-132">Требования</span><span class="sxs-lookup"><span data-stu-id="d54a4-132">Requirements</span></span>  
 <span data-ttu-id="d54a4-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d54a4-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d54a4-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d54a4-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d54a4-135">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d54a4-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d54a4-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d54a4-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54a4-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d54a4-137">See also</span></span>

- [<span data-ttu-id="d54a4-138">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="d54a4-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="d54a4-139">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="d54a4-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="d54a4-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="d54a4-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d54a4-141">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="d54a4-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
