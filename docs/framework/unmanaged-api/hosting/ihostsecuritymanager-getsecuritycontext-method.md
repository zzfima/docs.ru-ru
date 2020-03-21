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
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176257"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="68e94-102">Метод IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="68e94-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="68e94-103">Получает запрошенный [IHostSecurityКонтекст](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) от хоста.</span><span class="sxs-lookup"><span data-stu-id="68e94-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68e94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68e94-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68e94-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68e94-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="68e94-106">(в) Одно из значений [EContextType,](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) указывающее, какой тип контекста безопасности вернуть.</span><span class="sxs-lookup"><span data-stu-id="68e94-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="68e94-107">(ваут) Адрес указателя интерфейса `IHostSecurityContext` `eContextType`к .</span><span class="sxs-lookup"><span data-stu-id="68e94-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68e94-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="68e94-108">Return Value</span></span>  
  
|<span data-ttu-id="68e94-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68e94-109">HRESULT</span></span>|<span data-ttu-id="68e94-110">Описание</span><span class="sxs-lookup"><span data-stu-id="68e94-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68e94-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="68e94-111">S_OK</span></span>|<span data-ttu-id="68e94-112">`GetSecurityContext`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="68e94-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="68e94-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="68e94-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="68e94-114">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="68e94-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="68e94-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68e94-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="68e94-116">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="68e94-116">The call timed out.</span></span>|  
|<span data-ttu-id="68e94-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="68e94-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="68e94-118">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="68e94-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="68e94-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="68e94-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="68e94-120">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="68e94-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="68e94-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68e94-121">E_FAIL</span></span>|<span data-ttu-id="68e94-122">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="68e94-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="68e94-123">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="68e94-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="68e94-124">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="68e94-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68e94-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="68e94-125">Remarks</span></span>  
 <span data-ttu-id="68e94-126">Хост может управлять всем доступом к коду к токетонотам потока как по CLR, так и по пользовательскому коду.</span><span class="sxs-lookup"><span data-stu-id="68e94-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="68e94-127">Он также может гарантировать, что полная информация о контексте безопасности передается через асинхронные операции или кодовые точки с ограниченным доступом к коду.</span><span class="sxs-lookup"><span data-stu-id="68e94-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="68e94-128">`IHostSecurityContext`инкапсулирует эту информацию контекста безопасности, которая непрозрачна для CLR.</span><span class="sxs-lookup"><span data-stu-id="68e94-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="68e94-129">CLR фиксирует эту информацию и перемещает ее по диспетчеризации элемента рабочего элемента пула потоков, выполнению окончательного элемента, а также конструкции модуля и класса.</span><span class="sxs-lookup"><span data-stu-id="68e94-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68e94-130">Требования</span><span class="sxs-lookup"><span data-stu-id="68e94-130">Requirements</span></span>  
 <span data-ttu-id="68e94-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68e94-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68e94-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68e94-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68e94-133">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68e94-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68e94-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68e94-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68e94-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="68e94-135">See also</span></span>

- [<span data-ttu-id="68e94-136">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="68e94-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="68e94-137">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="68e94-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="68e94-138">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="68e94-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
