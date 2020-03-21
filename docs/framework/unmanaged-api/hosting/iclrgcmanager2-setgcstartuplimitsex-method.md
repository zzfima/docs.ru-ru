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
ms.openlocfilehash: 9885149a71147db6eef13958b8ef825caa1d6ec6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176387"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="b8e04-102">Метод ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="b8e04-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="b8e04-103">Устанавливает размер сегмента сбора мусора и максимальный размер поколения 0 системы сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="b8e04-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8e04-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e04-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8e04-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="b8e04-106">(в) Указанный размер сегмента сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="b8e04-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="b8e04-107">Минимальный размер сегмента составляет 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="b8e04-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="b8e04-108">Сегменты могут быть увеличены с шагом 1 МБ или больше.</span><span class="sxs-lookup"><span data-stu-id="b8e04-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="b8e04-109">(в) Указанный максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="b8e04-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="b8e04-110">Минимальный размер поколения 0 составляет 64 кБ.</span><span class="sxs-lookup"><span data-stu-id="b8e04-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8e04-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b8e04-111">Return Value</span></span>  
  
|<span data-ttu-id="b8e04-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8e04-112">HRESULT</span></span>|<span data-ttu-id="b8e04-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b8e04-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8e04-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8e04-114">S_OK</span></span>|<span data-ttu-id="b8e04-115">`SetGCStartupLimitsEx`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="b8e04-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="b8e04-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8e04-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8e04-117">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b8e04-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b8e04-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b8e04-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b8e04-119">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="b8e04-119">The call timed out.</span></span>|  
|<span data-ttu-id="b8e04-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8e04-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b8e04-121">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="b8e04-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b8e04-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b8e04-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b8e04-123">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="b8e04-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b8e04-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8e04-124">E_FAIL</span></span>|<span data-ttu-id="b8e04-125">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="b8e04-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b8e04-126">После того, как метод возвращается E_FAIL, CLR больше не может быть пригодным к удочку в процессе.</span><span class="sxs-lookup"><span data-stu-id="b8e04-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b8e04-127">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b8e04-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8e04-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8e04-128">Remarks</span></span>  
 <span data-ttu-id="b8e04-129">Значения, `SetGCStartupLimitsEx` которые наборы могут быть указаны только до запуска узла.</span><span class="sxs-lookup"><span data-stu-id="b8e04-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="b8e04-130">Более поздние звонки `SetGCStartupLimitsEx` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="b8e04-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="b8e04-131">Чтобы установить любой параметр, не затрагивая другой, укажите 0 (ноль) для параметра, который вы не хотите менять.</span><span class="sxs-lookup"><span data-stu-id="b8e04-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e04-132">Требования</span><span class="sxs-lookup"><span data-stu-id="b8e04-132">Requirements</span></span>  
 <span data-ttu-id="b8e04-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e04-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e04-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8e04-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8e04-135">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8e04-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8e04-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e04-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e04-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b8e04-137">See also</span></span>

- [<span data-ttu-id="b8e04-138">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="b8e04-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b8e04-139">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="b8e04-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="b8e04-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b8e04-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b8e04-141">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="b8e04-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
