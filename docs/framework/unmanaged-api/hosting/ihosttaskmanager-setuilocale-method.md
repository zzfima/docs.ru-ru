---
title: Метод IHostTaskManager::SetUILocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a263410e898ee5805ce2a3dc9d534c25f6b9106
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496157"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="2ed12-102">Метод IHostTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="2ed12-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="2ed12-103">Уведомляет ведущее приложение об изменении общеязыковой среды выполнения (CLR) национальной настройки пользовательского интерфейса пользователя, то есть язык и региональные параметры, в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="2ed12-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ed12-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ed12-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ed12-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="2ed12-106">[in] Значения идентификатора языкового стандарта, сопоставляется только что назначенного географических языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="2ed12-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ed12-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2ed12-107">Return Value</span></span>  
  
|<span data-ttu-id="2ed12-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ed12-108">HRESULT</span></span>|<span data-ttu-id="2ed12-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2ed12-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ed12-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ed12-110">S_OK</span></span>|<span data-ttu-id="2ed12-111">`SetUILocale` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2ed12-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="2ed12-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ed12-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ed12-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2ed12-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ed12-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ed12-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ed12-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2ed12-115">The call timed out.</span></span>|  
|<span data-ttu-id="2ed12-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ed12-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ed12-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2ed12-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ed12-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ed12-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ed12-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2ed12-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ed12-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ed12-120">E_FAIL</span></span>|<span data-ttu-id="2ed12-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="2ed12-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ed12-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2ed12-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ed12-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2ed12-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2ed12-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2ed12-124">E_NOTIMPL</span></span>|<span data-ttu-id="2ed12-125">Узел не поддерживает управляемый пользовательский код, чтобы изменить язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2ed12-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ed12-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ed12-126">Remarks</span></span>  
 <span data-ttu-id="2ed12-127">Среда выполнения вызывает `SetUILocale` при значение <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> в управляемом коде изменяется свойство.</span><span class="sxs-lookup"><span data-stu-id="2ed12-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="2ed12-128">Этот метод предоставляет возможность для узла выполнить какие-либо механизмы, которые он может иметь для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="2ed12-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="2ed12-129">Если узел не поддерживает языковой стандарт пользовательского интерфейса, изменить из управляемого кода или не реализует механизм синхронизации языковых стандартов, она должна возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="2ed12-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed12-130">Требования</span><span class="sxs-lookup"><span data-stu-id="2ed12-130">Requirements</span></span>  
 <span data-ttu-id="2ed12-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ed12-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed12-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ed12-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ed12-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ed12-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ed12-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ed12-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed12-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2ed12-135">See also</span></span>
- [<span data-ttu-id="2ed12-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2ed12-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2ed12-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2ed12-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2ed12-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="2ed12-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2ed12-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2ed12-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="2ed12-140">Метод SetLocale</span><span class="sxs-lookup"><span data-stu-id="2ed12-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
