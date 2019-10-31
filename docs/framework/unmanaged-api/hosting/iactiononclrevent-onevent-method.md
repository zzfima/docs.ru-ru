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
ms.openlocfilehash: 98807717fc913052dae15f9f3cbd462d4f537ad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126920"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="1302e-102">Метод IActionOnCLREvent::OnEvent</span><span class="sxs-lookup"><span data-stu-id="1302e-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="1302e-103">Выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1302e-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1302e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1302e-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1302e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1302e-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="1302e-106">окне Одно из значений [еклревент](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) , указывающее тип события.</span><span class="sxs-lookup"><span data-stu-id="1302e-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="1302e-107">окне Указатель на объект, содержащий сведения о `event`.</span><span class="sxs-lookup"><span data-stu-id="1302e-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1302e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1302e-108">Return Value</span></span>  
  
|<span data-ttu-id="1302e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1302e-109">HRESULT</span></span>|<span data-ttu-id="1302e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1302e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1302e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1302e-111">S_OK</span></span>|<span data-ttu-id="1302e-112">`OnEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1302e-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="1302e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1302e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1302e-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1302e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1302e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1302e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1302e-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1302e-116">The call timed out.</span></span>|  
|<span data-ttu-id="1302e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1302e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1302e-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1302e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1302e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1302e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1302e-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1302e-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1302e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1302e-121">E_FAIL</span></span>|<span data-ttu-id="1302e-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1302e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1302e-123">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1302e-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1302e-124">Последующие вызовы любого метода размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1302e-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1302e-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="1302e-125">Remarks</span></span>  
 <span data-ttu-id="1302e-126">Параметр `data` является указателем на объект неопределенного типа.</span><span class="sxs-lookup"><span data-stu-id="1302e-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="1302e-127">Если параметр `event` имеет значение `Event_DomainUnload`, `data` является числовым идентификатором для выгрузки <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1302e-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="1302e-128">Узел может предпринять соответствующие действия, используя этот идентификатор в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="1302e-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="1302e-129">Если `event` имеет `Event_MDAFired`, `data` является указателем на экземпляр [мдаинфо](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) , который содержит выходные данные сообщения от помощника по отладке управляемого кода (MDA).</span><span class="sxs-lookup"><span data-stu-id="1302e-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="1302e-130">MDA — это функция среды CLR, которая помогает разработчикам выполнять отладку путем создания сообщений XML о событиях, которые в противном случае сложны для перехвата.</span><span class="sxs-lookup"><span data-stu-id="1302e-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="1302e-131">Такие сообщения могут быть особенно полезны при отладке переходов между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="1302e-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="1302e-132">Дополнительные сведения см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.</span><span class="sxs-lookup"><span data-stu-id="1302e-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1302e-133">Требования</span><span class="sxs-lookup"><span data-stu-id="1302e-133">Requirements</span></span>  
 <span data-ttu-id="1302e-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1302e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1302e-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1302e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1302e-136">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1302e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1302e-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1302e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1302e-138">См. также</span><span class="sxs-lookup"><span data-stu-id="1302e-138">See also</span></span>

- [<span data-ttu-id="1302e-139">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="1302e-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="1302e-140">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="1302e-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="1302e-141">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="1302e-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="1302e-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="1302e-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1302e-143">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="1302e-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="1302e-144">Структура MDAInfo</span><span class="sxs-lookup"><span data-stu-id="1302e-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
