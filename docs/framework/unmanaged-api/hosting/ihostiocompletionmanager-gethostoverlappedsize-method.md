---
title: "Метод IHostIoCompletionManager::GetHostOverlappedSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 41fc1a4a0debe0c302115c79962c0da50cc4ee37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="c9832-102">Метод IHostIoCompletionManager::GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="c9832-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="c9832-103">Получает размер любых пользовательских данных, которые должен узла для добавления запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c9832-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9832-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9832-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9832-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9832-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="c9832-106">[out] Указатель на число байтов, которые необходимо выделить общеязыковой среды выполнения (CLR) и размера Win32 `OVERLAPPED` объекта.</span><span class="sxs-lookup"><span data-stu-id="c9832-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9832-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c9832-107">Return Value</span></span>  
  
|<span data-ttu-id="c9832-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9832-108">HRESULT</span></span>|<span data-ttu-id="c9832-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c9832-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9832-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9832-110">S_OK</span></span>|<span data-ttu-id="c9832-111">`GetHostOverlappedSize`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c9832-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="c9832-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9832-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9832-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c9832-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9832-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9832-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9832-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c9832-115">The call timed out.</span></span>|  
|<span data-ttu-id="c9832-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9832-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9832-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c9832-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9832-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9832-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9832-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c9832-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9832-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9832-120">E_FAIL</span></span>|<span data-ttu-id="c9832-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c9832-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9832-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c9832-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9832-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c9832-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9832-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9832-124">Remarks</span></span>  
 <span data-ttu-id="c9832-125">Все асинхронные вызовы ввода-вывода для API-интерфейсы платформы Windows принимают Win32 `OVERLAPPED` object, который предоставляет сведения, такие как положение указателя файла.</span><span class="sxs-lookup"><span data-stu-id="c9832-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="c9832-126">Чтобы сохранять состояние, приложений, вызовов асинхронных операций ввода-вывода обычно добавить пользовательские данные в структуру.</span><span class="sxs-lookup"><span data-stu-id="c9832-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="c9832-127">`GetHostOverlappedSize`и [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) дают возможность для узла включить такие пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="c9832-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="c9832-128">Среда CLR вызывает `GetHostOverlappedSize` метод для определения размера пользовательских данных, который планирует добавить узел `OVERLAPPED` объекта.</span><span class="sxs-lookup"><span data-stu-id="c9832-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9832-129">`GetHostOverlappedSize`вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="c9832-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="c9832-130">Пользовательские данные узла должны быть одинакового размера для каждого запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c9832-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9832-131">Размер `OVERLAPPED` сам объект не включается в значение `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="c9832-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="c9832-132">Дополнительные сведения о `OVERLAPPED` структуры см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="c9832-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9832-133">Требования</span><span class="sxs-lookup"><span data-stu-id="c9832-133">Requirements</span></span>  
 <span data-ttu-id="c9832-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9832-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9832-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c9832-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9832-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9832-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9832-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9832-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9832-138">См. также</span><span class="sxs-lookup"><span data-stu-id="c9832-138">See Also</span></span>  
 <xref:System.Threading.NativeOverlapped>  
 [<span data-ttu-id="c9832-139">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c9832-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="c9832-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c9832-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
