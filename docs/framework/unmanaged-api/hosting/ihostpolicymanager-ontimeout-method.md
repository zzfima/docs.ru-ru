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
ms.openlocfilehash: d5b5fa5198ae2c0bba30ae0f8d6d3834f2891672
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178004"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="602f7-102">Метод IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="602f7-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="602f7-103">Уведомляет хост о том, что время выполнения общего языка (CLR) собирается принять действие, указанное вызовом в [iCLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) метод в ответ на тайм-аут.</span><span class="sxs-lookup"><span data-stu-id="602f7-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="602f7-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="602f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="602f7-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="602f7-106">(в) Одно из значений [EClrOperation,](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) указывающего на вид операции, который приурочен.</span><span class="sxs-lookup"><span data-stu-id="602f7-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="602f7-107">(в) Одно из значений [EPolicyAction,](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) указывающее действие, предпринимаемое CLR в ответ на тайм-аут.</span><span class="sxs-lookup"><span data-stu-id="602f7-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="602f7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="602f7-108">Return Value</span></span>  
  
|<span data-ttu-id="602f7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="602f7-109">HRESULT</span></span>|<span data-ttu-id="602f7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="602f7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="602f7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="602f7-111">S_OK</span></span>|<span data-ttu-id="602f7-112">`OnTimeout`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="602f7-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="602f7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="602f7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="602f7-114">CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="602f7-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="602f7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="602f7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="602f7-116">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="602f7-116">The call timed out.</span></span>|  
|<span data-ttu-id="602f7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="602f7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="602f7-118">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="602f7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="602f7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="602f7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="602f7-120">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="602f7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="602f7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="602f7-121">E_FAIL</span></span>|<span data-ttu-id="602f7-122">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="602f7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="602f7-123">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="602f7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="602f7-124">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="602f7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="602f7-125">Требования</span><span class="sxs-lookup"><span data-stu-id="602f7-125">Requirements</span></span>  
 <span data-ttu-id="602f7-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="602f7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602f7-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="602f7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="602f7-128">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="602f7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="602f7-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602f7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602f7-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="602f7-130">See also</span></span>

- [<span data-ttu-id="602f7-131">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="602f7-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="602f7-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="602f7-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="602f7-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="602f7-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="602f7-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="602f7-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
