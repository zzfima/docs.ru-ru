---
title: Метод IHostPolicyManager::OnTimeout
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2badb7e1882e05678328b834b8dd094808548c9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638799"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="bb94c-102">Метод IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="bb94c-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="bb94c-103">Уведомляет основное приложение, среда CLR (CLR) собирается выполнить действие, заданное с помощью вызова [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) метод в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="bb94c-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb94c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb94c-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb94c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb94c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="bb94c-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значений, указывающих на вид операции, в которой истекло.</span><span class="sxs-lookup"><span data-stu-id="bb94c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="bb94c-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающий действие CLR занимает в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="bb94c-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb94c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb94c-108">Return Value</span></span>  
  
|<span data-ttu-id="bb94c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb94c-109">HRESULT</span></span>|<span data-ttu-id="bb94c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bb94c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb94c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb94c-111">S_OK</span></span>|<span data-ttu-id="bb94c-112">`OnTimeout` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="bb94c-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="bb94c-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bb94c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bb94c-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="bb94c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bb94c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bb94c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bb94c-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="bb94c-116">The call timed out.</span></span>|  
|<span data-ttu-id="bb94c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bb94c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bb94c-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="bb94c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bb94c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bb94c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bb94c-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="bb94c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bb94c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb94c-121">E_FAIL</span></span>|<span data-ttu-id="bb94c-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="bb94c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bb94c-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="bb94c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bb94c-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bb94c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb94c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="bb94c-125">Requirements</span></span>  
 <span data-ttu-id="bb94c-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb94c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb94c-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bb94c-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb94c-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb94c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb94c-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb94c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb94c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bb94c-130">See also</span></span>
- [<span data-ttu-id="bb94c-131">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="bb94c-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="bb94c-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="bb94c-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="bb94c-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="bb94c-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="bb94c-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="bb94c-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
