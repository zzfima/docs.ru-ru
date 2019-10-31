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
ms.openlocfilehash: 0f952978a2591c82b2ad3f5059070124b7873c94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140824"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="fc65b-102">Метод ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="fc65b-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="fc65b-103">Отменяет регистрацию ранее зарегистрированного указателя обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="fc65b-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc65b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc65b-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc65b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc65b-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="fc65b-106">окне Одно из значений [еклревент](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) , указывающее событие, для которого необходимо отменить регистрацию указателя обратного вызова, описанного в `pAction`.</span><span class="sxs-lookup"><span data-stu-id="fc65b-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="fc65b-107">окне Указатель на объект [иактиононклревент](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) , переданный в качестве параметра в метод [регистерактиононевент](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fc65b-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc65b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc65b-108">Return Value</span></span>  
  
|<span data-ttu-id="fc65b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc65b-109">HRESULT</span></span>|<span data-ttu-id="fc65b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fc65b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc65b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc65b-111">S_OK</span></span>|<span data-ttu-id="fc65b-112">`UnregisterActionOnEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fc65b-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="fc65b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc65b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc65b-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fc65b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc65b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc65b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc65b-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fc65b-116">The call timed out.</span></span>|  
|<span data-ttu-id="fc65b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc65b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc65b-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fc65b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc65b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc65b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc65b-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fc65b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc65b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc65b-121">E_FAIL</span></span>|<span data-ttu-id="fc65b-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fc65b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc65b-123">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fc65b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc65b-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fc65b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc65b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="fc65b-125">Requirements</span></span>  
 <span data-ttu-id="fc65b-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc65b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc65b-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc65b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc65b-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fc65b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc65b-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc65b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc65b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="fc65b-130">See also</span></span>

- [<span data-ttu-id="fc65b-131">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="fc65b-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="fc65b-132">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="fc65b-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="fc65b-133">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="fc65b-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="fc65b-134">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="fc65b-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
