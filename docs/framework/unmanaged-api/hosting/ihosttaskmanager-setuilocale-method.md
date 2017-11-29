---
title: "Метод IHostTaskManager::SetUILocale"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c29687d430187577ac25d8d2a007785632989ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="5d0b8-102">Метод IHostTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="5d0b8-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="5d0b8-103">Уведомляет основное приложение об изменении общеязыковой среды выполнения (CLR) язык пользовательского интерфейса пользователя или языка и региональных параметров в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d0b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d0b8-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d0b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d0b8-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="5d0b8-106">[in] Значение идентификатора языкового стандарта, сопоставленное с только что назначенного региональные параметры и язык.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d0b8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d0b8-107">Return Value</span></span>  
  
|<span data-ttu-id="5d0b8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d0b8-108">HRESULT</span></span>|<span data-ttu-id="5d0b8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5d0b8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d0b8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d0b8-110">S_OK</span></span>|<span data-ttu-id="5d0b8-111">`SetUILocale`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="5d0b8-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d0b8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d0b8-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d0b8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d0b8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d0b8-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-115">The call timed out.</span></span>|  
|<span data-ttu-id="5d0b8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d0b8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d0b8-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d0b8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d0b8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d0b8-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d0b8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d0b8-120">E_FAIL</span></span>|<span data-ttu-id="5d0b8-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d0b8-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d0b8-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5d0b8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5d0b8-124">E_NOTIMPL</span></span>|<span data-ttu-id="5d0b8-125">Основное приложение не позволяет управляемый пользовательский код, чтобы изменить язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d0b8-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d0b8-126">Remarks</span></span>  
 <span data-ttu-id="5d0b8-127">Среда выполнения вызывает метод `SetUILocale` при значение <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> свойство изменяется в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="5d0b8-128">Этот метод дает возможность для узла выполнить какие-либо у него механизмы для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="5d0b8-129">Если узел не допускает языка пользовательского интерфейса должен быть изменен из управляемого кода или не реализует механизм для синхронизации языковых стандартов, оно должно возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="5d0b8-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d0b8-130">Требования</span><span class="sxs-lookup"><span data-stu-id="5d0b8-130">Requirements</span></span>  
 <span data-ttu-id="5d0b8-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d0b8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d0b8-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d0b8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d0b8-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d0b8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d0b8-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d0b8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0b8-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5d0b8-135">See Also</span></span>  
 [<span data-ttu-id="5d0b8-136">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5d0b8-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5d0b8-137">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5d0b8-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5d0b8-138">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5d0b8-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5d0b8-139">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5d0b8-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="5d0b8-140">SetLocale-метод</span><span class="sxs-lookup"><span data-stu-id="5d0b8-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
