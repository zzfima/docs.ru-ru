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
ms.openlocfilehash: 9fd299ad25166bcbcf0202da13a5b4cbdd20d7d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133799"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="26a90-102">Метод IHostIoCompletionManager::InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="26a90-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="26a90-103">Предоставляет узлу возможность инициализировать любые пользовательские данные, добавляемые в структуру Win32 `OVERLAPPED`, которая используется для асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="26a90-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26a90-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26a90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="26a90-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="26a90-106">окне Указатель на структуру Win32 `OVERLAPPED`, включаемую в запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="26a90-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26a90-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="26a90-107">Return Value</span></span>  
  
|<span data-ttu-id="26a90-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="26a90-108">HRESULT</span></span>|<span data-ttu-id="26a90-109">Описание</span><span class="sxs-lookup"><span data-stu-id="26a90-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="26a90-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="26a90-110">S_OK</span></span>|<span data-ttu-id="26a90-111">`InitializeHostOverlapped` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="26a90-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="26a90-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="26a90-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="26a90-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="26a90-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="26a90-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="26a90-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="26a90-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="26a90-115">The call timed out.</span></span>|  
|<span data-ttu-id="26a90-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="26a90-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="26a90-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="26a90-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="26a90-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="26a90-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="26a90-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="26a90-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="26a90-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="26a90-120">E_FAIL</span></span>|<span data-ttu-id="26a90-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="26a90-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="26a90-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="26a90-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="26a90-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="26a90-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="26a90-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="26a90-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="26a90-125">Недостаточно памяти для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="26a90-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26a90-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="26a90-126">Remarks</span></span>  
 <span data-ttu-id="26a90-127">Функции платформы Windows используют структуру `OVERLAPPED` для хранения состояния асинхронных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="26a90-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="26a90-128">Среда CLR вызывает метод `InitializeHostOverlapped`, чтобы предоставить узлу возможность добавлять пользовательские данные в экземпляр `OVERLAPPED`.</span><span class="sxs-lookup"><span data-stu-id="26a90-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="26a90-129">Чтобы перейти к началу пользовательского блока данных, узлы должны задать для смещения размер структуры `OVERLAPPED` (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="26a90-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="26a90-130">Возвращаемое значение E_OUTOFMEMORY указывает на то, что узлу не удалось инициализировать свои пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="26a90-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="26a90-131">В этом случае среда CLR сообщает об ошибке и вызове завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="26a90-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a90-132">Требования</span><span class="sxs-lookup"><span data-stu-id="26a90-132">Requirements</span></span>  
 <span data-ttu-id="26a90-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a90-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a90-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="26a90-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26a90-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="26a90-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26a90-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26a90-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a90-137">См. также</span><span class="sxs-lookup"><span data-stu-id="26a90-137">See also</span></span>

- [<span data-ttu-id="26a90-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="26a90-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="26a90-139">Метод GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="26a90-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="26a90-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="26a90-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
