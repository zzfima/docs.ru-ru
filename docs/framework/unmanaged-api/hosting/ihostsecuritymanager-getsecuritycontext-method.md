---
title: Метод IHostSecurityManager::GetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f4f923e868b72e9de33884e4814ebfa329a16e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105837"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="c5c48-102">Метод IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c5c48-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="c5c48-103">Возвращает запрашиваемый [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) с узла.</span><span class="sxs-lookup"><span data-stu-id="c5c48-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5c48-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5c48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5c48-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="c5c48-106">[in] Один из [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , указывающее, какой тип контекста безопасности для возврата значений.</span><span class="sxs-lookup"><span data-stu-id="c5c48-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="c5c48-107">[out] Адрес указателя интерфейса `IHostSecurityContext` из `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="c5c48-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5c48-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c5c48-108">Return Value</span></span>  
  
|<span data-ttu-id="c5c48-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5c48-109">HRESULT</span></span>|<span data-ttu-id="c5c48-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c5c48-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5c48-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5c48-111">S_OK</span></span>|`GetSecurityContext` <span data-ttu-id="c5c48-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c5c48-112">returned successfully.</span></span>|  
|<span data-ttu-id="c5c48-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5c48-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5c48-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c5c48-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5c48-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5c48-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5c48-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c5c48-116">The call timed out.</span></span>|  
|<span data-ttu-id="c5c48-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5c48-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5c48-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c5c48-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5c48-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5c48-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5c48-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c5c48-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5c48-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5c48-121">E_FAIL</span></span>|<span data-ttu-id="c5c48-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c5c48-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5c48-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c5c48-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5c48-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c5c48-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5c48-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5c48-125">Remarks</span></span>  
 <span data-ttu-id="c5c48-126">Управляющее приложение может определять все доступ кода к маркерам потока кодом среды CLR и пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5c48-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="c5c48-127">Также можно обеспечить, полную безопасность сведений о контексте передается через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="c5c48-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> `IHostSecurityContext` <span data-ttu-id="c5c48-128">инкапсулирует эти сведения о контексте безопасности, который является непрозрачным для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c5c48-128">encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="c5c48-129">Среда CLR позволяет получить эти сведения и перемещает ее через поток пула рабочих элементов диспетчеризации, выполнения метода завершения и конструирование модулей и классов.</span><span class="sxs-lookup"><span data-stu-id="c5c48-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5c48-130">Требования</span><span class="sxs-lookup"><span data-stu-id="c5c48-130">Requirements</span></span>  
 <span data-ttu-id="c5c48-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5c48-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5c48-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5c48-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5c48-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5c48-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c5c48-134">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c5c48-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5c48-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c5c48-135">See also</span></span>

- [<span data-ttu-id="c5c48-136">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="c5c48-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="c5c48-137">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c5c48-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c5c48-138">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c5c48-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
