---
title: "Метод ICLRSyncManager::GetMonitorOwner"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.GetMonitorOwner
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b998a26056aec739587b77c1b1b39f0e9392a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="86189-102">Метод ICLRSyncManager::GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="86189-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="86189-103">Возвращает [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр, которому принадлежит монитором, заданным указанным файлом cookie.</span><span class="sxs-lookup"><span data-stu-id="86189-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86189-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86189-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86189-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86189-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="86189-106">[in] Файл cookie, связанные с монитором.</span><span class="sxs-lookup"><span data-stu-id="86189-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="86189-107">[out] Указатель на `IHostTask` , в данный момент принадлежит монитор, или значение null, если задача не имеет владельца.</span><span class="sxs-lookup"><span data-stu-id="86189-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86189-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86189-108">Return Value</span></span>  
  
|<span data-ttu-id="86189-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86189-109">HRESULT</span></span>|<span data-ttu-id="86189-110">Описание</span><span class="sxs-lookup"><span data-stu-id="86189-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86189-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86189-111">S_OK</span></span>|<span data-ttu-id="86189-112">`GetMonitorOwner`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="86189-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="86189-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86189-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86189-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="86189-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86189-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86189-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86189-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="86189-116">The call timed out.</span></span>|  
|<span data-ttu-id="86189-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86189-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86189-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="86189-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86189-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86189-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86189-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="86189-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86189-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86189-121">E_FAIL</span></span>|<span data-ttu-id="86189-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="86189-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86189-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="86189-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86189-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="86189-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86189-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="86189-125">Remarks</span></span>  
 <span data-ttu-id="86189-126">Основное приложение обычно вызывает `GetMonitorOwner` в рамках механизма обнаружения взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="86189-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="86189-127">Куки-файл связан с монитором, при его создании с помощью вызова [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="86189-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86189-128">Вызов, чтобы освободить событие, базовый монитор может блокироваться, но не взаимоблокировке — при вызове этого метода действует в данный момент в файле cookie, связанного с монитором.</span><span class="sxs-lookup"><span data-stu-id="86189-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="86189-129">Другие задачи могут также блокировать, если они пытаются получить этот монитор.</span><span class="sxs-lookup"><span data-stu-id="86189-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="86189-130">`GetMonitorOwner`всегда возвращается немедленно и можно вызвать в любое время после вызова `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="86189-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="86189-131">Узел не нужно подождать, пока задача ожидает события.</span><span class="sxs-lookup"><span data-stu-id="86189-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86189-132">Требования</span><span class="sxs-lookup"><span data-stu-id="86189-132">Requirements</span></span>  
 <span data-ttu-id="86189-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86189-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86189-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="86189-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86189-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86189-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86189-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86189-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86189-137">См. также</span><span class="sxs-lookup"><span data-stu-id="86189-137">See Also</span></span>  
 [<span data-ttu-id="86189-138">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="86189-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="86189-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="86189-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
