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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a472b686799bfec4b53b8880a0c52c6f0846b03a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442381"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="abf22-102">Метод IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="abf22-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="abf22-103">Вводит критический раздел, представленный текущим [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="abf22-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abf22-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abf22-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="abf22-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="abf22-106">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающее, какое действие должен предпринять узел, если операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="abf22-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abf22-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="abf22-107">Return Value</span></span>  
  
|<span data-ttu-id="abf22-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abf22-108">HRESULT</span></span>|<span data-ttu-id="abf22-109">Описание</span><span class="sxs-lookup"><span data-stu-id="abf22-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abf22-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="abf22-110">S_OK</span></span>|<span data-ttu-id="abf22-111">`Enter` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="abf22-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="abf22-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="abf22-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="abf22-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="abf22-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="abf22-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="abf22-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="abf22-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="abf22-115">The call timed out.</span></span>|  
|<span data-ttu-id="abf22-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="abf22-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="abf22-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="abf22-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="abf22-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="abf22-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="abf22-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="abf22-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="abf22-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="abf22-120">E_FAIL</span></span>|<span data-ttu-id="abf22-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="abf22-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="abf22-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="abf22-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="abf22-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="abf22-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abf22-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="abf22-124">Remarks</span></span>  
 <span data-ttu-id="abf22-125">`Enter` зеркально отражает Win32 `EnterCriticalSection` функции.</span><span class="sxs-lookup"><span data-stu-id="abf22-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abf22-126">Этот метод не возвращает до ввода критической секции.</span><span class="sxs-lookup"><span data-stu-id="abf22-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf22-127">Требования</span><span class="sxs-lookup"><span data-stu-id="abf22-127">Requirements</span></span>  
 <span data-ttu-id="abf22-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abf22-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf22-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="abf22-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abf22-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abf22-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abf22-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf22-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf22-132">См. также</span><span class="sxs-lookup"><span data-stu-id="abf22-132">See Also</span></span>  
 [<span data-ttu-id="abf22-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="abf22-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="abf22-134">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="abf22-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="abf22-135">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="abf22-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
