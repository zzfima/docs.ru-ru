---
title: Метод ICLRTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7db333cd97963ca8ef26673c0ba5cbf352fa331b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165312"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="b5b01-102">Метод ICLRTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="b5b01-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="b5b01-103">Получает [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляр, который выполняется в данный момент в потоке операционной системы, от которого поступил вызов метода.</span><span class="sxs-lookup"><span data-stu-id="b5b01-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5b01-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5b01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5b01-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="b5b01-106">[out] Указатель на адрес `ICLRTask` экземпляр, который в данный момент в потоке операционной системы, от которого поступил вызов, или значение null, если ни одна задача в данный момент в данном потоке.</span><span class="sxs-lookup"><span data-stu-id="b5b01-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5b01-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5b01-107">Return Value</span></span>  
  
|<span data-ttu-id="b5b01-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5b01-108">HRESULT</span></span>|<span data-ttu-id="b5b01-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b5b01-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5b01-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5b01-110">S_OK</span></span>|<span data-ttu-id="b5b01-111">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="b5b01-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b5b01-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b5b01-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b5b01-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b5b01-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b5b01-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b5b01-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b5b01-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b5b01-115">The call timed out.</span></span>|  
|<span data-ttu-id="b5b01-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b5b01-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b5b01-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b5b01-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b5b01-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b5b01-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b5b01-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b5b01-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b5b01-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5b01-120">E_FAIL</span></span>|<span data-ttu-id="b5b01-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="b5b01-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b5b01-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b5b01-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b5b01-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b5b01-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5b01-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5b01-124">Remarks</span></span>  
 <span data-ttu-id="b5b01-125">`ICLRTask` Экземпляр, на котором `ppTask` указывает параметр представляет текущая выполняющаяся задача для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b5b01-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="b5b01-126">`ICLRTask` Связан экземпляр с соответствующими [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра, который представляет задачу для узла.</span><span class="sxs-lookup"><span data-stu-id="b5b01-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5b01-127">Требования</span><span class="sxs-lookup"><span data-stu-id="b5b01-127">Requirements</span></span>  
 <span data-ttu-id="b5b01-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5b01-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5b01-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b5b01-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5b01-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5b01-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b5b01-131">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b5b01-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b5b01-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b5b01-132">See also</span></span>

- [<span data-ttu-id="b5b01-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b5b01-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b5b01-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b5b01-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b5b01-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b5b01-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b5b01-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b5b01-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
