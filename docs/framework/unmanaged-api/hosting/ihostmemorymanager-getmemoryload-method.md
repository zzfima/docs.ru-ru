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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176283"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="ebbc7-102">Метод IHostMemoryManager::GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="ebbc7-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="ebbc7-103">Получает количество физической памяти, которая в настоящее время используется, и, следовательно, недоступны, как сообщает хост.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebbc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebbc7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebbc7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebbc7-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="ebbc7-106">(ваут) Указатель на приблизительный процент общей физической памяти, которая в настоящее время используется.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="ebbc7-107">(ваут) Указатель на количество байтов, доступных для общего времени выполнения языка (CLR).</span><span class="sxs-lookup"><span data-stu-id="ebbc7-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebbc7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ebbc7-108">Return Value</span></span>  
  
|<span data-ttu-id="ebbc7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ebbc7-109">HRESULT</span></span>|<span data-ttu-id="ebbc7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ebbc7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebbc7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebbc7-111">S_OK</span></span>|<span data-ttu-id="ebbc7-112">`GetMemoryLoad`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="ebbc7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ebbc7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ebbc7-114">CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ebbc7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ebbc7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ebbc7-116">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-116">The call timed out.</span></span>|  
|<span data-ttu-id="ebbc7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ebbc7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ebbc7-118">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ebbc7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ebbc7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ebbc7-120">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ebbc7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ebbc7-121">E_FAIL</span></span>|<span data-ttu-id="ebbc7-122">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ebbc7-123">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ebbc7-124">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebbc7-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="ebbc7-125">Remarks</span></span>  
 <span data-ttu-id="ebbc7-126">`GetMemoryLoad`обертывает функцию `GlobalMemoryStatus` Win32.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="ebbc7-127">Значение `pMemoryLoad` эквивалентно еженедельнное `dwMemoryLoad` поле `GlobalMemoryStatus`в возвращаемом строении. `MEMORYSTATUS`</span><span class="sxs-lookup"><span data-stu-id="ebbc7-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="ebbc7-128">Время выполнения использует значение возврата в качестве эвристического для сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="ebbc7-129">Например, если хост сообщает, что большая часть памяти используется, сборщик мусора может выбрать для сбора из нескольких поколений, чтобы увеличить объем памяти, который потенциально может стать доступным.</span><span class="sxs-lookup"><span data-stu-id="ebbc7-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebbc7-130">Требования</span><span class="sxs-lookup"><span data-stu-id="ebbc7-130">Requirements</span></span>  
 <span data-ttu-id="ebbc7-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebbc7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebbc7-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebbc7-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebbc7-133">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebbc7-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebbc7-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebbc7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebbc7-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ebbc7-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="ebbc7-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="ebbc7-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
