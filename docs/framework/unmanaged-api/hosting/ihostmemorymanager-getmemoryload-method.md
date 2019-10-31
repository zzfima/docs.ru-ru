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
ms.openlocfilehash: 2210dcd9e8a8af92b7905ec680c53c1119e6a3cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136711"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="0a64c-102">Метод IHostMemoryManager::GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="0a64c-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="0a64c-103">Возвращает объем физической памяти, используемой в данный момент, и, следовательно, недоступен, сообщаемый узлом.</span><span class="sxs-lookup"><span data-stu-id="0a64c-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a64c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a64c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a64c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a64c-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="0a64c-106">заполняет Указатель на Приблизительный процент общего объема физической памяти, который используется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="0a64c-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="0a64c-107">заполняет Указатель на число байтов, доступных для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0a64c-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a64c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a64c-108">Return Value</span></span>  
  
|<span data-ttu-id="0a64c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a64c-109">HRESULT</span></span>|<span data-ttu-id="0a64c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0a64c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a64c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a64c-111">S_OK</span></span>|<span data-ttu-id="0a64c-112">`GetMemoryLoad` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="0a64c-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="0a64c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a64c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a64c-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0a64c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a64c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a64c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a64c-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="0a64c-116">The call timed out.</span></span>|  
|<span data-ttu-id="0a64c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a64c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a64c-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="0a64c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a64c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a64c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a64c-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="0a64c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a64c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a64c-121">E_FAIL</span></span>|<span data-ttu-id="0a64c-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0a64c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a64c-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0a64c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a64c-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0a64c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a64c-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="0a64c-125">Remarks</span></span>  
 <span data-ttu-id="0a64c-126">`GetMemoryLoad` создает оболочку для функции `GlobalMemoryStatus` Win32.</span><span class="sxs-lookup"><span data-stu-id="0a64c-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="0a64c-127">Значение `pMemoryLoad` является эквивалентом поля `dwMemoryLoad` в структуре `MEMORYSTATUS`, возвращаемой из `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="0a64c-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="0a64c-128">Среда выполнения использует возвращаемое значение в качестве эвристики для сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="0a64c-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="0a64c-129">Например, если основное приложение сообщает о том, что используется большая часть памяти, сборщик мусора может выбрать сбор данных из нескольких поколений, чтобы увеличить объем памяти, который потенциально может стать доступным.</span><span class="sxs-lookup"><span data-stu-id="0a64c-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a64c-130">Требования</span><span class="sxs-lookup"><span data-stu-id="0a64c-130">Requirements</span></span>  
 <span data-ttu-id="0a64c-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a64c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a64c-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0a64c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a64c-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0a64c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a64c-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a64c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a64c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="0a64c-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="0a64c-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="0a64c-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
