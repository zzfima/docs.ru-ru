---
title: "Метод IHostTaskManager::SetLocale"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eeb5e7510c6de882233ec1fa8fa1b8f501a00685
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="b035b-102">Метод IHostTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="b035b-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="b035b-103">Уведомляет основное приложение об изменении общеязыковой среды выполнения (CLR) языкового стандарта или языка и региональных параметров в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="b035b-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b035b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b035b-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b035b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b035b-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="b035b-106">[in] Значение идентификатора языкового стандарта, сопоставленное с только что назначенного региональные параметры и язык.</span><span class="sxs-lookup"><span data-stu-id="b035b-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b035b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b035b-107">Return Value</span></span>  
  
|<span data-ttu-id="b035b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b035b-108">HRESULT</span></span>|<span data-ttu-id="b035b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b035b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b035b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b035b-110">S_OK</span></span>|<span data-ttu-id="b035b-111">`SetLocale`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b035b-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="b035b-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b035b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b035b-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b035b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b035b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b035b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b035b-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b035b-115">The call timed out.</span></span>|  
|<span data-ttu-id="b035b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b035b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b035b-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b035b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b035b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b035b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b035b-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b035b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b035b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b035b-120">E_FAIL</span></span>|<span data-ttu-id="b035b-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="b035b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b035b-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b035b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b035b-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b035b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b035b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b035b-124">E_NOTIMPL</span></span>|<span data-ttu-id="b035b-125">Основное приложение не позволяет управляемому пользовательскому коду менять языковой стандарт.</span><span class="sxs-lookup"><span data-stu-id="b035b-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b035b-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="b035b-126">Remarks</span></span>  
 <span data-ttu-id="b035b-127">Среда выполнения вызывает метод `SetLocale` при значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> свойство изменяется в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="b035b-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="b035b-128">Этот метод дает возможность для узла выполнить какие-либо у него механизмы для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="b035b-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="b035b-129">Если узел не допускает языковой стандарт должен быть изменен из управляемого кода или не реализует механизм для синхронизации языковых стандартов, оно должно возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="b035b-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b035b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="b035b-130">Requirements</span></span>  
 <span data-ttu-id="b035b-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b035b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b035b-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b035b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b035b-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b035b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b035b-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b035b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b035b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b035b-135">See Also</span></span>  
 [<span data-ttu-id="b035b-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b035b-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b035b-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b035b-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="b035b-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b035b-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b035b-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b035b-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="b035b-140">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="b035b-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
