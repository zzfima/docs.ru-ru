---
title: Метод IHostThreadPoolManager::QueueUserWorkItem
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
ms.openlocfilehash: 39c35884d0fb53baefafbf86391a349e141418a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141315"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="1867d-102">Метод IHostThreadPoolManager::QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="1867d-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="1867d-103">Ставит в очередь функцию для выполнения и указывает объект, содержащий данные, которые будут использоваться этой функцией.</span><span class="sxs-lookup"><span data-stu-id="1867d-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="1867d-104">Функция выполняется, когда поток станет доступным.</span><span class="sxs-lookup"><span data-stu-id="1867d-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1867d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1867d-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1867d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1867d-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="1867d-107">окне Указатель функции, представляющий функцию для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1867d-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="1867d-108">окне Объект, содержащий данные, используемые `Function`.</span><span class="sxs-lookup"><span data-stu-id="1867d-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="1867d-109">окне Одно из значений флагов, определенное для метода `QueueUserWorkItem` Win32, которое управляет выполнением.</span><span class="sxs-lookup"><span data-stu-id="1867d-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1867d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1867d-110">Return Value</span></span>  
  
|<span data-ttu-id="1867d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1867d-111">HRESULT</span></span>|<span data-ttu-id="1867d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1867d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1867d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1867d-113">S_OK</span></span>|<span data-ttu-id="1867d-114">`QueueUserWorkItem` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1867d-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="1867d-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1867d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1867d-116">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1867d-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1867d-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1867d-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1867d-118">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1867d-118">The call timed out.</span></span>|  
|<span data-ttu-id="1867d-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1867d-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1867d-120">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1867d-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1867d-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1867d-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1867d-122">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1867d-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1867d-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1867d-123">E_FAIL</span></span>|<span data-ttu-id="1867d-124">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1867d-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1867d-125">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1867d-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1867d-126">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1867d-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1867d-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="1867d-127">Remarks</span></span>  
 <span data-ttu-id="1867d-128">`QueueUserWorkItem` помещает рабочий элемент в очередь в рабочий поток в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="1867d-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="1867d-129">Его сигнатура и типы параметров идентичны параметрам соответствующей функции Win32, которая имеет то же имя.</span><span class="sxs-lookup"><span data-stu-id="1867d-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="1867d-130">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="1867d-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1867d-131">Требования</span><span class="sxs-lookup"><span data-stu-id="1867d-131">Requirements</span></span>  
 <span data-ttu-id="1867d-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1867d-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1867d-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1867d-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1867d-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1867d-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1867d-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1867d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1867d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="1867d-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="1867d-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="1867d-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
