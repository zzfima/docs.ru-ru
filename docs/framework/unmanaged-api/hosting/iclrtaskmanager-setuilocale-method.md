---
title: "Метод ICLRTaskManager::SetUILocale"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28ecba8b88ceadaf743f5c65bc6f257f7ef8cd60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="9f74f-102">Метод ICLRTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="9f74f-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="9f74f-103">Уведомляет общеязыковой среды выполнения (CLR), что узел изменил язык пользовательского интерфейса пользователя, или язык и региональные параметры, в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="9f74f-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f74f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f74f-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f74f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f74f-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="9f74f-106">[in] Значение идентификатора языкового стандарта, сопоставленное с только что назначенного региональные параметры и язык интерфейса пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f74f-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f74f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9f74f-107">Return Value</span></span>  
  
|<span data-ttu-id="9f74f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f74f-108">HRESULT</span></span>|<span data-ttu-id="9f74f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9f74f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f74f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f74f-110">S_OK</span></span>|<span data-ttu-id="9f74f-111">`SetUILocale`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9f74f-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="9f74f-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f74f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f74f-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9f74f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f74f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f74f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f74f-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9f74f-115">The call timed out.</span></span>|  
|<span data-ttu-id="9f74f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f74f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f74f-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9f74f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f74f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f74f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f74f-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9f74f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f74f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f74f-120">E_FAIL</span></span>|<span data-ttu-id="9f74f-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="9f74f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f74f-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9f74f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f74f-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9f74f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f74f-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f74f-124">Remarks</span></span>  
 <span data-ttu-id="9f74f-125">`SetUILocale`дает возможность для узла выполнить какие-либо у него механизмы для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="9f74f-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f74f-126">Требования</span><span class="sxs-lookup"><span data-stu-id="9f74f-126">Requirements</span></span>  
 <span data-ttu-id="9f74f-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f74f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f74f-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f74f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f74f-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f74f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f74f-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f74f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f74f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9f74f-131">See Also</span></span>  
 [<span data-ttu-id="9f74f-132">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9f74f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9f74f-133">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9f74f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9f74f-134">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9f74f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9f74f-135">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9f74f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
