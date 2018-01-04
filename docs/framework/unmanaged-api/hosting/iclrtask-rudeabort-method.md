---
title: "Метод ICLRTask::RudeAbort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.RudeAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f48de1fb44d978b1d9c8960c3e44c360b0801e27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="70062-102">Метод ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="70062-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="70062-103">Указывает, что общеязыковой среды выполнения (CLR), чтобы прервать задачу, представленную текущим [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра немедленно и безусловно.</span><span class="sxs-lookup"><span data-stu-id="70062-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70062-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70062-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="70062-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="70062-105">Return Value</span></span>  
  
|<span data-ttu-id="70062-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70062-106">HRESULT</span></span>|<span data-ttu-id="70062-107">Описание</span><span class="sxs-lookup"><span data-stu-id="70062-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70062-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="70062-108">S_OK</span></span>|<span data-ttu-id="70062-109">`RudeAbort`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="70062-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="70062-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="70062-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="70062-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="70062-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="70062-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="70062-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="70062-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="70062-113">The call timed out.</span></span>|  
|<span data-ttu-id="70062-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="70062-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="70062-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="70062-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="70062-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="70062-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="70062-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="70062-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="70062-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="70062-118">E_FAIL</span></span>|<span data-ttu-id="70062-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="70062-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="70062-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="70062-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="70062-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="70062-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70062-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="70062-122">Remarks</span></span>  
 <span data-ttu-id="70062-123">Узел вызывает `RudeAbort` немедленно прервать задачу.</span><span class="sxs-lookup"><span data-stu-id="70062-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="70062-124">Методы завершения и процедур обработки исключений не гарантируется для выполнения.</span><span class="sxs-lookup"><span data-stu-id="70062-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70062-125">Требования</span><span class="sxs-lookup"><span data-stu-id="70062-125">Requirements</span></span>  
 <span data-ttu-id="70062-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70062-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70062-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="70062-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70062-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70062-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70062-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70062-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70062-130">См. также</span><span class="sxs-lookup"><span data-stu-id="70062-130">See Also</span></span>  
 [<span data-ttu-id="70062-131">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="70062-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="70062-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="70062-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="70062-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="70062-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="70062-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="70062-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
