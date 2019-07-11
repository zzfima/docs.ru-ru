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
ms.openlocfilehash: 9d27799e427efd3659dc2864e7d1e8e2061c5c19
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780779"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="4c8dc-102">Метод IHostIoCompletionManager::InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="4c8dc-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="4c8dc-103">Предоставляет возможность инициализировать любые пользовательские данные, добавляемые в Win32 основному `OVERLAPPED` структура, используемая для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c8dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c8dc-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c8dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c8dc-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="4c8dc-106">[in] Указатель на Win32 `OVERLAPPED` структуры, которые нужно включить в запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c8dc-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4c8dc-107">Return Value</span></span>  
  
|<span data-ttu-id="4c8dc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c8dc-108">HRESULT</span></span>|<span data-ttu-id="4c8dc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4c8dc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c8dc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c8dc-110">S_OK</span></span>|<span data-ttu-id="4c8dc-111">`InitializeHostOverlapped` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="4c8dc-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4c8dc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4c8dc-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4c8dc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4c8dc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4c8dc-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-115">The call timed out.</span></span>|  
|<span data-ttu-id="4c8dc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c8dc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4c8dc-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4c8dc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4c8dc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4c8dc-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4c8dc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4c8dc-120">E_FAIL</span></span>|<span data-ttu-id="4c8dc-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4c8dc-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4c8dc-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4c8dc-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4c8dc-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4c8dc-125">Недостаточно памяти, доступного для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c8dc-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c8dc-126">Remarks</span></span>  
 <span data-ttu-id="4c8dc-127">Платформа Windows используют функции `OVERLAPPED` структуру для хранения состояния для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="4c8dc-128">Среда CLR вызывает `InitializeHostOverlapped` метод, чтобы предоставить возможность добавления пользовательских данных для узла `OVERLAPPED` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c8dc-129">Для перехода в начало пользовательского блока данных, узлов необходимо установить смещение размер `OVERLAPPED` структуры (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="4c8dc-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="4c8dc-130">Возвращаемое значение E_OUTOFMEMORY указывает, что узел не удалось инициализировать его пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="4c8dc-131">В этом случае среда CLR сообщает об ошибке и считает вызов неудачным.</span><span class="sxs-lookup"><span data-stu-id="4c8dc-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c8dc-132">Требования</span><span class="sxs-lookup"><span data-stu-id="4c8dc-132">Requirements</span></span>  
 <span data-ttu-id="4c8dc-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c8dc-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c8dc-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4c8dc-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c8dc-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c8dc-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c8dc-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c8dc-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c8dc-137">См. также</span><span class="sxs-lookup"><span data-stu-id="4c8dc-137">See also</span></span>

- [<span data-ttu-id="4c8dc-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4c8dc-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="4c8dc-139">Метод GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="4c8dc-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="4c8dc-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4c8dc-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
