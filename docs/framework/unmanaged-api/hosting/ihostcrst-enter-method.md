---
title: Метод IHostCrst::Enter
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
ms.openlocfilehash: 757fb996b268892818a54a3f80a54edfd89c7630
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124434"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="2f5be-102">Метод IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="2f5be-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="2f5be-103">Вводит критическую секцию, представленную текущим экземпляром [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2f5be-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f5be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f5be-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f5be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f5be-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="2f5be-106">окне Одно из значений [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , указывающее, какое действие должно предпринять узел, если операция блокируется.</span><span class="sxs-lookup"><span data-stu-id="2f5be-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f5be-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f5be-107">Return Value</span></span>  
  
|<span data-ttu-id="2f5be-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f5be-108">HRESULT</span></span>|<span data-ttu-id="2f5be-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2f5be-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f5be-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f5be-110">S_OK</span></span>|<span data-ttu-id="2f5be-111">`Enter` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2f5be-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="2f5be-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f5be-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f5be-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2f5be-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f5be-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f5be-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f5be-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2f5be-115">The call timed out.</span></span>|  
|<span data-ttu-id="2f5be-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f5be-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f5be-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2f5be-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f5be-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f5be-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f5be-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2f5be-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f5be-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f5be-120">E_FAIL</span></span>|<span data-ttu-id="2f5be-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2f5be-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f5be-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2f5be-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f5be-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2f5be-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f5be-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="2f5be-124">Remarks</span></span>  
 <span data-ttu-id="2f5be-125">`Enter` дублирует функцию Win32 `EnterCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="2f5be-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f5be-126">Этот метод не возвращает значение до тех пор, пока не будет указан критический раздел.</span><span class="sxs-lookup"><span data-stu-id="2f5be-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f5be-127">Требования</span><span class="sxs-lookup"><span data-stu-id="2f5be-127">Requirements</span></span>  
 <span data-ttu-id="2f5be-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f5be-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f5be-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2f5be-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f5be-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2f5be-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f5be-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f5be-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5be-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2f5be-132">See also</span></span>

- [<span data-ttu-id="2f5be-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="2f5be-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2f5be-134">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="2f5be-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="2f5be-135">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="2f5be-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
