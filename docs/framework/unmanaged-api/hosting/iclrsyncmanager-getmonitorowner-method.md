---
title: Метод ICLRSyncManager::GetMonitorOwner
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3847c5e5704f4eef138bf8b3f7966e4ff66d8784
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716323"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="df91b-102">Метод ICLRSyncManager::GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="df91b-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="df91b-103">Получает [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра, которому принадлежит монитор, идентифицируются указанный файл cookie.</span><span class="sxs-lookup"><span data-stu-id="df91b-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df91b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df91b-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df91b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df91b-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="df91b-106">[in] Файл cookie, связанный с монитором.</span><span class="sxs-lookup"><span data-stu-id="df91b-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="df91b-107">[out] Указатель на `IHostTask` , в данный момент владеет монитор, или значение null, если ни одна задача имеет владельца.</span><span class="sxs-lookup"><span data-stu-id="df91b-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df91b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df91b-108">Return Value</span></span>  
  
|<span data-ttu-id="df91b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df91b-109">HRESULT</span></span>|<span data-ttu-id="df91b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="df91b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df91b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="df91b-111">S_OK</span></span>|<span data-ttu-id="df91b-112">`GetMonitorOwner` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="df91b-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="df91b-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df91b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df91b-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="df91b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df91b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df91b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df91b-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="df91b-116">The call timed out.</span></span>|  
|<span data-ttu-id="df91b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df91b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df91b-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="df91b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df91b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df91b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df91b-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="df91b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df91b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df91b-121">E_FAIL</span></span>|<span data-ttu-id="df91b-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="df91b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df91b-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="df91b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df91b-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df91b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df91b-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="df91b-125">Remarks</span></span>  
 <span data-ttu-id="df91b-126">Узел обычно вызывает метод `GetMonitorOwner` как часть механизм обнаружения взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="df91b-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="df91b-127">Файл cookie связан с монитором, при его создании с помощью вызова [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="df91b-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df91b-128">Вызов, чтобы освободить событие основной монитор может блокировать — но не взаимоблокировке — Если вызов этого метода действует в данный момент на файл cookie, связанный с монитором.</span><span class="sxs-lookup"><span data-stu-id="df91b-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="df91b-129">Другие задачи может также блокировать, если они пытаются получить этот монитор.</span><span class="sxs-lookup"><span data-stu-id="df91b-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="df91b-130">`GetMonitorOwner` всегда возвращается немедленно и можно вызвать в любое время после вызова `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="df91b-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="df91b-131">Узел не требуется подождать, пока задача ожидает события.</span><span class="sxs-lookup"><span data-stu-id="df91b-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df91b-132">Требования</span><span class="sxs-lookup"><span data-stu-id="df91b-132">Requirements</span></span>  
 <span data-ttu-id="df91b-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df91b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df91b-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df91b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df91b-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df91b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df91b-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df91b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df91b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="df91b-137">See also</span></span>
- [<span data-ttu-id="df91b-138">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="df91b-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="df91b-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="df91b-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
