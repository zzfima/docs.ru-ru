---
title: Метод IHostIoCompletionManager::CloseIoCompletionPort
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 281284ca432efc86964a2e3e37fa89d1506aa350
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698678"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="aac39-102">Метод IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="aac39-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="aac39-103">Запрашивает, что узел закрыть порт, который был открыт через предыдущими вызовами [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="aac39-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aac39-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aac39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aac39-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="aac39-106">[in] Дескриптор для закрытия порта.</span><span class="sxs-lookup"><span data-stu-id="aac39-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aac39-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aac39-107">Return Value</span></span>  
  
|<span data-ttu-id="aac39-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aac39-108">HRESULT</span></span>|<span data-ttu-id="aac39-109">Описание</span><span class="sxs-lookup"><span data-stu-id="aac39-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aac39-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="aac39-110">S_OK</span></span>|<span data-ttu-id="aac39-111">`CloseIoCompletionPort` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="aac39-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="aac39-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aac39-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aac39-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="aac39-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aac39-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aac39-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aac39-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="aac39-115">The call timed out.</span></span>|  
|<span data-ttu-id="aac39-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aac39-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aac39-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="aac39-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aac39-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aac39-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aac39-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="aac39-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aac39-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aac39-120">E_FAIL</span></span>|<span data-ttu-id="aac39-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="aac39-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aac39-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="aac39-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aac39-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aac39-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="aac39-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="aac39-124">E_INVALIDARG</span></span>|<span data-ttu-id="aac39-125">Передан недопустимый дескриптор порта.</span><span class="sxs-lookup"><span data-stu-id="aac39-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aac39-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="aac39-126">Remarks</span></span>  
 <span data-ttu-id="aac39-127">`hPort` должен быть дескриптор к порту, которая была создана с предыдущими вызовами `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="aac39-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aac39-128">Требования</span><span class="sxs-lookup"><span data-stu-id="aac39-128">Requirements</span></span>  
 <span data-ttu-id="aac39-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aac39-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aac39-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aac39-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aac39-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aac39-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aac39-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac39-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac39-133">См. также</span><span class="sxs-lookup"><span data-stu-id="aac39-133">See also</span></span>
- [<span data-ttu-id="aac39-134">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="aac39-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="aac39-135">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="aac39-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
