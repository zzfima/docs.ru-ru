---
title: Метод IHostPolicyManager::OnDefaultAction
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: 8d987614c1a5a2c90ccb3faa11c605767ae5cfda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178024"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="5efb8-102">Метод IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="5efb8-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="5efb8-103">Уведомляет узла о том, что общее время выполнения языка (CLR) собирается принять действие по умолчанию, которое было установлено <xref:System.AppDomain> вызовом на [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) метод в ответ на прекращение или выгрузку потока.</span><span class="sxs-lookup"><span data-stu-id="5efb8-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5efb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5efb8-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5efb8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5efb8-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="5efb8-106">(в) Одно из значений [EClrOperation,](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) указывающее на то, на какое событие реагирует CLR.</span><span class="sxs-lookup"><span data-stu-id="5efb8-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="5efb8-107">(в) Одно из значений [EPolicyAction,](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) указывающее на действия, предпринимаемые CLR в ответ на это событие.</span><span class="sxs-lookup"><span data-stu-id="5efb8-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5efb8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5efb8-108">Return Value</span></span>  
  
|<span data-ttu-id="5efb8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5efb8-109">HRESULT</span></span>|<span data-ttu-id="5efb8-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5efb8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5efb8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5efb8-111">S_OK</span></span>|<span data-ttu-id="5efb8-112">`OnDefaultAction`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="5efb8-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="5efb8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5efb8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5efb8-114">CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5efb8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="5efb8-115">Успешно</span><span class="sxs-lookup"><span data-stu-id="5efb8-115">successfully</span></span>|  
|<span data-ttu-id="5efb8-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5efb8-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5efb8-117">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="5efb8-117">The call timed out.</span></span>|  
|<span data-ttu-id="5efb8-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5efb8-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5efb8-119">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="5efb8-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5efb8-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5efb8-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5efb8-121">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="5efb8-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5efb8-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5efb8-122">E_FAIL</span></span>|<span data-ttu-id="5efb8-123">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="5efb8-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5efb8-124">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="5efb8-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5efb8-125">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5efb8-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5efb8-126">Требования</span><span class="sxs-lookup"><span data-stu-id="5efb8-126">Requirements</span></span>  
 <span data-ttu-id="5efb8-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5efb8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5efb8-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5efb8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5efb8-129">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5efb8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5efb8-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5efb8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5efb8-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5efb8-131">See also</span></span>

- [<span data-ttu-id="5efb8-132">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="5efb8-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="5efb8-133">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="5efb8-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="5efb8-134">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="5efb8-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="5efb8-135">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="5efb8-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
