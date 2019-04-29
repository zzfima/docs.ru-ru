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
ms.openlocfilehash: 08e4c395026a743323b40e5b1ace3db64e368078
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967738"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="2adad-102">Метод IHostCrst::TryEnter</span><span class="sxs-lookup"><span data-stu-id="2adad-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="2adad-103">Пытается войти в критический раздел, представленный текущим [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2adad-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2adad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2adad-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2adad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2adad-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="2adad-106">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающее, какое действие должен выполнить узел, если операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="2adad-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="2adad-107">[out] `true` Если критический раздел может быть введенная; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="2adad-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2adad-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2adad-108">Return Value</span></span>  
  
|<span data-ttu-id="2adad-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2adad-109">HRESULT</span></span>|<span data-ttu-id="2adad-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2adad-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2adad-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2adad-111">S_OK</span></span>|<span data-ttu-id="2adad-112">`TryEnter` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2adad-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="2adad-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2adad-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2adad-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2adad-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2adad-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2adad-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2adad-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2adad-116">The call timed out.</span></span>|  
|<span data-ttu-id="2adad-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2adad-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2adad-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2adad-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2adad-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2adad-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2adad-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2adad-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2adad-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2adad-121">E_FAIL</span></span>|<span data-ttu-id="2adad-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="2adad-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2adad-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2adad-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2adad-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2adad-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2adad-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="2adad-125">Remarks</span></span>  
 <span data-ttu-id="2adad-126">`TryEnter` возврат немедленно, указывает ли вызывающий поток вошел в критический раздел.</span><span class="sxs-lookup"><span data-stu-id="2adad-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="2adad-127">Этот метод отражает Wind32 `TryEnterCriticalSection` функции.</span><span class="sxs-lookup"><span data-stu-id="2adad-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2adad-128">Требования</span><span class="sxs-lookup"><span data-stu-id="2adad-128">Requirements</span></span>  
 <span data-ttu-id="2adad-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2adad-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2adad-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2adad-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2adad-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2adad-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2adad-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2adad-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2adad-133">См. также</span><span class="sxs-lookup"><span data-stu-id="2adad-133">See also</span></span>

- [<span data-ttu-id="2adad-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="2adad-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2adad-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="2adad-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="2adad-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="2adad-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
