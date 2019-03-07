---
title: Метод IHostPolicyManager::OnFailure
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b049322751c00895ca340c40274088a795f7b51f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471875"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="7a039-102">Метод IHostPolicyManager::OnFailure</span><span class="sxs-lookup"><span data-stu-id="7a039-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="7a039-103">Уведомляет основное приложение, среда CLR (CLR) собирается выполнить действие, заданное с помощью вызова [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) метод в ответ на сбой выделения и освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7a039-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a039-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a039-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a039-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7a039-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="7a039-106">[in] Один из [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значения, указывающие тип ошибки, к которой отвечает среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7a039-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="7a039-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающий действие CLR занимает в ответ на `failure`.</span><span class="sxs-lookup"><span data-stu-id="7a039-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a039-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7a039-108">Return Value</span></span>  
  
|<span data-ttu-id="7a039-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a039-109">HRESULT</span></span>|<span data-ttu-id="7a039-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7a039-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a039-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a039-111">S_OK</span></span>|<span data-ttu-id="7a039-112">`OnFailure` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7a039-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="7a039-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a039-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a039-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7a039-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a039-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a039-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a039-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7a039-116">The call timed out.</span></span>|  
|<span data-ttu-id="7a039-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a039-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a039-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7a039-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a039-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a039-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a039-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7a039-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a039-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a039-121">E_FAIL</span></span>|<span data-ttu-id="7a039-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="7a039-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a039-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7a039-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a039-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7a039-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a039-125">Требования</span><span class="sxs-lookup"><span data-stu-id="7a039-125">Requirements</span></span>  
 <span data-ttu-id="7a039-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a039-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a039-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a039-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a039-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a039-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a039-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a039-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a039-130">См. также</span><span class="sxs-lookup"><span data-stu-id="7a039-130">See also</span></span>
- [<span data-ttu-id="7a039-131">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="7a039-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="7a039-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="7a039-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="7a039-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="7a039-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="7a039-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="7a039-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
