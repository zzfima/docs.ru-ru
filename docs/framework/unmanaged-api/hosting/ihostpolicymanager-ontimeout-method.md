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
ms.openlocfilehash: e8a14dd6a6d196cea9caa6be669b2b75a167eca8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141107"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="46e5c-102">Метод IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="46e5c-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="46e5c-103">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом метода [ICLRPolicyManager:: сетактиононтимеаут](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="46e5c-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e5c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46e5c-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46e5c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46e5c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="46e5c-106">окне Одно из значений [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , указывающее тип операции, для которой истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="46e5c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="46e5c-107">окне Одно из значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , указывающее действие, ВЫПОЛНЯЕМое средой CLR в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="46e5c-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46e5c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46e5c-108">Return Value</span></span>  
  
|<span data-ttu-id="46e5c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46e5c-109">HRESULT</span></span>|<span data-ttu-id="46e5c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="46e5c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46e5c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="46e5c-111">S_OK</span></span>|<span data-ttu-id="46e5c-112">`OnTimeout` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="46e5c-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="46e5c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46e5c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46e5c-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="46e5c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46e5c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46e5c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46e5c-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="46e5c-116">The call timed out.</span></span>|  
|<span data-ttu-id="46e5c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46e5c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46e5c-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="46e5c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46e5c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46e5c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46e5c-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="46e5c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46e5c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46e5c-121">E_FAIL</span></span>|<span data-ttu-id="46e5c-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="46e5c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46e5c-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="46e5c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46e5c-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="46e5c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46e5c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="46e5c-125">Requirements</span></span>  
 <span data-ttu-id="46e5c-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46e5c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46e5c-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="46e5c-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46e5c-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="46e5c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46e5c-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46e5c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e5c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="46e5c-130">See also</span></span>

- [<span data-ttu-id="46e5c-131">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="46e5c-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="46e5c-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="46e5c-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="46e5c-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="46e5c-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="46e5c-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="46e5c-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
