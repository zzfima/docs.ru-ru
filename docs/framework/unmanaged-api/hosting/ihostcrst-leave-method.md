---
title: "Метод IHostCrst::Leave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Leave
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21e9a99e4fd22b2cc7d954d0f7316c45ffd7074c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="58c2b-102">Метод IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="58c2b-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="58c2b-103">Покидает критическую секцию, представленный текущим экземпляром [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="58c2b-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58c2b-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="58c2b-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="58c2b-105">Return Value</span></span>  
  
|<span data-ttu-id="58c2b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58c2b-106">HRESULT</span></span>|<span data-ttu-id="58c2b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="58c2b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58c2b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="58c2b-108">S_OK</span></span>|<span data-ttu-id="58c2b-109">`Leave`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="58c2b-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="58c2b-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58c2b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58c2b-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="58c2b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58c2b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58c2b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58c2b-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="58c2b-113">The call timed out.</span></span>|  
|<span data-ttu-id="58c2b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58c2b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58c2b-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="58c2b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58c2b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58c2b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58c2b-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="58c2b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58c2b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58c2b-118">E_FAIL</span></span>|<span data-ttu-id="58c2b-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="58c2b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58c2b-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="58c2b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58c2b-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="58c2b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58c2b-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="58c2b-122">Remarks</span></span>  
 <span data-ttu-id="58c2b-123">`Leave`позволяет среде CLR для взаимодействия непосредственно с узла threading реализации, а не с помощью соответствующего Win32 `LeaveCriticalSection` функции.</span><span class="sxs-lookup"><span data-stu-id="58c2b-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="58c2b-124">Поток, который принимает право на владение критическую секцию, представленную текущим `IHostCrst` экземпляра необходимо вызвать метод `Leave` после при каждом его входе в критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="58c2b-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c2b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="58c2b-125">Requirements</span></span>  
 <span data-ttu-id="58c2b-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58c2b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c2b-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58c2b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58c2b-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58c2b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58c2b-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c2b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c2b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="58c2b-130">See Also</span></span>  
 [<span data-ttu-id="58c2b-131">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="58c2b-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="58c2b-132">IHostCrst-интерфейс</span><span class="sxs-lookup"><span data-stu-id="58c2b-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="58c2b-133">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="58c2b-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
