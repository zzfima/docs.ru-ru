---
title: Интерфейс IHostThreadPoolManager
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e7976740a79efda8e5ab569f2efb55444012c5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220374"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="99fd5-102">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="99fd5-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="99fd5-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для настройки пула потоков и очередь рабочих элементов в пул потоков.</span><span class="sxs-lookup"><span data-stu-id="99fd5-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99fd5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="99fd5-104">Methods</span></span>  
  
|<span data-ttu-id="99fd5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="99fd5-105">Method</span></span>|<span data-ttu-id="99fd5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="99fd5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99fd5-107">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="99fd5-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="99fd5-108">Получает количество потоков в пуле потоков, который в настоящий момент не обрабатывает рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="99fd5-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="99fd5-109">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="99fd5-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="99fd5-110">Возвращает максимальное число потоков, ведущий одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="99fd5-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="99fd5-111">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="99fd5-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="99fd5-112">Получает минимальное количество свободных потоков, ведущий обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="99fd5-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="99fd5-113">Метод QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="99fd5-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="99fd5-114">Помещает в очередь для выполнения функции и предоставляет объект, содержащий данные, используемые функцией.</span><span class="sxs-lookup"><span data-stu-id="99fd5-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="99fd5-115">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="99fd5-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="99fd5-116">Задает максимальное количество потоков, основное приложение может хранить в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="99fd5-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="99fd5-117">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="99fd5-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="99fd5-118">Задает минимальное количество свободных потоков, которые необходимо поддерживать узел обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="99fd5-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99fd5-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="99fd5-119">Remarks</span></span>  
 <span data-ttu-id="99fd5-120">Узел не требуется настраивать пул потоков, используя значения, заданные в вызовах `SetMaxThreads` и `SetMinThreads` методы.</span><span class="sxs-lookup"><span data-stu-id="99fd5-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="99fd5-121">В этом случае узел должен возвращать значение HRESULT E_NOTIMPL из этих методов.</span><span class="sxs-lookup"><span data-stu-id="99fd5-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99fd5-122">Требования</span><span class="sxs-lookup"><span data-stu-id="99fd5-122">Requirements</span></span>  
 <span data-ttu-id="99fd5-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99fd5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99fd5-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99fd5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99fd5-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99fd5-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="99fd5-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="99fd5-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99fd5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="99fd5-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="99fd5-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="99fd5-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
