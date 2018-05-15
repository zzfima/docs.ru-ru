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
ms.openlocfilehash: 5da62d8d46b71b1f9eef677d2252ec7b21a3ae4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="668fe-102">Метод IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="668fe-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="668fe-103">Предоставляет основному указатель интерфейса [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="668fe-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="668fe-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="668fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="668fe-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="668fe-106">[in] Указатель интерфейса `ICLRIoCompletionManager` экземпляра, предоставляемую средой CLR.</span><span class="sxs-lookup"><span data-stu-id="668fe-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="668fe-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="668fe-107">Return Value</span></span>  
  
|<span data-ttu-id="668fe-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="668fe-108">HRESULT</span></span>|<span data-ttu-id="668fe-109">Описание</span><span class="sxs-lookup"><span data-stu-id="668fe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="668fe-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="668fe-110">S_OK</span></span>|<span data-ttu-id="668fe-111">`SetCLRIoCompletionManager` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="668fe-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="668fe-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="668fe-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="668fe-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="668fe-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="668fe-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="668fe-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="668fe-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="668fe-115">The call timed out.</span></span>|  
|<span data-ttu-id="668fe-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="668fe-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="668fe-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="668fe-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="668fe-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="668fe-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="668fe-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="668fe-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="668fe-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="668fe-120">E_FAIL</span></span>|<span data-ttu-id="668fe-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="668fe-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="668fe-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="668fe-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="668fe-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="668fe-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="668fe-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="668fe-124">Remarks</span></span>  
 <span data-ttu-id="668fe-125">После вызова CLR `SetCLRIoCompletionManager`, узел должен вызвать метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) для уведомления среды CLR при завершении запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="668fe-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="668fe-126">Требования</span><span class="sxs-lookup"><span data-stu-id="668fe-126">Requirements</span></span>  
 <span data-ttu-id="668fe-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="668fe-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668fe-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="668fe-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="668fe-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="668fe-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="668fe-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="668fe-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668fe-131">См. также</span><span class="sxs-lookup"><span data-stu-id="668fe-131">See Also</span></span>  
 [<span data-ttu-id="668fe-132">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="668fe-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="668fe-133">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="668fe-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
