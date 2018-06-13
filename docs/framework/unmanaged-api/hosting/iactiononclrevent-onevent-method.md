---
title: Метод IActionOnCLREvent::OnEvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28178cca27c257e480a7c5ec87c1925af7de4f78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436420"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="c5c02-102">Метод IActionOnCLREvent::OnEvent</span><span class="sxs-lookup"><span data-stu-id="c5c02-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="c5c02-103">Выполняет обратные вызовы для событий, которые были зарегистрированы с помощью вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c5c02-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5c02-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5c02-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5c02-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="c5c02-106">[in] Один из [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) значения, которые указывает тип события.</span><span class="sxs-lookup"><span data-stu-id="c5c02-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="c5c02-107">[in] Указатель на объект, содержащий сведения о `event`.</span><span class="sxs-lookup"><span data-stu-id="c5c02-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5c02-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c5c02-108">Return Value</span></span>  
  
|<span data-ttu-id="c5c02-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5c02-109">HRESULT</span></span>|<span data-ttu-id="c5c02-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c5c02-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5c02-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5c02-111">S_OK</span></span>|<span data-ttu-id="c5c02-112">`OnEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c5c02-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c5c02-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5c02-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5c02-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c5c02-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5c02-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5c02-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5c02-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c5c02-116">The call timed out.</span></span>|  
|<span data-ttu-id="c5c02-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5c02-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5c02-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c5c02-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5c02-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5c02-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5c02-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c5c02-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5c02-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5c02-121">E_FAIL</span></span>|<span data-ttu-id="c5c02-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c5c02-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5c02-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c5c02-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5c02-124">Последующие вызовы любой метод размещения возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c5c02-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5c02-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5c02-125">Remarks</span></span>  
 <span data-ttu-id="c5c02-126">`data` Параметр является указателем на объект незаданного типа.</span><span class="sxs-lookup"><span data-stu-id="c5c02-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="c5c02-127">Если `event` параметр `Event_DomainUnload`, `data` числовой идентификатор <xref:System.AppDomain> , был выгружен.</span><span class="sxs-lookup"><span data-stu-id="c5c02-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="c5c02-128">Узел может предпринять соответствующее действие, используя этот идентификатор в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="c5c02-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="c5c02-129">Если `event` — `Event_MDAFired`, `data` — это указатель на [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) экземпляру, содержащему вывод сообщений из управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="c5c02-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="c5c02-130">MDA — это функция среды CLR, которая помогает разработчикам при отладке, создавая XML-сообщения о событиях, которые в противном случае сложно для перехвата исключения.</span><span class="sxs-lookup"><span data-stu-id="c5c02-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="c5c02-131">Такие сообщения могут быть особенно полезен при отладке переходы между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="c5c02-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="c5c02-132">Дополнительные сведения см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="c5c02-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5c02-133">Требования</span><span class="sxs-lookup"><span data-stu-id="c5c02-133">Requirements</span></span>  
 <span data-ttu-id="c5c02-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5c02-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5c02-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5c02-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5c02-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5c02-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5c02-137">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5c02-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c02-138">См. также</span><span class="sxs-lookup"><span data-stu-id="c5c02-138">See Also</span></span>  
 [<span data-ttu-id="c5c02-139">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="c5c02-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="c5c02-140">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="c5c02-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="c5c02-141">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="c5c02-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="c5c02-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c5c02-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="c5c02-143">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="c5c02-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="c5c02-144">Структура MDAInfo</span><span class="sxs-lookup"><span data-stu-id="c5c02-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
