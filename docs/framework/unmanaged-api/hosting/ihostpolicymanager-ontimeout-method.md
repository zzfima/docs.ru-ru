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
ms.openlocfilehash: ad1a9bc6b2e5c84f15cf0cf706504f18341f8584
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209181"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="efa9e-102">Метод IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="efa9e-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="efa9e-103">Уведомляет основное приложение, среда CLR (CLR) собирается выполнить действие, заданное с помощью вызова [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) метод в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="efa9e-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efa9e-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efa9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efa9e-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="efa9e-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значений, указывающих на вид операции, в которой истекло.</span><span class="sxs-lookup"><span data-stu-id="efa9e-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="efa9e-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающий действие CLR занимает в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="efa9e-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efa9e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="efa9e-108">Return Value</span></span>  
  
|<span data-ttu-id="efa9e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efa9e-109">HRESULT</span></span>|<span data-ttu-id="efa9e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="efa9e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efa9e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="efa9e-111">S_OK</span></span>|`OnTimeout` <span data-ttu-id="efa9e-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="efa9e-112">returned successfully.</span></span>|  
|<span data-ttu-id="efa9e-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="efa9e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="efa9e-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="efa9e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="efa9e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="efa9e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="efa9e-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="efa9e-116">The call timed out.</span></span>|  
|<span data-ttu-id="efa9e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="efa9e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="efa9e-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="efa9e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="efa9e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="efa9e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="efa9e-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="efa9e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="efa9e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="efa9e-121">E_FAIL</span></span>|<span data-ttu-id="efa9e-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="efa9e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="efa9e-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="efa9e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="efa9e-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="efa9e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efa9e-125">Требования</span><span class="sxs-lookup"><span data-stu-id="efa9e-125">Requirements</span></span>  
 <span data-ttu-id="efa9e-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efa9e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa9e-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="efa9e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efa9e-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efa9e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="efa9e-129">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="efa9e-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efa9e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="efa9e-130">See also</span></span>

- [<span data-ttu-id="efa9e-131">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="efa9e-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="efa9e-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="efa9e-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="efa9e-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="efa9e-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="efa9e-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="efa9e-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
