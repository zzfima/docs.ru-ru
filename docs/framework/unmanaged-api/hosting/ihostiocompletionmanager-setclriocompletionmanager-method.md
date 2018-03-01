---
title: "Метод IHostIoCompletionManager::SetCLRIoCompletionManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fde1045fd0f15e7255a163c1f1b041800e85921
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="42279-102">Метод IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="42279-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="42279-103">Предоставляет основному указатель интерфейса [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="42279-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42279-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42279-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42279-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="42279-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="42279-106">[in] Указатель интерфейса `ICLRIoCompletionManager` экземпляра, предоставляемую средой CLR.</span><span class="sxs-lookup"><span data-stu-id="42279-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42279-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="42279-107">Return Value</span></span>  
  
|<span data-ttu-id="42279-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42279-108">HRESULT</span></span>|<span data-ttu-id="42279-109">Описание</span><span class="sxs-lookup"><span data-stu-id="42279-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42279-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="42279-110">S_OK</span></span>|<span data-ttu-id="42279-111">`SetCLRIoCompletionManager`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="42279-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="42279-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42279-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42279-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="42279-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42279-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42279-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42279-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="42279-115">The call timed out.</span></span>|  
|<span data-ttu-id="42279-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42279-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42279-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="42279-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42279-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42279-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42279-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="42279-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42279-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42279-120">E_FAIL</span></span>|<span data-ttu-id="42279-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="42279-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42279-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="42279-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42279-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="42279-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42279-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="42279-124">Remarks</span></span>  
 <span data-ttu-id="42279-125">После вызова CLR `SetCLRIoCompletionManager`, узел должен вызвать метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) для уведомления среды CLR при завершении запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="42279-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42279-126">Требования</span><span class="sxs-lookup"><span data-stu-id="42279-126">Requirements</span></span>  
 <span data-ttu-id="42279-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42279-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42279-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42279-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42279-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42279-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42279-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42279-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42279-131">См. также</span><span class="sxs-lookup"><span data-stu-id="42279-131">See Also</span></span>  
 [<span data-ttu-id="42279-132">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="42279-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="42279-133">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="42279-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
