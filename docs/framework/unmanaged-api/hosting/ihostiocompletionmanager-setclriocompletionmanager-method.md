---
title: "Метод IHostIoCompletionManager::SetCLRIoCompletionManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetCLRIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2447ba9cf3ee5968bde26b0a578cc06ef5c614c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="50983-102">Метод IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="50983-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="50983-103">Предоставляет основному указатель интерфейса [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="50983-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50983-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50983-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50983-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50983-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="50983-106">[in] Указатель интерфейса `ICLRIoCompletionManager` экземпляра, предоставляемую средой CLR.</span><span class="sxs-lookup"><span data-stu-id="50983-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50983-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="50983-107">Return Value</span></span>  
  
|<span data-ttu-id="50983-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50983-108">HRESULT</span></span>|<span data-ttu-id="50983-109">Описание</span><span class="sxs-lookup"><span data-stu-id="50983-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50983-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50983-110">S_OK</span></span>|<span data-ttu-id="50983-111">`SetCLRIoCompletionManager`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="50983-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="50983-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50983-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50983-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="50983-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50983-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50983-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50983-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="50983-115">The call timed out.</span></span>|  
|<span data-ttu-id="50983-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50983-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50983-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="50983-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50983-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50983-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50983-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="50983-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50983-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50983-120">E_FAIL</span></span>|<span data-ttu-id="50983-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="50983-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50983-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="50983-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50983-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50983-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50983-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="50983-124">Remarks</span></span>  
 <span data-ttu-id="50983-125">После вызова CLR `SetCLRIoCompletionManager`, узел должен вызвать метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) для уведомления среды CLR при завершении запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="50983-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50983-126">Требования</span><span class="sxs-lookup"><span data-stu-id="50983-126">Requirements</span></span>  
 <span data-ttu-id="50983-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50983-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50983-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50983-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50983-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50983-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50983-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50983-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50983-131">См. также</span><span class="sxs-lookup"><span data-stu-id="50983-131">See Also</span></span>  
 [<span data-ttu-id="50983-132">ICLRIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="50983-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="50983-133">IHostIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="50983-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
