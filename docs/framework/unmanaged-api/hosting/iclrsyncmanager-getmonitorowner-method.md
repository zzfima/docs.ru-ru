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
ms.openlocfilehash: 90fbba9a5aead27d79c5355d69bc12481e826b65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="4324b-102">Метод ICLRSyncManager::GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="4324b-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="4324b-103">Возвращает [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр, которому принадлежит монитором, заданным указанным файлом cookie.</span><span class="sxs-lookup"><span data-stu-id="4324b-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4324b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4324b-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4324b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4324b-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="4324b-106">[in] Файл cookie, связанные с монитором.</span><span class="sxs-lookup"><span data-stu-id="4324b-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="4324b-107">[out] Указатель на `IHostTask` , в данный момент принадлежит монитор, или значение null, если задача не имеет владельца.</span><span class="sxs-lookup"><span data-stu-id="4324b-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4324b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4324b-108">Return Value</span></span>  
  
|<span data-ttu-id="4324b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4324b-109">HRESULT</span></span>|<span data-ttu-id="4324b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4324b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4324b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4324b-111">S_OK</span></span>|<span data-ttu-id="4324b-112">`GetMonitorOwner`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4324b-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="4324b-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4324b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4324b-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4324b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4324b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4324b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4324b-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4324b-116">The call timed out.</span></span>|  
|<span data-ttu-id="4324b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4324b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4324b-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4324b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4324b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4324b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4324b-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4324b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4324b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4324b-121">E_FAIL</span></span>|<span data-ttu-id="4324b-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4324b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4324b-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4324b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4324b-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4324b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4324b-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="4324b-125">Remarks</span></span>  
 <span data-ttu-id="4324b-126">Основное приложение обычно вызывает `GetMonitorOwner` в рамках механизма обнаружения взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="4324b-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="4324b-127">Куки-файл связан с монитором, при его создании с помощью вызова [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="4324b-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4324b-128">Вызов, чтобы освободить событие, базовый монитор может блокироваться, но не взаимоблокировке — при вызове этого метода действует в данный момент в файле cookie, связанного с монитором.</span><span class="sxs-lookup"><span data-stu-id="4324b-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="4324b-129">Другие задачи могут также блокировать, если они пытаются получить этот монитор.</span><span class="sxs-lookup"><span data-stu-id="4324b-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="4324b-130">`GetMonitorOwner`всегда возвращается немедленно и можно вызвать в любое время после вызова `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="4324b-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="4324b-131">Узел не нужно подождать, пока задача ожидает события.</span><span class="sxs-lookup"><span data-stu-id="4324b-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4324b-132">Требования</span><span class="sxs-lookup"><span data-stu-id="4324b-132">Requirements</span></span>  
 <span data-ttu-id="4324b-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4324b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4324b-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4324b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4324b-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4324b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4324b-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4324b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4324b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="4324b-137">See Also</span></span>  
 [<span data-ttu-id="4324b-138">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4324b-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="4324b-139">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4324b-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
