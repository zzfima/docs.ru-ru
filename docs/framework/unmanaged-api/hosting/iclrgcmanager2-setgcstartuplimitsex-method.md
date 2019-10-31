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
ms.openlocfilehash: 77de550cd3fb614e03f8028707c3cbf914734910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141089"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="90f1a-102">Метод ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="90f1a-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="90f1a-103">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="90f1a-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90f1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90f1a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90f1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="90f1a-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="90f1a-106">окне Указанный размер сегмента сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="90f1a-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="90f1a-107">Минимальный размер сегмента — 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="90f1a-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="90f1a-108">Размер сегментов можно увеличить с шагом в 1 МБ или больше.</span><span class="sxs-lookup"><span data-stu-id="90f1a-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="90f1a-109">окне Указанный максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="90f1a-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="90f1a-110">Минимальный размер поколения 0 — 64 КБ.</span><span class="sxs-lookup"><span data-stu-id="90f1a-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90f1a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="90f1a-111">Return Value</span></span>  
  
|<span data-ttu-id="90f1a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90f1a-112">HRESULT</span></span>|<span data-ttu-id="90f1a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="90f1a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90f1a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="90f1a-114">S_OK</span></span>|<span data-ttu-id="90f1a-115">`SetGCStartupLimitsEx` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="90f1a-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="90f1a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="90f1a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="90f1a-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="90f1a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="90f1a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="90f1a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="90f1a-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="90f1a-119">The call timed out.</span></span>|  
|<span data-ttu-id="90f1a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="90f1a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="90f1a-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="90f1a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="90f1a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="90f1a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="90f1a-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="90f1a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="90f1a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="90f1a-124">E_FAIL</span></span>|<span data-ttu-id="90f1a-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="90f1a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="90f1a-126">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="90f1a-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="90f1a-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="90f1a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90f1a-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="90f1a-128">Remarks</span></span>  
 <span data-ttu-id="90f1a-129">Значения, которые `SetGCStartupLimitsEx` наборы, можно указать только перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="90f1a-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="90f1a-130">Последующие вызовы `SetGCStartupLimitsEx` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="90f1a-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="90f1a-131">Чтобы задать любой параметр, не влияя на другой, укажите 0 (нуль) для параметра, который не нужно изменять.</span><span class="sxs-lookup"><span data-stu-id="90f1a-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90f1a-132">Требования</span><span class="sxs-lookup"><span data-stu-id="90f1a-132">Requirements</span></span>  
 <span data-ttu-id="90f1a-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90f1a-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90f1a-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="90f1a-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90f1a-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="90f1a-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90f1a-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90f1a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f1a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="90f1a-137">See also</span></span>

- [<span data-ttu-id="90f1a-138">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="90f1a-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="90f1a-139">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="90f1a-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="90f1a-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="90f1a-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="90f1a-141">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="90f1a-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
