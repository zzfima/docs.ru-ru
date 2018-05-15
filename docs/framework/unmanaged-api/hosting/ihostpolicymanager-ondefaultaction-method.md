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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17a14b09de14f32e2ae3646f7847d44307ab3b53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="86f42-102">Метод IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="86f42-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="86f42-103">Уведомляет узел, который общеязыковой среды выполнения (CLR) должен предпринять действия по умолчанию, который был задан с помощью вызова [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) метода в ответ на прерывание потока или <xref:System.AppDomain> выгрузки.</span><span class="sxs-lookup"><span data-stu-id="86f42-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f42-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86f42-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86f42-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86f42-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="86f42-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значений, указывающее тип события, к которому отвечает среды CLR.</span><span class="sxs-lookup"><span data-stu-id="86f42-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="86f42-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающее действие, требующее среды CLR в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="86f42-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86f42-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86f42-108">Return Value</span></span>  
  
|<span data-ttu-id="86f42-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86f42-109">HRESULT</span></span>|<span data-ttu-id="86f42-110">Описание</span><span class="sxs-lookup"><span data-stu-id="86f42-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86f42-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86f42-111">S_OK</span></span>|<span data-ttu-id="86f42-112">`OnDefaultAction` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="86f42-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="86f42-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86f42-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86f42-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="86f42-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="86f42-115">успешно</span><span class="sxs-lookup"><span data-stu-id="86f42-115">successfully</span></span>|  
|<span data-ttu-id="86f42-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86f42-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86f42-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="86f42-117">The call timed out.</span></span>|  
|<span data-ttu-id="86f42-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86f42-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86f42-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="86f42-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86f42-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86f42-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86f42-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="86f42-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86f42-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86f42-122">E_FAIL</span></span>|<span data-ttu-id="86f42-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="86f42-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86f42-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="86f42-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86f42-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="86f42-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86f42-126">Требования</span><span class="sxs-lookup"><span data-stu-id="86f42-126">Requirements</span></span>  
 <span data-ttu-id="86f42-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86f42-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86f42-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="86f42-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86f42-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86f42-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86f42-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86f42-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f42-131">См. также</span><span class="sxs-lookup"><span data-stu-id="86f42-131">See Also</span></span>  
 [<span data-ttu-id="86f42-132">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="86f42-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="86f42-133">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="86f42-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="86f42-134">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="86f42-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="86f42-135">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="86f42-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
