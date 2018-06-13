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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96673049d37034781dff9f206db86a1d5d953d52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436404"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="f59f4-102">Метод ICLRGCManager::GetStats</span><span class="sxs-lookup"><span data-stu-id="f59f4-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="f59f4-103">Получает набор текущих статистических данных о системе сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f59f4-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f59f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f59f4-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f59f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f59f4-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="f59f4-106">[in, out] Объект [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) экземпляр, содержащий запрошенную статистики.</span><span class="sxs-lookup"><span data-stu-id="f59f4-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f59f4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f59f4-107">Return Value</span></span>  
  
|<span data-ttu-id="f59f4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f59f4-108">HRESULT</span></span>|<span data-ttu-id="f59f4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f59f4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f59f4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f59f4-110">S_OK</span></span>|<span data-ttu-id="f59f4-111">`GetStats` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f59f4-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="f59f4-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f59f4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f59f4-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f59f4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f59f4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f59f4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f59f4-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f59f4-115">The call timed out.</span></span>|  
|<span data-ttu-id="f59f4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f59f4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f59f4-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f59f4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f59f4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f59f4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f59f4-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f59f4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f59f4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f59f4-120">E_FAIL</span></span>|<span data-ttu-id="f59f4-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="f59f4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f59f4-122">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f59f4-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f59f4-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f59f4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f59f4-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="f59f4-124">Remarks</span></span>  
 <span data-ttu-id="f59f4-125">Среда CLR вычисляет и возвращает только те статистические данные, которые определяются `Flags` поле `pStats`.</span><span class="sxs-lookup"><span data-stu-id="f59f4-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="f59f4-126">Задать `Flags` на один или несколько значений [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) перечисления, чтобы указать, какая именно статистика в [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуры должны быть заданы.</span><span class="sxs-lookup"><span data-stu-id="f59f4-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="f59f4-127">Ниже приведен пример использования:</span><span class="sxs-lookup"><span data-stu-id="f59f4-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f59f4-128">Требования</span><span class="sxs-lookup"><span data-stu-id="f59f4-128">Requirements</span></span>  
 <span data-ttu-id="f59f4-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f59f4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f59f4-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f59f4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f59f4-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f59f4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f59f4-132">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f59f4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f59f4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f59f4-133">See Also</span></span>  
 [<span data-ttu-id="f59f4-134">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="f59f4-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="f59f4-135">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="f59f4-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="f59f4-136">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="f59f4-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 [<span data-ttu-id="f59f4-137">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="f59f4-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="f59f4-138">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f59f4-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f59f4-139">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="f59f4-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="f59f4-140">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="f59f4-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="f59f4-141">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f59f4-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="f59f4-142">Размещение</span><span class="sxs-lookup"><span data-stu-id="f59f4-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
