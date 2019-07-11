---
title: Метод IHostIoCompletionManager::SetCLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97d4561c34c03eefc7487f5f96b7a490a480ac19
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780761"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="b0f04-102">Метод IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b0f04-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="b0f04-103">Предоставляет указатель интерфейса на узле [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="b0f04-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0f04-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0f04-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0f04-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="b0f04-106">[in] Указатель интерфейса на `ICLRIoCompletionManager` экземпляра, предоставляемыми средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b0f04-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0f04-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b0f04-107">Return Value</span></span>  
  
|<span data-ttu-id="b0f04-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0f04-108">HRESULT</span></span>|<span data-ttu-id="b0f04-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b0f04-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0f04-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0f04-110">S_OK</span></span>|<span data-ttu-id="b0f04-111">`SetCLRIoCompletionManager` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b0f04-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="b0f04-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0f04-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b0f04-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b0f04-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b0f04-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b0f04-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b0f04-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b0f04-115">The call timed out.</span></span>|  
|<span data-ttu-id="b0f04-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b0f04-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b0f04-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b0f04-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b0f04-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b0f04-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b0f04-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b0f04-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b0f04-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0f04-120">E_FAIL</span></span>|<span data-ttu-id="b0f04-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="b0f04-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b0f04-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b0f04-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b0f04-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b0f04-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0f04-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0f04-124">Remarks</span></span>  
 <span data-ttu-id="b0f04-125">После вызова CLR `SetCLRIoCompletionManager`, узел должен вызвать метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) для уведомления среды CLR после завершения запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b0f04-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0f04-126">Требования</span><span class="sxs-lookup"><span data-stu-id="b0f04-126">Requirements</span></span>  
 <span data-ttu-id="b0f04-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0f04-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0f04-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0f04-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0f04-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0f04-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0f04-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0f04-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f04-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b0f04-131">See also</span></span>

- [<span data-ttu-id="b0f04-132">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b0f04-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b0f04-133">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b0f04-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
