---
title: "Метод ICLROnEventManager::UnregisterActionOnEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager.UnregisterActionOnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d295817a7c6f8a177de3ff251904beeaf8ca828
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="86e7f-102">Метод ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="86e7f-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="86e7f-103">Отменяет регистрацию ранее зарегистрированного обратного вызова указатель для указанного события.</span><span class="sxs-lookup"><span data-stu-id="86e7f-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86e7f-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86e7f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86e7f-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="86e7f-106">[in] Один из [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) значений, указывающее, события, для которого требуется отменить регистрацию обратного вызова указателя, описываемого `pAction`.</span><span class="sxs-lookup"><span data-stu-id="86e7f-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="86e7f-107">[in] Указатель на [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) объект, который был передан в качестве параметра [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="86e7f-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86e7f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86e7f-108">Return Value</span></span>  
  
|<span data-ttu-id="86e7f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86e7f-109">HRESULT</span></span>|<span data-ttu-id="86e7f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="86e7f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86e7f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86e7f-111">S_OK</span></span>|<span data-ttu-id="86e7f-112">`UnregisterActionOnEvent`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="86e7f-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="86e7f-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86e7f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86e7f-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="86e7f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86e7f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86e7f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86e7f-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="86e7f-116">The call timed out.</span></span>|  
|<span data-ttu-id="86e7f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86e7f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86e7f-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="86e7f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86e7f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86e7f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86e7f-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="86e7f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86e7f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86e7f-121">E_FAIL</span></span>|<span data-ttu-id="86e7f-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="86e7f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86e7f-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="86e7f-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86e7f-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="86e7f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86e7f-125">Требования</span><span class="sxs-lookup"><span data-stu-id="86e7f-125">Requirements</span></span>  
 <span data-ttu-id="86e7f-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86e7f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e7f-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="86e7f-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86e7f-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86e7f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86e7f-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e7f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e7f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="86e7f-130">See Also</span></span>  
 [<span data-ttu-id="86e7f-131">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="86e7f-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="86e7f-132">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="86e7f-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="86e7f-133">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="86e7f-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="86e7f-134">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="86e7f-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
