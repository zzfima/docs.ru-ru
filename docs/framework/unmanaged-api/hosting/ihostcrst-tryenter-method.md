---
title: "Метод IHostCrst::TryEnter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.TryEnter
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c6b622666c3bda806c77329d0d0a10726b4838c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="9f0c2-102">Метод IHostCrst::TryEnter</span><span class="sxs-lookup"><span data-stu-id="9f0c2-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="9f0c2-103">Пытается выполнить вход в критическую секцию, представленную текущим [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f0c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f0c2-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f0c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f0c2-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="9f0c2-106">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающее, какое действие должен предпринять узел, если операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="9f0c2-107">[out] `true` Если критический раздел может быть введенная; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f0c2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9f0c2-108">Return Value</span></span>  
  
|<span data-ttu-id="9f0c2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f0c2-109">HRESULT</span></span>|<span data-ttu-id="9f0c2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="9f0c2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f0c2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f0c2-111">S_OK</span></span>|<span data-ttu-id="9f0c2-112">`TryEnter`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="9f0c2-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f0c2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f0c2-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f0c2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f0c2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f0c2-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-116">The call timed out.</span></span>|  
|<span data-ttu-id="9f0c2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f0c2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f0c2-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f0c2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f0c2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f0c2-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f0c2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f0c2-121">E_FAIL</span></span>|<span data-ttu-id="9f0c2-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f0c2-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f0c2-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f0c2-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f0c2-125">Remarks</span></span>  
 <span data-ttu-id="9f0c2-126">`TryEnter`возврат немедленно, указывает ли вызывающий поток вошел в критической секции.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="9f0c2-127">Этот метод получает зеркально Wind32 `TryEnterCriticalSection` функции.</span><span class="sxs-lookup"><span data-stu-id="9f0c2-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f0c2-128">Требования</span><span class="sxs-lookup"><span data-stu-id="9f0c2-128">Requirements</span></span>  
 <span data-ttu-id="9f0c2-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f0c2-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f0c2-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f0c2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f0c2-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f0c2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f0c2-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f0c2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0c2-133">См. также</span><span class="sxs-lookup"><span data-stu-id="9f0c2-133">See Also</span></span>  
 [<span data-ttu-id="9f0c2-134">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9f0c2-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="9f0c2-135">IHostCrst-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9f0c2-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="9f0c2-136">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9f0c2-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
