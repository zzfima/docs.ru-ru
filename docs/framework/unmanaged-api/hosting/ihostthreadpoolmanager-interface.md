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
ms.openlocfilehash: 92097cdf735630f3537296f188bd83ea8162add2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="c7104-102">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="c7104-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="c7104-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для настройки пула потоков и очередь рабочих элементов в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="c7104-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7104-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c7104-104">Methods</span></span>  
  
|<span data-ttu-id="c7104-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c7104-105">Method</span></span>|<span data-ttu-id="c7104-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c7104-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7104-107">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="c7104-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="c7104-108">Возвращает количество потоков в пуле потоков, который в настоящий момент не обрабатывает рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="c7104-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="c7104-109">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c7104-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="c7104-110">Возвращает максимальное число потоков, поддерживаемых основным приложением одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="c7104-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="c7104-111">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="c7104-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="c7104-112">Получает минимальное количество свободных потоков, поддерживаемых основным приложением обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="c7104-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="c7104-113">Метод QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="c7104-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="c7104-114">Ставит в очередь для выполнения функции и предоставляет объект, содержащий данные для использования функцией.</span><span class="sxs-lookup"><span data-stu-id="c7104-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="c7104-115">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c7104-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="c7104-116">Задает максимальное число потоков, которые основное приложение может хранить в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="c7104-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="c7104-117">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="c7104-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="c7104-118">Задает минимальное количество свободных потоков, которые должен поддерживать узла обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="c7104-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7104-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7104-119">Remarks</span></span>  
 <span data-ttu-id="c7104-120">Узел не требуется настраивать пул потоков, используя значения, заданные в вызовах `SetMaxThreads` и `SetMinThreads` методы.</span><span class="sxs-lookup"><span data-stu-id="c7104-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="c7104-121">В этом случае узел должен возвращать значение HRESULT E_NOTIMPL из этих методов.</span><span class="sxs-lookup"><span data-stu-id="c7104-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7104-122">Требования</span><span class="sxs-lookup"><span data-stu-id="c7104-122">Requirements</span></span>  
 <span data-ttu-id="c7104-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7104-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7104-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7104-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7104-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7104-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7104-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7104-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7104-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c7104-127">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="c7104-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c7104-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
