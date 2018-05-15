---
title: Метод IHostIoCompletionManager::InitializeHostOverlapped
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 023e112aa8273d99efce2e0f2116f95569ac0c3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="59b20-102">Метод IHostIoCompletionManager::InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="59b20-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="59b20-103">Предоставляет основному приложению возможность инициализировать любые пользовательские данные для добавления Win32 `OVERLAPPED` структура, используемая для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="59b20-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59b20-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59b20-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="59b20-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="59b20-106">[in] Указатель на Win32 `OVERLAPPED` структуры, которые нужно включить в запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="59b20-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59b20-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="59b20-107">Return Value</span></span>  
  
|<span data-ttu-id="59b20-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59b20-108">HRESULT</span></span>|<span data-ttu-id="59b20-109">Описание</span><span class="sxs-lookup"><span data-stu-id="59b20-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59b20-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="59b20-110">S_OK</span></span>|<span data-ttu-id="59b20-111">`InitializeHostOverlapped` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="59b20-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="59b20-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="59b20-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="59b20-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="59b20-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="59b20-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="59b20-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="59b20-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="59b20-115">The call timed out.</span></span>|  
|<span data-ttu-id="59b20-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="59b20-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="59b20-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="59b20-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="59b20-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="59b20-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="59b20-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="59b20-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="59b20-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="59b20-120">E_FAIL</span></span>|<span data-ttu-id="59b20-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="59b20-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="59b20-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="59b20-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="59b20-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="59b20-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="59b20-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="59b20-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="59b20-125">Не хватает памяти была доступна для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="59b20-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59b20-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="59b20-126">Remarks</span></span>  
 <span data-ttu-id="59b20-127">Платформа Windows используют `OVERLAPPED` структуры для хранения состояния для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="59b20-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="59b20-128">Среда CLR вызывает `InitializeHostOverlapped` метод, чтобы предоставить возможность добавлять пользовательские данные для узла `OVERLAPPED` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="59b20-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59b20-129">Для перехода в начало пользовательского блока данных, узлов необходимо задать смещение размер `OVERLAPPED` структуры (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="59b20-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="59b20-130">Возвращаемое значение E_OUTOFMEMORY указывает, что узел не удалось инициализировать его пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="59b20-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="59b20-131">В этом случае среда CLR сообщает об ошибке и происходит сбой вызова.</span><span class="sxs-lookup"><span data-stu-id="59b20-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b20-132">Требования</span><span class="sxs-lookup"><span data-stu-id="59b20-132">Requirements</span></span>  
 <span data-ttu-id="59b20-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59b20-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b20-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="59b20-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59b20-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59b20-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59b20-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59b20-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b20-137">См. также</span><span class="sxs-lookup"><span data-stu-id="59b20-137">See Also</span></span>  
 [<span data-ttu-id="59b20-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="59b20-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="59b20-139">Метод GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="59b20-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [<span data-ttu-id="59b20-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="59b20-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
