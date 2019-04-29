---
title: Метод ICLRRuntimeHost::SetHostControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6817a2154e876dfa83540e3496f42acdcdb25a83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771823"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="a0178-102">Метод ICLRRuntimeHost::SetHostControl</span><span class="sxs-lookup"><span data-stu-id="a0178-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="a0178-103">Задает указатель интерфейса, среда CLR (CLR) можно использовать для получения от реализации узлом [интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a0178-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0178-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0178-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0178-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0178-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="a0178-106">[in] Указатель интерфейса на реализации [интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a0178-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0178-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0178-107">Return Value</span></span>  
  
|<span data-ttu-id="a0178-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0178-108">HRESULT</span></span>|<span data-ttu-id="a0178-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a0178-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0178-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0178-110">S_OK</span></span>|<span data-ttu-id="a0178-111">`SetHostControl` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a0178-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="a0178-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0178-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0178-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a0178-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0178-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0178-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0178-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a0178-115">The call timed out.</span></span>|  
|<span data-ttu-id="a0178-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0178-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0178-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a0178-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0178-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0178-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0178-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a0178-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0178-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0178-120">E_FAIL</span></span>|<span data-ttu-id="a0178-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a0178-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0178-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a0178-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0178-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0178-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0178-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="a0178-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="a0178-125">Среда CLR инициализирована.</span><span class="sxs-lookup"><span data-stu-id="a0178-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0178-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0178-126">Remarks</span></span>  
 <span data-ttu-id="a0178-127">Необходимо вызвать `SetHostControl` до инициализации среды CLR, то есть перед вызовом метода [метод Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) или использовать любой из [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="a0178-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="a0178-128">Рекомендуется вызывать `SetHostControl` сразу после вызова [функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) или [функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="a0178-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0178-129">Требования</span><span class="sxs-lookup"><span data-stu-id="a0178-129">Requirements</span></span>  
 <span data-ttu-id="a0178-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0178-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0178-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0178-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0178-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0178-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0178-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0178-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0178-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a0178-134">See also</span></span>

- [<span data-ttu-id="a0178-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a0178-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="a0178-136">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="a0178-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
