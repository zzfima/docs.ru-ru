---
title: Метод IHostIoCompletionManager::CreateIoCompletionPort
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cf7978af4081b84a361e0a96a6c9da7180cb217
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194049"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="f6fa9-102">Метод IHostIoCompletionManager::CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="f6fa9-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="f6fa9-103">Запросы на создание нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6fa9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6fa9-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6fa9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6fa9-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="f6fa9-106">[out] Указатель на дескриптор вновь созданного порта завершения ввода-вывода, или 0 (нуль), если не удалось создать порт.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6fa9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f6fa9-107">Return Value</span></span>  
  
|<span data-ttu-id="f6fa9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6fa9-108">HRESULT</span></span>|<span data-ttu-id="f6fa9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f6fa9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6fa9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6fa9-110">S_OK</span></span>|<span data-ttu-id="f6fa9-111">`CreateIoCompletionPort` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="f6fa9-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6fa9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6fa9-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6fa9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6fa9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6fa9-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-115">The call timed out.</span></span>|  
|<span data-ttu-id="f6fa9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6fa9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6fa9-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6fa9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6fa9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6fa9-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6fa9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6fa9-120">E_FAIL</span></span>|<span data-ttu-id="f6fa9-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6fa9-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6fa9-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6fa9-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f6fa9-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f6fa9-125">Недостаточно памяти, доступного для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6fa9-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6fa9-126">Remarks</span></span>  
 <span data-ttu-id="f6fa9-127">Среда CLR вызывает `CreateIoCompletionPort` метод для запроса, создания нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="f6fa9-128">Привязывает операции ввода-вывода к этому порту посредством вызова [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f6fa9-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="f6fa9-129">Узел сообщает о состоянии обратно в среду CLR, вызвав [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="f6fa9-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6fa9-130">Требования</span><span class="sxs-lookup"><span data-stu-id="f6fa9-130">Requirements</span></span>  
 <span data-ttu-id="f6fa9-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6fa9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6fa9-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6fa9-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6fa9-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6fa9-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6fa9-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6fa9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6fa9-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f6fa9-135">See also</span></span>

- [<span data-ttu-id="f6fa9-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f6fa9-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="f6fa9-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f6fa9-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
