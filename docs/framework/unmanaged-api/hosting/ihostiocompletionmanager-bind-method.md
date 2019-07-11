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
ms.openlocfilehash: d73b8b635be78472374668bbcc36541616705651
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736542"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="3c5a3-102">Метод IHostIoCompletionManager::Bind</span><span class="sxs-lookup"><span data-stu-id="3c5a3-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="3c5a3-103">Привязывает указанный дескриптор к порту завершения ввода-вывода, который был создан с предыдущими вызовами [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="3c5a3-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c5a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c5a3-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c5a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c5a3-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="3c5a3-106">[in] Порт завершения ввода-вывода, к которому требуется привязать `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="3c5a3-107">Если значение `hPort` имеет значение null, `hHandle` привязан к порту завершения ввода-вывода по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="3c5a3-108">[in] Дескриптор операционной системы для привязки к `hPort`.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c5a3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c5a3-109">Return Value</span></span>  
  
|<span data-ttu-id="3c5a3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c5a3-110">HRESULT</span></span>|<span data-ttu-id="3c5a3-111">Описание</span><span class="sxs-lookup"><span data-stu-id="3c5a3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c5a3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c5a3-112">S_OK</span></span>|<span data-ttu-id="3c5a3-113">`Bind` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="3c5a3-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c5a3-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c5a3-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c5a3-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c5a3-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c5a3-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-117">The call timed out.</span></span>|  
|<span data-ttu-id="3c5a3-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c5a3-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c5a3-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c5a3-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c5a3-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c5a3-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c5a3-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c5a3-122">E_FAIL</span></span>|<span data-ttu-id="3c5a3-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c5a3-124">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c5a3-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c5a3-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c5a3-126">Remarks</span></span>  
 <span data-ttu-id="3c5a3-127">Порт завершения ввода-вывода создается с помощью вызова `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="3c5a3-128">Среда CLR вызывает `Bind` для привязки дескриптора к этому порту.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c5a3-129">При завершении запроса ввода-вывода, узел должен вызвать метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3c5a3-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c5a3-130">Требования</span><span class="sxs-lookup"><span data-stu-id="3c5a3-130">Requirements</span></span>  
 <span data-ttu-id="3c5a3-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c5a3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c5a3-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c5a3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c5a3-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c5a3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c5a3-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c5a3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5a3-135">См. также</span><span class="sxs-lookup"><span data-stu-id="3c5a3-135">See also</span></span>

- [<span data-ttu-id="3c5a3-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="3c5a3-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
