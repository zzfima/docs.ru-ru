---
title: "Метод IHostIoCompletionManager::CloseIoCompletionPort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CloseIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 066d51c821cf86522ffaca4c15db360ce96ed773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="d7041-102">Метод IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="d7041-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="d7041-103">Запросы, что узел закрыть порт, который был открыт по предыдущим вызовом [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="d7041-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7041-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7041-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7041-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7041-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="d7041-106">[in] Дескриптор для закрытия порта.</span><span class="sxs-lookup"><span data-stu-id="d7041-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7041-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7041-107">Return Value</span></span>  
  
|<span data-ttu-id="d7041-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7041-108">HRESULT</span></span>|<span data-ttu-id="d7041-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d7041-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7041-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7041-110">S_OK</span></span>|<span data-ttu-id="d7041-111">`CloseIoCompletionPort`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d7041-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="d7041-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7041-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7041-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d7041-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7041-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7041-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7041-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d7041-115">The call timed out.</span></span>|  
|<span data-ttu-id="d7041-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7041-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7041-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d7041-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7041-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7041-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7041-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d7041-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7041-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7041-120">E_FAIL</span></span>|<span data-ttu-id="d7041-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d7041-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7041-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d7041-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7041-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d7041-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d7041-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d7041-124">E_INVALIDARG</span></span>|<span data-ttu-id="d7041-125">Передан недопустимый дескриптор порта.</span><span class="sxs-lookup"><span data-stu-id="d7041-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7041-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7041-126">Remarks</span></span>  
 <span data-ttu-id="d7041-127">`hPort`должен быть дескриптор к порту, созданные предыдущими вызовами метода `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="d7041-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7041-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d7041-128">Requirements</span></span>  
 <span data-ttu-id="d7041-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7041-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7041-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7041-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7041-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7041-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7041-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7041-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7041-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d7041-133">See Also</span></span>  
 [<span data-ttu-id="d7041-134">ICLRIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d7041-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="d7041-135">IHostIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d7041-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
