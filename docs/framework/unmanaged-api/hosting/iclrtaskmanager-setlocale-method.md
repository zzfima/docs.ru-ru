---
title: Метод ICLRTaskManager::SetLocale
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad9e07e76d39ce25dc339eb5fb02635866966093
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612129"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="50af5-102">Метод ICLRTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="50af5-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="50af5-103">Уведомляет общеязыковой среды выполнения (CLR) о том, что узел изменил значение идентификатора языкового стандарта (который сопоставляется с региональные параметры и язык) в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="50af5-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50af5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50af5-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50af5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50af5-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="50af5-106">[in] Значения идентификатора языкового стандарта, сопоставляется только что назначенного географических языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="50af5-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50af5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="50af5-107">Return Value</span></span>  
  
|<span data-ttu-id="50af5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50af5-108">HRESULT</span></span>|<span data-ttu-id="50af5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="50af5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50af5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50af5-110">S_OK</span></span>|<span data-ttu-id="50af5-111">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="50af5-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="50af5-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50af5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50af5-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="50af5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50af5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50af5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50af5-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="50af5-115">The call timed out.</span></span>|  
|<span data-ttu-id="50af5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50af5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50af5-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="50af5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50af5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50af5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50af5-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="50af5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50af5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50af5-120">E_FAIL</span></span>|<span data-ttu-id="50af5-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="50af5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50af5-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="50af5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50af5-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50af5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50af5-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="50af5-124">Remarks</span></span>  
 <span data-ttu-id="50af5-125">`SetLocale` предоставляет узлу возможность выполнить какие-либо механизмы, которые он может иметь для синхронизации языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="50af5-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50af5-126">Требования</span><span class="sxs-lookup"><span data-stu-id="50af5-126">Requirements</span></span>  
 <span data-ttu-id="50af5-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50af5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50af5-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50af5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50af5-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50af5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50af5-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50af5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50af5-131">См. также</span><span class="sxs-lookup"><span data-stu-id="50af5-131">See also</span></span>
- [<span data-ttu-id="50af5-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="50af5-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="50af5-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="50af5-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="50af5-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="50af5-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="50af5-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="50af5-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
