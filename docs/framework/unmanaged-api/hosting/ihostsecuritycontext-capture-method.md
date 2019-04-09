---
title: Метод IHostSecurityContext::Capture
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0f6ae812b64080a2c4d236a2be02ad81c4a11b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193308"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="4304b-102">Метод IHostSecurityContext::Capture</span><span class="sxs-lookup"><span data-stu-id="4304b-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="4304b-103">Возвращает точную копию [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) экземпляр, возвращаемый из вызова [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="4304b-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4304b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4304b-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4304b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4304b-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="4304b-106">[out] Указатель на адрес клон `IHostSecurityContext` объекта, которые должны отслеживаться.</span><span class="sxs-lookup"><span data-stu-id="4304b-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4304b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4304b-107">Return Value</span></span>  
  
|<span data-ttu-id="4304b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4304b-108">HRESULT</span></span>|<span data-ttu-id="4304b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4304b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4304b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4304b-110">S_OK</span></span>|`Capture` <span data-ttu-id="4304b-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4304b-111">returned successfully.</span></span>|  
|<span data-ttu-id="4304b-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4304b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4304b-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4304b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4304b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4304b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4304b-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4304b-115">The call timed out.</span></span>|  
|<span data-ttu-id="4304b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4304b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4304b-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4304b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4304b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4304b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4304b-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4304b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4304b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4304b-120">E_FAIL</span></span>|<span data-ttu-id="4304b-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="4304b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4304b-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4304b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4304b-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4304b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4304b-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="4304b-124">Remarks</span></span>  
 <span data-ttu-id="4304b-125">Указатель интерфейса, возвращенный из `Capture` является клоном захваченном контексте.</span><span class="sxs-lookup"><span data-stu-id="4304b-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="4304b-126">Эти сведения при перемещении между точкой асинхронного кода, его времени существования, отделен от, для которого был выполнен вызов указателя.</span><span class="sxs-lookup"><span data-stu-id="4304b-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="4304b-127">Исходный указатель таким образом могут быть сняты.</span><span class="sxs-lookup"><span data-stu-id="4304b-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4304b-128">Требования</span><span class="sxs-lookup"><span data-stu-id="4304b-128">Requirements</span></span>  
 <span data-ttu-id="4304b-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4304b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4304b-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4304b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4304b-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4304b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4304b-132">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4304b-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4304b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4304b-133">See also</span></span>

- [<span data-ttu-id="4304b-134">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="4304b-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4304b-135">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="4304b-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
