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
ms.openlocfilehash: 9300f67e75d40f041a4fba52f6742741ec9f91de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187351"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="57150-102">Метод ICLRGCManager::GetStats</span><span class="sxs-lookup"><span data-stu-id="57150-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="57150-103">Получает набор текущую статистику о сборщик мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="57150-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57150-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57150-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57150-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57150-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="57150-106">[in, out] Объект [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) экземпляр, который содержит запрошенный статистические данные.</span><span class="sxs-lookup"><span data-stu-id="57150-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57150-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57150-107">Return Value</span></span>  
  
|<span data-ttu-id="57150-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57150-108">HRESULT</span></span>|<span data-ttu-id="57150-109">Описание</span><span class="sxs-lookup"><span data-stu-id="57150-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57150-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="57150-110">S_OK</span></span>|<span data-ttu-id="57150-111">`GetStats` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="57150-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="57150-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57150-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57150-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="57150-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57150-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57150-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57150-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="57150-115">The call timed out.</span></span>|  
|<span data-ttu-id="57150-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57150-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57150-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="57150-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57150-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57150-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57150-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="57150-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57150-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57150-120">E_FAIL</span></span>|<span data-ttu-id="57150-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="57150-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57150-122">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="57150-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57150-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="57150-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57150-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="57150-124">Remarks</span></span>  
 <span data-ttu-id="57150-125">Среда CLR вычисляет и возвращает только те статистические данные, которые указываются с `Flags` поле `pStats`.</span><span class="sxs-lookup"><span data-stu-id="57150-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="57150-126">Задайте `Flags` на один или несколько значений [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) перечисление, чтобы указать, какая именно статистика в [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) задаются структуры.</span><span class="sxs-lookup"><span data-stu-id="57150-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="57150-127">Ниже приведен пример использования:</span><span class="sxs-lookup"><span data-stu-id="57150-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="57150-128">Требования</span><span class="sxs-lookup"><span data-stu-id="57150-128">Requirements</span></span>  
 <span data-ttu-id="57150-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57150-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57150-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="57150-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57150-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57150-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57150-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57150-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57150-133">См. также</span><span class="sxs-lookup"><span data-stu-id="57150-133">See also</span></span>

- [<span data-ttu-id="57150-134">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="57150-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="57150-135">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="57150-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="57150-136">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="57150-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="57150-137">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="57150-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="57150-138">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="57150-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="57150-139">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="57150-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="57150-140">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="57150-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="57150-141">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="57150-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="57150-142">Размещение</span><span class="sxs-lookup"><span data-stu-id="57150-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
