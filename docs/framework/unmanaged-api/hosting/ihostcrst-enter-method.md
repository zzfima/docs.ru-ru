---
title: "Метод IHostCrst::Enter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 390f30c85dac494451af1ff82328c913dd9438ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="6ee52-102">Метод IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="6ee52-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="6ee52-103">Вводит критический раздел, представленный текущим [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6ee52-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ee52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ee52-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ee52-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ee52-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="6ee52-106">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающее, какое действие должен предпринять узел, если операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="6ee52-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ee52-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6ee52-107">Return Value</span></span>  
  
|<span data-ttu-id="6ee52-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ee52-108">HRESULT</span></span>|<span data-ttu-id="6ee52-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6ee52-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ee52-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ee52-110">S_OK</span></span>|<span data-ttu-id="6ee52-111">`Enter`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="6ee52-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="6ee52-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ee52-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ee52-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6ee52-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ee52-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ee52-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ee52-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="6ee52-115">The call timed out.</span></span>|  
|<span data-ttu-id="6ee52-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ee52-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ee52-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="6ee52-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ee52-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ee52-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ee52-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="6ee52-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ee52-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ee52-120">E_FAIL</span></span>|<span data-ttu-id="6ee52-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="6ee52-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6ee52-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6ee52-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ee52-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6ee52-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ee52-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ee52-124">Remarks</span></span>  
 <span data-ttu-id="6ee52-125">`Enter`зеркально отражает Win32 `EnterCriticalSection` функции.</span><span class="sxs-lookup"><span data-stu-id="6ee52-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ee52-126">Этот метод не возвращает до ввода критической секции.</span><span class="sxs-lookup"><span data-stu-id="6ee52-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ee52-127">Требования</span><span class="sxs-lookup"><span data-stu-id="6ee52-127">Requirements</span></span>  
 <span data-ttu-id="6ee52-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ee52-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ee52-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ee52-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ee52-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ee52-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ee52-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ee52-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee52-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6ee52-132">See Also</span></span>  
 [<span data-ttu-id="6ee52-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="6ee52-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="6ee52-134">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="6ee52-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="6ee52-135">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="6ee52-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
