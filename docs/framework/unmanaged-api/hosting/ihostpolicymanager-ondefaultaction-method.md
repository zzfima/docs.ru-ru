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
ms.openlocfilehash: 45167a2b358b9a7a39390c07f552aa3f3dabce4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108658"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="abc35-102">Метод IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="abc35-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="abc35-103">Уведомляет основное приложение, среда CLR (CLR) сейчас будет выполняться действие по умолчанию, который был задан с помощью вызова [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) метод в ответ на прерывание или <xref:System.AppDomain> выгрузить.</span><span class="sxs-lookup"><span data-stu-id="abc35-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abc35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abc35-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abc35-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="abc35-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="abc35-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значения, указывающие тип события, к которой отвечает среды CLR.</span><span class="sxs-lookup"><span data-stu-id="abc35-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="abc35-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения, указывающие действие, которое среда CLR занимает в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="abc35-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abc35-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="abc35-108">Return Value</span></span>  
  
|<span data-ttu-id="abc35-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abc35-109">HRESULT</span></span>|<span data-ttu-id="abc35-110">Описание</span><span class="sxs-lookup"><span data-stu-id="abc35-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abc35-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="abc35-111">S_OK</span></span>|`OnDefaultAction` <span data-ttu-id="abc35-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="abc35-112">returned successfully.</span></span>|  
|<span data-ttu-id="abc35-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="abc35-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="abc35-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором он не может выполнять управляемый код или обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="abc35-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="abc35-115">успешно</span><span class="sxs-lookup"><span data-stu-id="abc35-115">successfully</span></span>|  
|<span data-ttu-id="abc35-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="abc35-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="abc35-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="abc35-117">The call timed out.</span></span>|  
|<span data-ttu-id="abc35-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="abc35-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="abc35-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="abc35-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="abc35-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="abc35-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="abc35-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="abc35-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="abc35-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="abc35-122">E_FAIL</span></span>|<span data-ttu-id="abc35-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="abc35-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="abc35-124">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="abc35-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="abc35-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="abc35-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="abc35-126">Требования</span><span class="sxs-lookup"><span data-stu-id="abc35-126">Requirements</span></span>  
 <span data-ttu-id="abc35-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abc35-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abc35-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="abc35-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abc35-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abc35-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="abc35-130">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="abc35-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="abc35-131">См. также</span><span class="sxs-lookup"><span data-stu-id="abc35-131">See also</span></span>

- [<span data-ttu-id="abc35-132">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="abc35-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="abc35-133">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="abc35-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="abc35-134">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="abc35-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="abc35-135">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="abc35-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
