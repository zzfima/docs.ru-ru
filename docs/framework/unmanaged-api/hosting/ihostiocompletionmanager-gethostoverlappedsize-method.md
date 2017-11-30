---
title: "Метод IHostIoCompletionManager::GetHostOverlappedSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetHostOverlappedSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6633e0271f29d44bb1d14495d80ffdf9868485a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="4819c-102">Метод IHostIoCompletionManager::GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="4819c-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="4819c-103">Получает размер любых пользовательских данных, которые должен узла для добавления запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4819c-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4819c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4819c-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4819c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4819c-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="4819c-106">[out] Указатель на число байтов, которые необходимо выделить общеязыковой среды выполнения (CLR) и размера Win32 `OVERLAPPED` объекта.</span><span class="sxs-lookup"><span data-stu-id="4819c-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4819c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4819c-107">Return Value</span></span>  
  
|<span data-ttu-id="4819c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4819c-108">HRESULT</span></span>|<span data-ttu-id="4819c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4819c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4819c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4819c-110">S_OK</span></span>|<span data-ttu-id="4819c-111">`GetHostOverlappedSize`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4819c-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="4819c-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4819c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4819c-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4819c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4819c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4819c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4819c-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4819c-115">The call timed out.</span></span>|  
|<span data-ttu-id="4819c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4819c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4819c-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4819c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4819c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4819c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4819c-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4819c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4819c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4819c-120">E_FAIL</span></span>|<span data-ttu-id="4819c-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4819c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4819c-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4819c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4819c-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4819c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4819c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="4819c-124">Remarks</span></span>  
 <span data-ttu-id="4819c-125">Все асинхронные вызовы ввода-вывода для API-интерфейсы платформы Windows принимают Win32 `OVERLAPPED` object, который предоставляет сведения, такие как положение указателя файла.</span><span class="sxs-lookup"><span data-stu-id="4819c-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="4819c-126">Чтобы сохранять состояние, приложений, вызовов асинхронных операций ввода-вывода обычно добавить пользовательские данные в структуру.</span><span class="sxs-lookup"><span data-stu-id="4819c-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="4819c-127">`GetHostOverlappedSize`и [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) дают возможность для узла включить такие пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="4819c-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="4819c-128">Среда CLR вызывает `GetHostOverlappedSize` метод для определения размера пользовательских данных, который планирует добавить узел `OVERLAPPED` объекта.</span><span class="sxs-lookup"><span data-stu-id="4819c-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4819c-129">`GetHostOverlappedSize`вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="4819c-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="4819c-130">Пользовательские данные узла должны быть одинакового размера для каждого запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4819c-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4819c-131">Размер `OVERLAPPED` сам объект не включается в значение `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="4819c-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="4819c-132">Дополнительные сведения о `OVERLAPPED` структуры см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="4819c-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4819c-133">Требования</span><span class="sxs-lookup"><span data-stu-id="4819c-133">Requirements</span></span>  
 <span data-ttu-id="4819c-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4819c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4819c-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4819c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4819c-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4819c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4819c-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4819c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4819c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="4819c-138">See Also</span></span>  
 <xref:System.Threading.NativeOverlapped>  
 [<span data-ttu-id="4819c-139">ICLRIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4819c-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="4819c-140">IHostIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4819c-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
