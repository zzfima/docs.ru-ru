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
ms.openlocfilehash: 3bb65d747d7cdc81bd534108f6189eb1c94e3b15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128546"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="d115b-102">Метод IHostPolicyManager::OnFailure</span><span class="sxs-lookup"><span data-stu-id="d115b-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="d115b-103">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом метода [ICLRPolicyManager:: сетактиононфаилуре](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) в ответ на выделение ресурсов или сбой при реорганизации.</span><span class="sxs-lookup"><span data-stu-id="d115b-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d115b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d115b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d115b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d115b-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="d115b-106">окне Одно из значений [еклрфаилуре](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) , указывающее тип сбоя, на который отвечает среда CLR.</span><span class="sxs-lookup"><span data-stu-id="d115b-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="d115b-107">окне Одно из значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , указывающее действие, которое среда CLR принимает в ответ на `failure`.</span><span class="sxs-lookup"><span data-stu-id="d115b-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d115b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d115b-108">Return Value</span></span>  
  
|<span data-ttu-id="d115b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d115b-109">HRESULT</span></span>|<span data-ttu-id="d115b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d115b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d115b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d115b-111">S_OK</span></span>|<span data-ttu-id="d115b-112">`OnFailure` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d115b-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="d115b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d115b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d115b-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d115b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d115b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d115b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d115b-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d115b-116">The call timed out.</span></span>|  
|<span data-ttu-id="d115b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d115b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d115b-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d115b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d115b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d115b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d115b-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d115b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d115b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d115b-121">E_FAIL</span></span>|<span data-ttu-id="d115b-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d115b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d115b-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d115b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d115b-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d115b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d115b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d115b-125">Requirements</span></span>  
 <span data-ttu-id="d115b-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d115b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d115b-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d115b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d115b-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d115b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d115b-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d115b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d115b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d115b-130">See also</span></span>

- [<span data-ttu-id="d115b-131">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="d115b-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="d115b-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="d115b-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="d115b-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d115b-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="d115b-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d115b-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
