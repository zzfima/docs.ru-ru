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
ms.openlocfilehash: 54abd54662d4e99881dddf15876b596a4a705f70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638883"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="9af23-102">Метод ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="9af23-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="9af23-103">Отменяет регистрацию ранее зарегистрированного обратного вызова указатель для указанного события.</span><span class="sxs-lookup"><span data-stu-id="9af23-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9af23-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9af23-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9af23-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9af23-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="9af23-106">[in] Один из [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) значений, указывающее, события, для которого для отмены регистрации обратного вызова указатель, описываемого `pAction`.</span><span class="sxs-lookup"><span data-stu-id="9af23-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="9af23-107">[in] Указатель на [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) объект, который был передан в качестве параметра [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9af23-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9af23-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9af23-108">Return Value</span></span>  
  
|<span data-ttu-id="9af23-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9af23-109">HRESULT</span></span>|<span data-ttu-id="9af23-110">Описание</span><span class="sxs-lookup"><span data-stu-id="9af23-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9af23-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9af23-111">S_OK</span></span>|<span data-ttu-id="9af23-112">`UnregisterActionOnEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9af23-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="9af23-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9af23-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9af23-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9af23-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9af23-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9af23-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9af23-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9af23-116">The call timed out.</span></span>|  
|<span data-ttu-id="9af23-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9af23-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9af23-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9af23-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9af23-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9af23-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9af23-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9af23-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9af23-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9af23-121">E_FAIL</span></span>|<span data-ttu-id="9af23-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="9af23-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9af23-123">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="9af23-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9af23-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9af23-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9af23-125">Требования</span><span class="sxs-lookup"><span data-stu-id="9af23-125">Requirements</span></span>  
 <span data-ttu-id="9af23-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9af23-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9af23-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9af23-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9af23-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9af23-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9af23-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9af23-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af23-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9af23-130">See also</span></span>

- [<span data-ttu-id="9af23-131">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="9af23-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="9af23-132">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="9af23-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="9af23-133">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="9af23-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9af23-134">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="9af23-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
