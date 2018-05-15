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
ms.openlocfilehash: aff8fa88fe811d5a07ea8ffb1653e403338ba546
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="0d888-102">Метод IHostSecurityContext::Capture</span><span class="sxs-lookup"><span data-stu-id="0d888-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="0d888-103">Возвращает точную копию [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) экземпляр возвращен из вызова [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="0d888-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d888-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d888-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d888-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d888-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="0d888-106">[out] Указатель на адрес клон `IHostSecurityContext` объектов для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0d888-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d888-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d888-107">Return Value</span></span>  
  
|<span data-ttu-id="0d888-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d888-108">HRESULT</span></span>|<span data-ttu-id="0d888-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0d888-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d888-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d888-110">S_OK</span></span>|<span data-ttu-id="0d888-111">`Capture` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0d888-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="0d888-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d888-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d888-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0d888-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d888-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d888-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d888-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0d888-115">The call timed out.</span></span>|  
|<span data-ttu-id="0d888-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d888-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d888-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0d888-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d888-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d888-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d888-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0d888-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d888-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d888-120">E_FAIL</span></span>|<span data-ttu-id="0d888-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0d888-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d888-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0d888-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d888-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0d888-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d888-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d888-124">Remarks</span></span>  
 <span data-ttu-id="0d888-125">Указатель интерфейса, возвращенный из `Capture` является клоном перехваченного контекста.</span><span class="sxs-lookup"><span data-stu-id="0d888-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="0d888-126">При перемещении этих сведений по асинхронным точкам кода время существования отделяется от, указатель, по которой был выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="0d888-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="0d888-127">Таким образом могут быть сняты исходный указатель.</span><span class="sxs-lookup"><span data-stu-id="0d888-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d888-128">Требования</span><span class="sxs-lookup"><span data-stu-id="0d888-128">Requirements</span></span>  
 <span data-ttu-id="0d888-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d888-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d888-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d888-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d888-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d888-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d888-132">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d888-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d888-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0d888-133">See Also</span></span>  
 [<span data-ttu-id="0d888-134">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="0d888-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="0d888-135">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="0d888-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
