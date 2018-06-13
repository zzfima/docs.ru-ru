---
title: Метод ICLROnEventManager::UnregisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7add5e85aac273b4d513a24196af8305082c417f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434654"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="f55d6-102">Метод ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="f55d6-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="f55d6-103">Отменяет регистрацию ранее зарегистрированного обратного вызова указатель для указанного события.</span><span class="sxs-lookup"><span data-stu-id="f55d6-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f55d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f55d6-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f55d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f55d6-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="f55d6-106">[in] Один из [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) значений, указывающее, события, для которого требуется отменить регистрацию обратного вызова указателя, описываемого `pAction`.</span><span class="sxs-lookup"><span data-stu-id="f55d6-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="f55d6-107">[in] Указатель на [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) объект, который был передан в качестве параметра [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f55d6-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f55d6-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f55d6-108">Return Value</span></span>  
  
|<span data-ttu-id="f55d6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f55d6-109">HRESULT</span></span>|<span data-ttu-id="f55d6-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f55d6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f55d6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f55d6-111">S_OK</span></span>|<span data-ttu-id="f55d6-112">`UnregisterActionOnEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f55d6-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f55d6-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f55d6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f55d6-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f55d6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f55d6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f55d6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f55d6-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f55d6-116">The call timed out.</span></span>|  
|<span data-ttu-id="f55d6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f55d6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f55d6-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f55d6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f55d6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f55d6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f55d6-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f55d6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f55d6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f55d6-121">E_FAIL</span></span>|<span data-ttu-id="f55d6-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="f55d6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f55d6-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f55d6-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f55d6-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f55d6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f55d6-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f55d6-125">Requirements</span></span>  
 <span data-ttu-id="f55d6-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f55d6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f55d6-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f55d6-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f55d6-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f55d6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f55d6-129">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f55d6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f55d6-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f55d6-130">See Also</span></span>  
 [<span data-ttu-id="f55d6-131">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="f55d6-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="f55d6-132">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="f55d6-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="f55d6-133">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f55d6-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f55d6-134">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="f55d6-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
