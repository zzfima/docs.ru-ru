---
title: Метод ICLROnEventManager::RegisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68a8493a9eb5177844e81ef7a9612f979ffe89c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216500"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="220bc-102">Метод ICLROnEventManager::RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="220bc-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="220bc-103">Регистрирует обратный вызов указатель для указанного события.</span><span class="sxs-lookup"><span data-stu-id="220bc-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="220bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="220bc-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="220bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="220bc-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="220bc-106">[in] Один из [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) значений, указывающее, событий, для которого необходимо зарегистрировать обратный вызов указателя, описываемого `pAction`.</span><span class="sxs-lookup"><span data-stu-id="220bc-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="220bc-107">[in] Указатель на [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) объект, который вызывается при возникновении зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="220bc-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="220bc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="220bc-108">Return Value</span></span>  
  
|<span data-ttu-id="220bc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="220bc-109">HRESULT</span></span>|<span data-ttu-id="220bc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="220bc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="220bc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="220bc-111">S_OK</span></span>|`RegisterActionOnEvent` <span data-ttu-id="220bc-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="220bc-112">returned successfully.</span></span>|  
|<span data-ttu-id="220bc-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="220bc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="220bc-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="220bc-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="220bc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="220bc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="220bc-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="220bc-116">The call timed out.</span></span>|  
|<span data-ttu-id="220bc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="220bc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="220bc-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="220bc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="220bc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="220bc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="220bc-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="220bc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="220bc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="220bc-121">E_FAIL</span></span>|<span data-ttu-id="220bc-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="220bc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="220bc-123">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="220bc-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="220bc-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="220bc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="220bc-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="220bc-125">Remarks</span></span>  
 <span data-ttu-id="220bc-126">Узел может регистрировать обратные вызовы для одного или обоих типов событий, описываемого `EClrEvent`.</span><span class="sxs-lookup"><span data-stu-id="220bc-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="220bc-127">Получает узел `ICLROnEventManager` интерфейс путем вызова [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="220bc-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="220bc-128">События, `RegisterActionOnEvent` регистры, которые можно вызывать несколько раз и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.</span><span class="sxs-lookup"><span data-stu-id="220bc-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="220bc-129">Требования</span><span class="sxs-lookup"><span data-stu-id="220bc-129">Requirements</span></span>  
 <span data-ttu-id="220bc-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="220bc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="220bc-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="220bc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="220bc-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="220bc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="220bc-133">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="220bc-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="220bc-134">См. также</span><span class="sxs-lookup"><span data-stu-id="220bc-134">See also</span></span>

- [<span data-ttu-id="220bc-135">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="220bc-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="220bc-136">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="220bc-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="220bc-137">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="220bc-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="220bc-138">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="220bc-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
