---
title: Метод ICLRGCManager::Collect
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2da0b3b7a8a7ae46050345aaf5fcfa65fa349ae5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477989"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="e7c1f-102">Метод ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="e7c1f-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="e7c1f-103">Принудительная сборка мусора для заданного поколения.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7c1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7c1f-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7c1f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7c1f-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="e7c1f-106">[in] Поколение, для сбора.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-106">[in] The generation to collect.</span></span> <span data-ttu-id="e7c1f-107">Значение -1 заставляет коллекции для всех поколений.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7c1f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7c1f-108">Return Value</span></span>  
  
|<span data-ttu-id="e7c1f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7c1f-109">HRESULT</span></span>|<span data-ttu-id="e7c1f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e7c1f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7c1f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7c1f-111">S_OK</span></span>|<span data-ttu-id="e7c1f-112">`Collect` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="e7c1f-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7c1f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7c1f-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e7c1f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7c1f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7c1f-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-116">The call timed out.</span></span>|  
|<span data-ttu-id="e7c1f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7c1f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7c1f-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7c1f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7c1f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7c1f-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7c1f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7c1f-121">E_FAIL</span></span>|<span data-ttu-id="e7c1f-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7c1f-123">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7c1f-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7c1f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7c1f-125">Remarks</span></span>  
 <span data-ttu-id="e7c1f-126">`Collect` Метод вынуждает сборщик мусора среды CLR для выполнения сбора, независимо от текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="e7c1f-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7c1f-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e7c1f-127">Requirements</span></span>  
 <span data-ttu-id="e7c1f-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7c1f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7c1f-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7c1f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7c1f-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7c1f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7c1f-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7c1f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c1f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e7c1f-132">See also</span></span>
- [<span data-ttu-id="e7c1f-133">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="e7c1f-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="e7c1f-134">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="e7c1f-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="e7c1f-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e7c1f-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e7c1f-136">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="e7c1f-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="e7c1f-137">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e7c1f-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="e7c1f-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e7c1f-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e7c1f-139">Размещение</span><span class="sxs-lookup"><span data-stu-id="e7c1f-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
