---
title: "Метод IHostSecurityManager::GetSecurityContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.GetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b150700c50842791a2413688583e7e1289852d62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="8104b-102">Метод IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="8104b-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="8104b-103">Возвращает запрошенный [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) хоста.</span><span class="sxs-lookup"><span data-stu-id="8104b-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8104b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8104b-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8104b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8104b-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="8104b-106">[in] Один из [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , указывающее, какой тип контекста безопасности для возврата значений.</span><span class="sxs-lookup"><span data-stu-id="8104b-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="8104b-107">[out] Адрес указателя интерфейса `IHostSecurityContext` из `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="8104b-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8104b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8104b-108">Return Value</span></span>  
  
|<span data-ttu-id="8104b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8104b-109">HRESULT</span></span>|<span data-ttu-id="8104b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8104b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8104b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8104b-111">S_OK</span></span>|<span data-ttu-id="8104b-112">`GetSecurityContext`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8104b-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="8104b-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8104b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8104b-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8104b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8104b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8104b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8104b-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8104b-116">The call timed out.</span></span>|  
|<span data-ttu-id="8104b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8104b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8104b-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8104b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8104b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8104b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8104b-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8104b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8104b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8104b-121">E_FAIL</span></span>|<span data-ttu-id="8104b-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8104b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8104b-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8104b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8104b-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8104b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8104b-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="8104b-125">Remarks</span></span>  
 <span data-ttu-id="8104b-126">Узел может управлять доступом кода к маркерам потока из кода среды CLR и пользователя.</span><span class="sxs-lookup"><span data-stu-id="8104b-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="8104b-127">Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="8104b-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="8104b-128">`IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8104b-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="8104b-129">Среда CLR перехватывает эту информацию и перемещает ее через операции подготовки к отправке элемента рабочего пула потоков, выполнения метода завершения и конструирование модулей и классов.</span><span class="sxs-lookup"><span data-stu-id="8104b-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8104b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="8104b-130">Requirements</span></span>  
 <span data-ttu-id="8104b-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8104b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8104b-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8104b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8104b-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8104b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8104b-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8104b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8104b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8104b-135">See Also</span></span>  
 [<span data-ttu-id="8104b-136">Econtexttype-перечисление</span><span class="sxs-lookup"><span data-stu-id="8104b-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="8104b-137">IHostSecurityContext-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8104b-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="8104b-138">IHostSecurityManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8104b-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
