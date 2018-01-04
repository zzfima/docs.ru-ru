---
title: "Метод IHostIoCompletionManager::CreateIoCompletionPort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CreateIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 230d6446460af92dbc4356977c0df4556d0229a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="e3926-102">Метод IHostIoCompletionManager::CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="e3926-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="e3926-103">Запросы на создание нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="e3926-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3926-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3926-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3926-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3926-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="e3926-106">[out] Указатель на дескриптор вновь созданного порта завершения ввода-вывода или 0 (нуль), если не удалось создать порт.</span><span class="sxs-lookup"><span data-stu-id="e3926-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3926-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3926-107">Return Value</span></span>  
  
|<span data-ttu-id="e3926-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3926-108">HRESULT</span></span>|<span data-ttu-id="e3926-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e3926-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3926-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3926-110">S_OK</span></span>|<span data-ttu-id="e3926-111">`CreateIoCompletionPort`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e3926-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="e3926-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3926-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3926-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e3926-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3926-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3926-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3926-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e3926-115">The call timed out.</span></span>|  
|<span data-ttu-id="e3926-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3926-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3926-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e3926-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3926-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3926-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3926-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e3926-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3926-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3926-120">E_FAIL</span></span>|<span data-ttu-id="e3926-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="e3926-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3926-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e3926-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3926-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3926-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e3926-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e3926-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e3926-125">Не хватает памяти была доступна для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="e3926-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3926-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3926-126">Remarks</span></span>  
 <span data-ttu-id="e3926-127">Среда CLR вызывает `CreateIoCompletionPort` метод для запроса, создания нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="e3926-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="e3926-128">Привязывает операции ввода-вывода к этому порту посредством вызова [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="e3926-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="e3926-129">Узел сообщает состояние обратно в среду CLR, вызвав [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="e3926-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3926-130">Требования</span><span class="sxs-lookup"><span data-stu-id="e3926-130">Requirements</span></span>  
 <span data-ttu-id="e3926-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3926-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3926-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3926-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3926-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e3926-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3926-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3926-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3926-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e3926-135">See Also</span></span>  
 [<span data-ttu-id="e3926-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="e3926-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="e3926-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="e3926-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
