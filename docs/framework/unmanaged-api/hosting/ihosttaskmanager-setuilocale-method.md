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
ms.openlocfilehash: a929a125fc8c70744246f4f96d8a09a4605f537c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132947"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="83173-102">Метод IHostTaskManager::SetUILocale</span><span class="sxs-lookup"><span data-stu-id="83173-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="83173-103">Уведомляет основное приложение о том, что среда CLR изменила языковой стандарт пользовательского интерфейса (UI), или язык и региональные параметры, в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="83173-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83173-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83173-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83173-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83173-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="83173-106">окне Значение идентификатора локали, сопоставляемое с новым назначенным географическим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="83173-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83173-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83173-107">Return Value</span></span>  
  
|<span data-ttu-id="83173-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83173-108">HRESULT</span></span>|<span data-ttu-id="83173-109">Описание</span><span class="sxs-lookup"><span data-stu-id="83173-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83173-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="83173-110">S_OK</span></span>|<span data-ttu-id="83173-111">`SetUILocale` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="83173-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="83173-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83173-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83173-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="83173-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83173-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83173-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83173-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="83173-115">The call timed out.</span></span>|  
|<span data-ttu-id="83173-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83173-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83173-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="83173-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83173-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83173-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83173-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="83173-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83173-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83173-120">E_FAIL</span></span>|<span data-ttu-id="83173-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="83173-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83173-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="83173-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83173-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="83173-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="83173-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="83173-124">E_NOTIMPL</span></span>|<span data-ttu-id="83173-125">Узел не позволяет управляемому пользовательскому коду изменять язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="83173-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83173-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="83173-126">Remarks</span></span>  
 <span data-ttu-id="83173-127">Среда выполнения вызывает `SetUILocale`, когда значение свойства <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> изменяется управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="83173-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="83173-128">Этот метод предоставляет узлу возможность выполнять любые механизмы, которые могут потребоваться для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="83173-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="83173-129">Если узел не позволяет изменять языковой стандарт пользовательского интерфейса из управляемого кода или не реализует механизм для синхронизации языковых стандартов, он должен возвратить значение E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="83173-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83173-130">Требования</span><span class="sxs-lookup"><span data-stu-id="83173-130">Requirements</span></span>  
 <span data-ttu-id="83173-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83173-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83173-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="83173-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83173-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83173-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83173-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83173-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83173-135">См. также</span><span class="sxs-lookup"><span data-stu-id="83173-135">See also</span></span>

- [<span data-ttu-id="83173-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="83173-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="83173-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="83173-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="83173-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="83173-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="83173-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="83173-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="83173-140">Метод SetLocale</span><span class="sxs-lookup"><span data-stu-id="83173-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
