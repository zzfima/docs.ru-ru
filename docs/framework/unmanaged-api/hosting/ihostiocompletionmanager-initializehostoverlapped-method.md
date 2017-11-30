---
title: "Метод IHostIoCompletionManager::InitializeHostOverlapped"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.InitializeHostOverlapped
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26e8f9d963e6924a8c6abd73c3e025543c7d5b83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="4621a-102">Метод IHostIoCompletionManager::InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="4621a-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="4621a-103">Предоставляет основному приложению возможность инициализировать любые пользовательские данные для добавления Win32 `OVERLAPPED` структура, используемая для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4621a-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4621a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4621a-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4621a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4621a-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="4621a-106">[in] Указатель на Win32 `OVERLAPPED` структуры, которые нужно включить в запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4621a-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4621a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4621a-107">Return Value</span></span>  
  
|<span data-ttu-id="4621a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4621a-108">HRESULT</span></span>|<span data-ttu-id="4621a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4621a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4621a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4621a-110">S_OK</span></span>|<span data-ttu-id="4621a-111">`InitializeHostOverlapped`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4621a-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="4621a-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4621a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4621a-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4621a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4621a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4621a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4621a-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4621a-115">The call timed out.</span></span>|  
|<span data-ttu-id="4621a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4621a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4621a-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4621a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4621a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4621a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4621a-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4621a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4621a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4621a-120">E_FAIL</span></span>|<span data-ttu-id="4621a-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4621a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4621a-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4621a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4621a-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4621a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4621a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4621a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4621a-125">Не хватает памяти была доступна для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="4621a-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4621a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="4621a-126">Remarks</span></span>  
 <span data-ttu-id="4621a-127">Платформа Windows используют `OVERLAPPED` структуры для хранения состояния для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4621a-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="4621a-128">Среда CLR вызывает `InitializeHostOverlapped` метод, чтобы предоставить возможность добавлять пользовательские данные для узла `OVERLAPPED` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4621a-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4621a-129">Для перехода в начало пользовательского блока данных, узлов необходимо задать смещение размер `OVERLAPPED` структуры (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="4621a-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="4621a-130">Возвращаемое значение E_OUTOFMEMORY указывает, что узел не удалось инициализировать его пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="4621a-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="4621a-131">В этом случае среда CLR сообщает об ошибке и происходит сбой вызова.</span><span class="sxs-lookup"><span data-stu-id="4621a-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4621a-132">Требования</span><span class="sxs-lookup"><span data-stu-id="4621a-132">Requirements</span></span>  
 <span data-ttu-id="4621a-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4621a-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4621a-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4621a-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4621a-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4621a-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4621a-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4621a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4621a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="4621a-137">See Also</span></span>  
 [<span data-ttu-id="4621a-138">ICLRIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4621a-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="4621a-139">Gethostoverlappedsize-метод</span><span class="sxs-lookup"><span data-stu-id="4621a-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [<span data-ttu-id="4621a-140">IHostIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4621a-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
