---
title: Метод IHostCrst::TryEnter
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9c463b055f5bd7d965e2df9428ee7c4a1e612dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675279"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="5c9bc-102">Метод IHostCrst::TryEnter</span><span class="sxs-lookup"><span data-stu-id="5c9bc-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="5c9bc-103">Пытается войти в критический раздел, представленный текущим [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c9bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c9bc-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c9bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c9bc-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="5c9bc-106">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающее, какое действие должен выполнить узел, если операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="5c9bc-107">[out] `true` Если критический раздел может быть введенная; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c9bc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5c9bc-108">Return Value</span></span>  
  
|<span data-ttu-id="5c9bc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c9bc-109">HRESULT</span></span>|<span data-ttu-id="5c9bc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5c9bc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c9bc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c9bc-111">S_OK</span></span>|<span data-ttu-id="5c9bc-112">`TryEnter` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="5c9bc-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5c9bc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5c9bc-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5c9bc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5c9bc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5c9bc-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-116">The call timed out.</span></span>|  
|<span data-ttu-id="5c9bc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5c9bc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5c9bc-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5c9bc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5c9bc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5c9bc-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5c9bc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c9bc-121">E_FAIL</span></span>|<span data-ttu-id="5c9bc-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c9bc-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5c9bc-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c9bc-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c9bc-125">Remarks</span></span>  
 <span data-ttu-id="5c9bc-126">`TryEnter` возврат немедленно, указывает ли вызывающий поток вошел в критический раздел.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="5c9bc-127">Этот метод отражает Wind32 `TryEnterCriticalSection` функции.</span><span class="sxs-lookup"><span data-stu-id="5c9bc-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c9bc-128">Требования</span><span class="sxs-lookup"><span data-stu-id="5c9bc-128">Requirements</span></span>  
 <span data-ttu-id="5c9bc-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c9bc-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c9bc-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c9bc-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c9bc-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c9bc-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c9bc-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c9bc-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9bc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5c9bc-133">See also</span></span>
- [<span data-ttu-id="5c9bc-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5c9bc-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5c9bc-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="5c9bc-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="5c9bc-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5c9bc-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
