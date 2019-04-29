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
ms.openlocfilehash: 1dea19a13cd2c741a24695b293ae1c8621ad5688
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796803"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="c70bb-102">Метод IHostIoCompletionManager::InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="c70bb-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="c70bb-103">Предоставляет возможность инициализировать любые пользовательские данные, добавляемые в Win32 основному `OVERLAPPED` структура, используемая для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c70bb-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c70bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c70bb-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c70bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c70bb-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="c70bb-106">[in] Указатель на Win32 `OVERLAPPED` структуры, которые нужно включить в запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c70bb-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c70bb-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c70bb-107">Return Value</span></span>  
  
|<span data-ttu-id="c70bb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c70bb-108">HRESULT</span></span>|<span data-ttu-id="c70bb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c70bb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c70bb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c70bb-110">S_OK</span></span>|<span data-ttu-id="c70bb-111">`InitializeHostOverlapped` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c70bb-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="c70bb-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c70bb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c70bb-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c70bb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c70bb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c70bb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c70bb-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c70bb-115">The call timed out.</span></span>|  
|<span data-ttu-id="c70bb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c70bb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c70bb-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c70bb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c70bb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c70bb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c70bb-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c70bb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c70bb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c70bb-120">E_FAIL</span></span>|<span data-ttu-id="c70bb-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c70bb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c70bb-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c70bb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c70bb-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c70bb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c70bb-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c70bb-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c70bb-125">Недостаточно памяти, доступного для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="c70bb-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c70bb-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="c70bb-126">Remarks</span></span>  
 <span data-ttu-id="c70bb-127">Платформа Windows используют функции `OVERLAPPED` структуру для хранения состояния для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c70bb-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="c70bb-128">Среда CLR вызывает `InitializeHostOverlapped` метод, чтобы предоставить возможность добавления пользовательских данных для узла `OVERLAPPED` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c70bb-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c70bb-129">Для перехода в начало пользовательского блока данных, узлов необходимо установить смещение размер `OVERLAPPED` структуры (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="c70bb-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="c70bb-130">Возвращаемое значение E_OUTOFMEMORY указывает, что узел не удалось инициализировать его пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="c70bb-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="c70bb-131">В этом случае среда CLR сообщает об ошибке и считает вызов неудачным.</span><span class="sxs-lookup"><span data-stu-id="c70bb-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c70bb-132">Требования</span><span class="sxs-lookup"><span data-stu-id="c70bb-132">Requirements</span></span>  
 <span data-ttu-id="c70bb-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c70bb-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c70bb-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c70bb-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c70bb-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c70bb-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c70bb-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c70bb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c70bb-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c70bb-137">See also</span></span>

- [<span data-ttu-id="c70bb-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c70bb-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c70bb-139">Метод GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="c70bb-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="c70bb-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c70bb-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
