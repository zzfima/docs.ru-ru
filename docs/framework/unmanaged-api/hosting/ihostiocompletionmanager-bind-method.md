---
title: Метод IHostIoCompletionManager::Bind
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fa87026e0d4c93da782be15bef98afa9a0e4dfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102470"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="2a742-102">Метод IHostIoCompletionManager::Bind</span><span class="sxs-lookup"><span data-stu-id="2a742-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="2a742-103">Привязывает указанный дескриптор к порту завершения ввода-вывода, который был создан с предыдущими вызовами [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="2a742-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a742-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a742-104">Syntax</span></span>  
  
```  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a742-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a742-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="2a742-106">[in] Порт завершения ввода-вывода, к которому требуется привязать `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="2a742-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="2a742-107">Если значение `hPort` имеет значение null, `hHandle` привязан к порту завершения ввода-вывода по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a742-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="2a742-108">[in] Дескриптор операционной системы для привязки к `hPort`.</span><span class="sxs-lookup"><span data-stu-id="2a742-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a742-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a742-109">Return Value</span></span>  
  
|<span data-ttu-id="2a742-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a742-110">HRESULT</span></span>|<span data-ttu-id="2a742-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2a742-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a742-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a742-112">S_OK</span></span>|<span data-ttu-id="2a742-113">`Bind` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2a742-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="2a742-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a742-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a742-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2a742-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a742-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a742-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a742-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2a742-117">The call timed out.</span></span>|  
|<span data-ttu-id="2a742-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a742-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a742-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2a742-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a742-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a742-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a742-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2a742-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a742-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a742-122">E_FAIL</span></span>|<span data-ttu-id="2a742-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="2a742-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a742-124">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2a742-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a742-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2a742-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a742-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a742-126">Remarks</span></span>  
 <span data-ttu-id="2a742-127">Порт завершения ввода-вывода создается с помощью вызова `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="2a742-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="2a742-128">Среда CLR вызывает `Bind` для привязки дескриптора к этому порту.</span><span class="sxs-lookup"><span data-stu-id="2a742-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a742-129">При завершении запроса ввода-вывода, узел должен вызвать метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2a742-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a742-130">Требования</span><span class="sxs-lookup"><span data-stu-id="2a742-130">Requirements</span></span>  
 <span data-ttu-id="2a742-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a742-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a742-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a742-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a742-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a742-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a742-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a742-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a742-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2a742-135">See also</span></span>

- [<span data-ttu-id="2a742-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2a742-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
