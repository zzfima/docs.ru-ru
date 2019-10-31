---
title: Метод ICLRGCManager::GetStats
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
ms.openlocfilehash: 9e8b65c735028029f4fb44c2640df74ef171d9de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141140"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="5dc22-102">Метод ICLRGCManager::GetStats</span><span class="sxs-lookup"><span data-stu-id="5dc22-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="5dc22-103">Возвращает набор текущих статистических данных о системе сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5dc22-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5dc22-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dc22-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5dc22-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="5dc22-106">[вход, выход] Экземпляр [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) , содержащий запрошенную статистику.</span><span class="sxs-lookup"><span data-stu-id="5dc22-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dc22-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5dc22-107">Return Value</span></span>  
  
|<span data-ttu-id="5dc22-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5dc22-108">HRESULT</span></span>|<span data-ttu-id="5dc22-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5dc22-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5dc22-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5dc22-110">S_OK</span></span>|<span data-ttu-id="5dc22-111">`GetStats` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="5dc22-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="5dc22-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5dc22-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5dc22-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5dc22-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5dc22-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5dc22-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5dc22-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="5dc22-115">The call timed out.</span></span>|  
|<span data-ttu-id="5dc22-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5dc22-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5dc22-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="5dc22-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5dc22-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5dc22-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5dc22-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="5dc22-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5dc22-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5dc22-120">E_FAIL</span></span>|<span data-ttu-id="5dc22-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="5dc22-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5dc22-122">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5dc22-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5dc22-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5dc22-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dc22-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="5dc22-124">Remarks</span></span>  
 <span data-ttu-id="5dc22-125">Среда CLR вычисляет и возвращает только те статистические данные, которые указаны в `Flags` поле `pStats`.</span><span class="sxs-lookup"><span data-stu-id="5dc22-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="5dc22-126">Задайте для поля `Flags` одно или несколько значений перечисления [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md), чтобы указать, какую статистику в структуре [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) нужно задать.</span><span class="sxs-lookup"><span data-stu-id="5dc22-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="5dc22-127">Пример использования таков:</span><span class="sxs-lookup"><span data-stu-id="5dc22-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5dc22-128">Требования</span><span class="sxs-lookup"><span data-stu-id="5dc22-128">Requirements</span></span>  
 <span data-ttu-id="5dc22-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc22-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc22-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5dc22-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5dc22-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5dc22-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dc22-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc22-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc22-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5dc22-133">See also</span></span>

- [<span data-ttu-id="5dc22-134">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="5dc22-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5dc22-135">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="5dc22-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="5dc22-136">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="5dc22-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="5dc22-137">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="5dc22-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="5dc22-138">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5dc22-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5dc22-139">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="5dc22-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="5dc22-140">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="5dc22-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="5dc22-141">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5dc22-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5dc22-142">Размещение</span><span class="sxs-lookup"><span data-stu-id="5dc22-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
