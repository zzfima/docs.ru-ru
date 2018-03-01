---
title: "Метод ICLRTaskManager::SetLocale"
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
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bbed6bff52d7ccad38eb45d12a31d08dc8b1b774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="b640a-102">Метод ICLRTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="b640a-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="b640a-103">Уведомляет общеязыковой среды выполнения (CLR), что узел изменил значение идентификатора языкового стандарта (который сопоставляет региональные параметры и язык) в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="b640a-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b640a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b640a-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b640a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b640a-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="b640a-106">[in] Значение идентификатора языкового стандарта, сопоставленное с только что назначенного региональные параметры и язык.</span><span class="sxs-lookup"><span data-stu-id="b640a-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b640a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b640a-107">Return Value</span></span>  
  
|<span data-ttu-id="b640a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b640a-108">HRESULT</span></span>|<span data-ttu-id="b640a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b640a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b640a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b640a-110">S_OK</span></span>|<span data-ttu-id="b640a-111">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="b640a-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b640a-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b640a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b640a-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b640a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b640a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b640a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b640a-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b640a-115">The call timed out.</span></span>|  
|<span data-ttu-id="b640a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b640a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b640a-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b640a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b640a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b640a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b640a-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b640a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b640a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b640a-120">E_FAIL</span></span>|<span data-ttu-id="b640a-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="b640a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b640a-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b640a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b640a-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b640a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b640a-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="b640a-124">Remarks</span></span>  
 <span data-ttu-id="b640a-125">`SetLocale`дает возможность выполнять какие-либо у него механизмы для синхронизации языковых стандартов для узла.</span><span class="sxs-lookup"><span data-stu-id="b640a-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b640a-126">Требования</span><span class="sxs-lookup"><span data-stu-id="b640a-126">Requirements</span></span>  
 <span data-ttu-id="b640a-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b640a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b640a-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b640a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b640a-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b640a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b640a-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b640a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b640a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b640a-131">See Also</span></span>  
 [<span data-ttu-id="b640a-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b640a-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b640a-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b640a-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="b640a-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b640a-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b640a-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b640a-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
