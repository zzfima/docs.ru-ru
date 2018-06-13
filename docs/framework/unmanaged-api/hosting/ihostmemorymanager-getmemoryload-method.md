---
title: Метод IHostMemoryManager::GetMemoryLoad
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92ef3a6d7eb45a3b978c916c406bfa6199f17d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440152"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="66235-102">Метод IHostMemoryManager::GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="66235-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="66235-103">Получает объем физической памяти, в настоящее время используется и следовательно, недоступной, как с отчетом узла.</span><span class="sxs-lookup"><span data-stu-id="66235-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66235-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66235-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66235-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66235-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="66235-106">[out] Указатель на примерное процентное соотношение общего объема физической памяти, который используется в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="66235-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="66235-107">[out] Указатель на число байтов, доступных для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="66235-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66235-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="66235-108">Return Value</span></span>  
  
|<span data-ttu-id="66235-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66235-109">HRESULT</span></span>|<span data-ttu-id="66235-110">Описание</span><span class="sxs-lookup"><span data-stu-id="66235-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66235-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="66235-111">S_OK</span></span>|<span data-ttu-id="66235-112">`GetMemoryLoad` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="66235-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="66235-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="66235-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="66235-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="66235-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="66235-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="66235-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="66235-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="66235-116">The call timed out.</span></span>|  
|<span data-ttu-id="66235-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="66235-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="66235-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="66235-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="66235-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="66235-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="66235-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="66235-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="66235-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66235-121">E_FAIL</span></span>|<span data-ttu-id="66235-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="66235-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66235-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="66235-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="66235-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="66235-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66235-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="66235-125">Remarks</span></span>  
 <span data-ttu-id="66235-126">`GetMemoryLoad` Создает оболочку для Win32 `GlobalMemoryStatus` функции.</span><span class="sxs-lookup"><span data-stu-id="66235-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="66235-127">Значение `pMemoryLoad` является эквивалентом `dwMemoryLoad` в `MEMORYSTATUS` структуры, возвращенный `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="66235-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="66235-128">Среда выполнения использует возвращаемое значение в качестве эвристики для сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="66235-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="66235-129">Например если узел сообщает, что большая часть памяти используется, сборщик мусора может приступить нескольких поколениях с целью увеличить объем памяти, который потенциально может стать доступным.</span><span class="sxs-lookup"><span data-stu-id="66235-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66235-130">Требования</span><span class="sxs-lookup"><span data-stu-id="66235-130">Requirements</span></span>  
 <span data-ttu-id="66235-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66235-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66235-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="66235-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66235-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66235-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66235-134">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66235-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66235-135">См. также</span><span class="sxs-lookup"><span data-stu-id="66235-135">See Also</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
 [<span data-ttu-id="66235-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="66235-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
