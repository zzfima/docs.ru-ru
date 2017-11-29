---
title: "Метод ICLRDebugManager::IsDebuggerAttached"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 986c9ab7853324d1a2f0fc104399141068ae9a09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="06d89-102">Метод ICLRDebugManager::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="06d89-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="06d89-103">Получает значение, показывающее, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="06d89-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06d89-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06d89-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06d89-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="06d89-106">[out] `true` Если отладчик присоединен к процессу; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="06d89-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06d89-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="06d89-107">Return Value</span></span>  
  
|<span data-ttu-id="06d89-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06d89-108">HRESULT</span></span>|<span data-ttu-id="06d89-109">Описание</span><span class="sxs-lookup"><span data-stu-id="06d89-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06d89-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="06d89-110">S_OK</span></span>|<span data-ttu-id="06d89-111">`IsDebuggerAttached`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="06d89-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="06d89-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06d89-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06d89-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="06d89-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="06d89-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="06d89-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="06d89-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="06d89-115">The call timed out.</span></span>|  
|<span data-ttu-id="06d89-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="06d89-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="06d89-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="06d89-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="06d89-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="06d89-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="06d89-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="06d89-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="06d89-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06d89-120">E_FAIL</span></span>|<span data-ttu-id="06d89-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="06d89-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06d89-122">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="06d89-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="06d89-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="06d89-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06d89-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="06d89-124">Remarks</span></span>  
 <span data-ttu-id="06d89-125">`IsDebuggerAttached`предоставляет узлу возможность запрашивать средой CLR с целью определить, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="06d89-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d89-126">Требования</span><span class="sxs-lookup"><span data-stu-id="06d89-126">Requirements</span></span>  
 <span data-ttu-id="06d89-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06d89-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d89-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06d89-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06d89-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06d89-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06d89-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d89-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d89-131">См. также</span><span class="sxs-lookup"><span data-stu-id="06d89-131">See Also</span></span>  
 [<span data-ttu-id="06d89-132">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="06d89-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="06d89-133">Iclrdebugmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="06d89-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="06d89-134">IHostControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="06d89-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
