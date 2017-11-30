---
title: "Метод IHostPolicyManager::OnTimeout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnTimeout
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 272f78077c1d512fe574eebeaf6c92dc1939f6b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="dbd77-102">Метод IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="dbd77-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="dbd77-103">Уведомляет узел, который должен выполнить действие, заданное вызовом общеязыковой среды выполнения (CLR) [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) метода в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="dbd77-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbd77-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbd77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dbd77-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="dbd77-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значений, указывающих вид, истекло время ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="dbd77-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="dbd77-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающее действие, среда CLR занимает в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="dbd77-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbd77-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dbd77-108">Return Value</span></span>  
  
|<span data-ttu-id="dbd77-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbd77-109">HRESULT</span></span>|<span data-ttu-id="dbd77-110">Описание</span><span class="sxs-lookup"><span data-stu-id="dbd77-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbd77-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbd77-111">S_OK</span></span>|<span data-ttu-id="dbd77-112">`OnTimeout`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dbd77-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="dbd77-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbd77-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbd77-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dbd77-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbd77-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbd77-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbd77-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="dbd77-116">The call timed out.</span></span>|  
|<span data-ttu-id="dbd77-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbd77-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbd77-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="dbd77-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbd77-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbd77-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbd77-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="dbd77-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbd77-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbd77-121">E_FAIL</span></span>|<span data-ttu-id="dbd77-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="dbd77-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbd77-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dbd77-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbd77-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dbd77-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbd77-125">Требования</span><span class="sxs-lookup"><span data-stu-id="dbd77-125">Requirements</span></span>  
 <span data-ttu-id="dbd77-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd77-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd77-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbd77-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbd77-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dbd77-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbd77-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd77-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd77-130">См. также</span><span class="sxs-lookup"><span data-stu-id="dbd77-130">See Also</span></span>  
 [<span data-ttu-id="dbd77-131">EClrOperation-перечисление</span><span class="sxs-lookup"><span data-stu-id="dbd77-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="dbd77-132">EPolicyAction-перечисление</span><span class="sxs-lookup"><span data-stu-id="dbd77-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="dbd77-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="dbd77-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="dbd77-134">IHostPolicyManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dbd77-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
