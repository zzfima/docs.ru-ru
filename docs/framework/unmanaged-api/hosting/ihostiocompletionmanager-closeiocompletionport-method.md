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
ms.openlocfilehash: cceced01b34f10cf38b41cfcb2a17059650f9ad9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736535"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="dda69-102">Метод IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="dda69-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="dda69-103">Запрашивает, что узел закрыть порт, который был открыт через предыдущими вызовами [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="dda69-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dda69-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dda69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dda69-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="dda69-106">[in] Дескриптор для закрытия порта.</span><span class="sxs-lookup"><span data-stu-id="dda69-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dda69-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dda69-107">Return Value</span></span>  
  
|<span data-ttu-id="dda69-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dda69-108">HRESULT</span></span>|<span data-ttu-id="dda69-109">Описание</span><span class="sxs-lookup"><span data-stu-id="dda69-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dda69-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dda69-110">S_OK</span></span>|<span data-ttu-id="dda69-111">`CloseIoCompletionPort` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dda69-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="dda69-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dda69-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dda69-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dda69-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dda69-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dda69-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dda69-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="dda69-115">The call timed out.</span></span>|  
|<span data-ttu-id="dda69-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dda69-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dda69-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="dda69-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dda69-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dda69-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dda69-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="dda69-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dda69-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dda69-120">E_FAIL</span></span>|<span data-ttu-id="dda69-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="dda69-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dda69-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dda69-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dda69-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dda69-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dda69-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dda69-124">E_INVALIDARG</span></span>|<span data-ttu-id="dda69-125">Передан недопустимый дескриптор порта.</span><span class="sxs-lookup"><span data-stu-id="dda69-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dda69-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="dda69-126">Remarks</span></span>  
 <span data-ttu-id="dda69-127">`hPort` должен быть дескриптор к порту, которая была создана с предыдущими вызовами `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="dda69-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dda69-128">Требования</span><span class="sxs-lookup"><span data-stu-id="dda69-128">Requirements</span></span>  
 <span data-ttu-id="dda69-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dda69-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dda69-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dda69-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dda69-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dda69-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dda69-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dda69-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda69-133">См. также</span><span class="sxs-lookup"><span data-stu-id="dda69-133">See also</span></span>

- [<span data-ttu-id="dda69-134">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="dda69-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="dda69-135">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="dda69-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
