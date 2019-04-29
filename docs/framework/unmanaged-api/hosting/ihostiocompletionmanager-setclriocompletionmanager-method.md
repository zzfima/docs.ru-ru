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
ms.openlocfilehash: cd48664c78e3f5772cdfa655ebbc7cfa716f4950
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796848"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="21e11-102">Метод IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="21e11-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="21e11-103">Предоставляет указатель интерфейса на узле [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="21e11-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21e11-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21e11-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21e11-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="21e11-106">[in] Указатель интерфейса на `ICLRIoCompletionManager` экземпляра, предоставляемыми средой CLR.</span><span class="sxs-lookup"><span data-stu-id="21e11-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21e11-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="21e11-107">Return Value</span></span>  
  
|<span data-ttu-id="21e11-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21e11-108">HRESULT</span></span>|<span data-ttu-id="21e11-109">Описание</span><span class="sxs-lookup"><span data-stu-id="21e11-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21e11-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="21e11-110">S_OK</span></span>|<span data-ttu-id="21e11-111">`SetCLRIoCompletionManager` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="21e11-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="21e11-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="21e11-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21e11-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="21e11-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="21e11-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="21e11-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="21e11-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="21e11-115">The call timed out.</span></span>|  
|<span data-ttu-id="21e11-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="21e11-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="21e11-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="21e11-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="21e11-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="21e11-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="21e11-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="21e11-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="21e11-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21e11-120">E_FAIL</span></span>|<span data-ttu-id="21e11-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="21e11-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="21e11-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="21e11-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="21e11-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="21e11-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21e11-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="21e11-124">Remarks</span></span>  
 <span data-ttu-id="21e11-125">После вызова CLR `SetCLRIoCompletionManager`, узел должен вызвать метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) для уведомления среды CLR после завершения запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="21e11-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e11-126">Требования</span><span class="sxs-lookup"><span data-stu-id="21e11-126">Requirements</span></span>  
 <span data-ttu-id="21e11-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21e11-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e11-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21e11-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21e11-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21e11-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21e11-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e11-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e11-131">См. также</span><span class="sxs-lookup"><span data-stu-id="21e11-131">See also</span></span>

- [<span data-ttu-id="21e11-132">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="21e11-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="21e11-133">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="21e11-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
