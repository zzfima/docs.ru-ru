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
ms.openlocfilehash: f4b40a595bbdea4dd390a42af6a0d4b1a5efa2f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130498"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="14e04-102">Метод IHostCrst::TryEnter</span><span class="sxs-lookup"><span data-stu-id="14e04-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="14e04-103">Пытается ввести критическую секцию, представленную текущим экземпляром [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="14e04-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14e04-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14e04-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="14e04-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="14e04-106">окне Одно из значений [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , указывающее, какое действие должно предпринять узел, если операция блокируется.</span><span class="sxs-lookup"><span data-stu-id="14e04-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="14e04-107">[out] `true`, если можно указать критический раздел; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="14e04-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14e04-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="14e04-108">Return Value</span></span>  
  
|<span data-ttu-id="14e04-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14e04-109">HRESULT</span></span>|<span data-ttu-id="14e04-110">Описание</span><span class="sxs-lookup"><span data-stu-id="14e04-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14e04-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="14e04-111">S_OK</span></span>|<span data-ttu-id="14e04-112">`TryEnter` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="14e04-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="14e04-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14e04-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14e04-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="14e04-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14e04-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14e04-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14e04-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="14e04-116">The call timed out.</span></span>|  
|<span data-ttu-id="14e04-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14e04-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14e04-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="14e04-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14e04-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14e04-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14e04-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="14e04-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14e04-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14e04-121">E_FAIL</span></span>|<span data-ttu-id="14e04-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="14e04-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14e04-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="14e04-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14e04-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="14e04-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e04-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="14e04-125">Remarks</span></span>  
 <span data-ttu-id="14e04-126">`TryEnter` немедленно возвращает значение и указывает, вошел ли вызывающий поток в критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="14e04-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="14e04-127">Этот метод отражает функцию Wind32 `TryEnterCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="14e04-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14e04-128">Требования</span><span class="sxs-lookup"><span data-stu-id="14e04-128">Requirements</span></span>  
 <span data-ttu-id="14e04-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14e04-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e04-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="14e04-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14e04-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="14e04-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14e04-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14e04-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e04-133">См. также</span><span class="sxs-lookup"><span data-stu-id="14e04-133">See also</span></span>

- [<span data-ttu-id="14e04-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="14e04-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="14e04-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="14e04-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="14e04-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="14e04-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
