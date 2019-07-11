---
title: Метод IHostTaskManager::SetLocale
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f388a52c320c3f0d5f4ad7e073e1e8960d7947dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749368"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="fd0ef-102">Метод IHostTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="fd0ef-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="fd0ef-103">Уведомляет ведущее приложение об изменении общеязыковой среды выполнения (CLR) языкового стандарта или языка и региональных параметров, в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd0ef-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd0ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd0ef-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="fd0ef-106">[in] Значения идентификатора языкового стандарта, сопоставляется только что назначенного географических языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd0ef-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd0ef-107">Return Value</span></span>  
  
|<span data-ttu-id="fd0ef-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd0ef-108">HRESULT</span></span>|<span data-ttu-id="fd0ef-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fd0ef-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd0ef-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd0ef-110">S_OK</span></span>|<span data-ttu-id="fd0ef-111">`SetLocale` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="fd0ef-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd0ef-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd0ef-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd0ef-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd0ef-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd0ef-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd0ef-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd0ef-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd0ef-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd0ef-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd0ef-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd0ef-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd0ef-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd0ef-120">E_FAIL</span></span>|<span data-ttu-id="fd0ef-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd0ef-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd0ef-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd0ef-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fd0ef-124">E_NOTIMPL</span></span>|<span data-ttu-id="fd0ef-125">Узел не поддерживает управляемый пользовательский код для изменения языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0ef-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd0ef-126">Remarks</span></span>  
 <span data-ttu-id="fd0ef-127">Среда выполнения вызывает `SetLocale` при значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> в управляемом коде изменяется свойство.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="fd0ef-128">Этот метод предоставляет возможность для узла выполнить какие-либо механизмы, которые он может иметь для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="fd0ef-129">Если узел не поддерживает языковой стандарт, изменить из управляемого кода или не реализует механизм синхронизации языковых стандартов, она должна возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="fd0ef-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd0ef-130">Требования</span><span class="sxs-lookup"><span data-stu-id="fd0ef-130">Requirements</span></span>  
 <span data-ttu-id="fd0ef-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd0ef-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd0ef-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd0ef-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd0ef-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd0ef-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd0ef-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd0ef-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0ef-135">См. также</span><span class="sxs-lookup"><span data-stu-id="fd0ef-135">See also</span></span>

- [<span data-ttu-id="fd0ef-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="fd0ef-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fd0ef-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fd0ef-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fd0ef-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="fd0ef-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fd0ef-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fd0ef-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="fd0ef-140">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="fd0ef-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
