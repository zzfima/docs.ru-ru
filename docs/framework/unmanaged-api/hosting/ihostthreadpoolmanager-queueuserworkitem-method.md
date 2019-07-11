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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12c571f478f15a0b72168977f12623be1c4a08a9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749161"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="47286-102">Метод IHostThreadPoolManager::QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="47286-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="47286-103">Помещает в очередь для выполнения функции и указывает объект, содержащий данные, используемые этой функцией.</span><span class="sxs-lookup"><span data-stu-id="47286-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="47286-104">Функция выполняется, когда поток не станет доступным.</span><span class="sxs-lookup"><span data-stu-id="47286-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47286-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47286-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47286-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="47286-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="47286-107">[in] Указатель на функцию, который представляет функцию для выполнения.</span><span class="sxs-lookup"><span data-stu-id="47286-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="47286-108">[in] Объект, содержащий данные для использования с `Function`.</span><span class="sxs-lookup"><span data-stu-id="47286-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="47286-109">[in] Один из флагов значения, как это определено для Win32 `QueueUserWorkItem` метод, который управляет выполнением.</span><span class="sxs-lookup"><span data-stu-id="47286-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47286-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47286-110">Return Value</span></span>  
  
|<span data-ttu-id="47286-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47286-111">HRESULT</span></span>|<span data-ttu-id="47286-112">Описание</span><span class="sxs-lookup"><span data-stu-id="47286-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47286-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="47286-113">S_OK</span></span>|<span data-ttu-id="47286-114">`QueueUserWorkItem` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="47286-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="47286-115">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47286-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47286-116">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="47286-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47286-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47286-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47286-118">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="47286-118">The call timed out.</span></span>|  
|<span data-ttu-id="47286-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47286-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47286-120">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="47286-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47286-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47286-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47286-122">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="47286-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47286-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47286-123">E_FAIL</span></span>|<span data-ttu-id="47286-124">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="47286-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47286-125">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="47286-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47286-126">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="47286-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47286-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="47286-127">Remarks</span></span>  
 <span data-ttu-id="47286-128">`QueueUserWorkItem` ставит в очередь рабочий элемент в рабочий поток в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="47286-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="47286-129">Его сигнатура и типы параметров идентичны соответствующей функции Win32, которая имеет то же имя.</span><span class="sxs-lookup"><span data-stu-id="47286-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="47286-130">Дополнительные сведения см. в документации платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="47286-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47286-131">Требования</span><span class="sxs-lookup"><span data-stu-id="47286-131">Requirements</span></span>  
 <span data-ttu-id="47286-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47286-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47286-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="47286-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47286-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47286-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47286-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47286-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47286-136">См. также</span><span class="sxs-lookup"><span data-stu-id="47286-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="47286-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="47286-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
