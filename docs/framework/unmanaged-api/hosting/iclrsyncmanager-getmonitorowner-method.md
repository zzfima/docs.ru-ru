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
ms.openlocfilehash: 3aec11674275769bb5c4b68521a40a72a1d68a22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124682"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="c87f3-102">Метод ICLRSyncManager::GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="c87f3-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="c87f3-103">Возвращает экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , которому принадлежит монитор, идентифицируемый указанным файлом cookie.</span><span class="sxs-lookup"><span data-stu-id="c87f3-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c87f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c87f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c87f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c87f3-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="c87f3-106">окне Файл cookie, связанный с монитором.</span><span class="sxs-lookup"><span data-stu-id="c87f3-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="c87f3-107">заполняет Указатель на `IHostTask`, которому в данный момент принадлежит монитор, или значение null, если ни одна задача не владеет.</span><span class="sxs-lookup"><span data-stu-id="c87f3-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c87f3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c87f3-108">Return Value</span></span>  
  
|<span data-ttu-id="c87f3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c87f3-109">HRESULT</span></span>|<span data-ttu-id="c87f3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c87f3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c87f3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c87f3-111">S_OK</span></span>|<span data-ttu-id="c87f3-112">`GetMonitorOwner` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="c87f3-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="c87f3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c87f3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c87f3-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c87f3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c87f3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c87f3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c87f3-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="c87f3-116">The call timed out.</span></span>|  
|<span data-ttu-id="c87f3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c87f3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c87f3-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="c87f3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c87f3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c87f3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c87f3-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="c87f3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c87f3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c87f3-121">E_FAIL</span></span>|<span data-ttu-id="c87f3-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c87f3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c87f3-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c87f3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c87f3-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c87f3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c87f3-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="c87f3-125">Remarks</span></span>  
 <span data-ttu-id="c87f3-126">Узел обычно вызывает `GetMonitorOwner` как часть механизма обнаружения взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="c87f3-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="c87f3-127">Файл cookie связывается с монитором при его создании с помощью вызова [метод ihostsyncmanager:: CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="c87f3-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c87f3-128">Вызов для освобождения события, лежащего в основе монитора, может блокироваться, но не будет взаимоблокировками, если вызов этого метода в настоящее время действует на файл cookie, связанный с этим монитором.</span><span class="sxs-lookup"><span data-stu-id="c87f3-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="c87f3-129">Другие задачи также могут блокироваться при попытке получить этот монитор.</span><span class="sxs-lookup"><span data-stu-id="c87f3-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="c87f3-130">`GetMonitorOwner` всегда немедленно возвращает значение и может вызываться в любое время после вызова `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="c87f3-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="c87f3-131">Узлу не нужно ждать, пока задача ожидает события.</span><span class="sxs-lookup"><span data-stu-id="c87f3-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c87f3-132">Требования</span><span class="sxs-lookup"><span data-stu-id="c87f3-132">Requirements</span></span>  
 <span data-ttu-id="c87f3-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c87f3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c87f3-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c87f3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c87f3-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c87f3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c87f3-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c87f3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87f3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c87f3-137">See also</span></span>

- [<span data-ttu-id="c87f3-138">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="c87f3-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c87f3-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c87f3-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
