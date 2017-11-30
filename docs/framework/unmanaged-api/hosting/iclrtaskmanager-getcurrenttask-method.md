---
title: "Метод ICLRTaskManager::GetCurrentTask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.GetCurrentTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1adf2959beb8687dc3d08ceb7a118bb19a5fa68d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="6f0ca-102">Метод ICLRTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="6f0ca-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="6f0ca-103">Возвращает [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляр, который выполняется в потоке операционной системы, из которого был осуществлен вызов метода.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f0ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f0ca-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f0ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f0ca-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="6f0ca-106">[out] Указатель на адрес `ICLRTask` экземпляр, который в данный момент в потоке операционной системы, от которого поступил вызов или значение null, если задача не выполняется в настоящее время в данном потоке.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f0ca-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6f0ca-107">Return Value</span></span>  
  
|<span data-ttu-id="6f0ca-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f0ca-108">HRESULT</span></span>|<span data-ttu-id="6f0ca-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6f0ca-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f0ca-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f0ca-110">S_OK</span></span>|<span data-ttu-id="6f0ca-111">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="6f0ca-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f0ca-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f0ca-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6f0ca-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6f0ca-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6f0ca-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-115">The call timed out.</span></span>|  
|<span data-ttu-id="6f0ca-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6f0ca-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6f0ca-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6f0ca-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6f0ca-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6f0ca-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6f0ca-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f0ca-120">E_FAIL</span></span>|<span data-ttu-id="6f0ca-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6f0ca-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6f0ca-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f0ca-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f0ca-124">Remarks</span></span>  
 <span data-ttu-id="6f0ca-125">`ICLRTask` Экземпляр `ppTask` указывает параметр представляет выполняемые задачи для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="6f0ca-126">`ICLRTask` С соответствующими связан экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр, представляющий задачи для узла.</span><span class="sxs-lookup"><span data-stu-id="6f0ca-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f0ca-127">Требования</span><span class="sxs-lookup"><span data-stu-id="6f0ca-127">Requirements</span></span>  
 <span data-ttu-id="6f0ca-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f0ca-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f0ca-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f0ca-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f0ca-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f0ca-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f0ca-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f0ca-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0ca-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6f0ca-132">See Also</span></span>  
 [<span data-ttu-id="6f0ca-133">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6f0ca-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="6f0ca-134">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6f0ca-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6f0ca-135">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6f0ca-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="6f0ca-136">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6f0ca-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
