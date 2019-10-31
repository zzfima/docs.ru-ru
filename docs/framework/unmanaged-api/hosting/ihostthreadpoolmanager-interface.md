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
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122085"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="545db-102">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="545db-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="545db-103">Предоставляет методы, позволяющие среде CLR настроить пул потоков и поместить рабочие элементы в очередь в пул потоков.</span><span class="sxs-lookup"><span data-stu-id="545db-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="545db-104">Методы</span><span class="sxs-lookup"><span data-stu-id="545db-104">Methods</span></span>  
  
|<span data-ttu-id="545db-105">Метод</span><span class="sxs-lookup"><span data-stu-id="545db-105">Method</span></span>|<span data-ttu-id="545db-106">Описание</span><span class="sxs-lookup"><span data-stu-id="545db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="545db-107">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="545db-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="545db-108">Возвращает число потоков в пуле потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="545db-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="545db-109">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="545db-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="545db-110">Возвращает максимальное число потоков, которые обслуживается одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="545db-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="545db-111">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="545db-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="545db-112">Возвращает минимальное число бездействующих потоков, поддерживаемых узлом в ожидаемых запросах.</span><span class="sxs-lookup"><span data-stu-id="545db-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="545db-113">Метод QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="545db-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="545db-114">Ставит в очередь функцию для выполнения и предоставляет объект, содержащий данные, которые будут использоваться функцией.</span><span class="sxs-lookup"><span data-stu-id="545db-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="545db-115">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="545db-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="545db-116">Задает максимальное число потоков, которые узел может поддерживать в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="545db-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="545db-117">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="545db-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="545db-118">Задает минимальное число бездействующих потоков, которые должны поддерживаться узлом в ожидаемых запросах.</span><span class="sxs-lookup"><span data-stu-id="545db-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="545db-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="545db-119">Remarks</span></span>  
 <span data-ttu-id="545db-120">Узел не требуется для настройки пула потоков с использованием значений, указанных в вызовах методов `SetMaxThreads` и `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="545db-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="545db-121">В этом случае узел должен возвратить из этих методов значение HRESULT, равное E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="545db-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="545db-122">Требования</span><span class="sxs-lookup"><span data-stu-id="545db-122">Requirements</span></span>  
 <span data-ttu-id="545db-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="545db-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="545db-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="545db-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="545db-125">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="545db-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="545db-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="545db-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="545db-127">См. также</span><span class="sxs-lookup"><span data-stu-id="545db-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="545db-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="545db-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
