---
title: Метод IHostCrst::Leave
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: 050af068579d84b984ed83377d0c201e281bd154
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130534"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="376e2-102">Метод IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="376e2-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="376e2-103">Оставляет критический раздел, представленный текущим экземпляром [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="376e2-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="376e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="376e2-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="376e2-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="376e2-105">Return Value</span></span>  
  
|<span data-ttu-id="376e2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="376e2-106">HRESULT</span></span>|<span data-ttu-id="376e2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="376e2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="376e2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="376e2-108">S_OK</span></span>|<span data-ttu-id="376e2-109">`Leave` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="376e2-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="376e2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="376e2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="376e2-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="376e2-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="376e2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="376e2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="376e2-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="376e2-113">The call timed out.</span></span>|  
|<span data-ttu-id="376e2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="376e2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="376e2-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="376e2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="376e2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="376e2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="376e2-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="376e2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="376e2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="376e2-118">E_FAIL</span></span>|<span data-ttu-id="376e2-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="376e2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="376e2-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="376e2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="376e2-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="376e2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="376e2-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="376e2-122">Remarks</span></span>  
 <span data-ttu-id="376e2-123">`Leave` позволяет среде CLR напрямую взаимодействовать с реализацией потоковой реализации узла вместо использования соответствующей функции Win32 `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="376e2-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="376e2-124">Поток, который принимает владение критической секцией, представленной текущим экземпляром `IHostCrst`, должен вызывать `Leave` один раз для каждого входа в критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="376e2-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="376e2-125">Требования</span><span class="sxs-lookup"><span data-stu-id="376e2-125">Requirements</span></span>  
 <span data-ttu-id="376e2-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="376e2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="376e2-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="376e2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="376e2-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="376e2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="376e2-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="376e2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="376e2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="376e2-130">See also</span></span>

- [<span data-ttu-id="376e2-131">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="376e2-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="376e2-132">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="376e2-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="376e2-133">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="376e2-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
