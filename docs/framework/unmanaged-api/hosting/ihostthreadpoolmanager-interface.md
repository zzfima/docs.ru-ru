---
title: "Интерфейс IHostThreadPoolManager"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1cd58c53deec0a895ae6f67cccf26d2c8c2530be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="310ad-102">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="310ad-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="310ad-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для настройки пула потоков и очередь рабочих элементов в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="310ad-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="310ad-104">Методы</span><span class="sxs-lookup"><span data-stu-id="310ad-104">Methods</span></span>  
  
|<span data-ttu-id="310ad-105">Метод</span><span class="sxs-lookup"><span data-stu-id="310ad-105">Method</span></span>|<span data-ttu-id="310ad-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="310ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="310ad-107">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="310ad-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="310ad-108">Возвращает количество потоков в пуле потоков, который в настоящий момент не обрабатывает рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="310ad-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="310ad-109">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="310ad-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="310ad-110">Возвращает максимальное число потоков, поддерживаемых основным приложением одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="310ad-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="310ad-111">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="310ad-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="310ad-112">Получает минимальное количество свободных потоков, поддерживаемых основным приложением обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="310ad-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="310ad-113">Метод QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="310ad-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="310ad-114">Ставит в очередь для выполнения функции и предоставляет объект, содержащий данные для использования функцией.</span><span class="sxs-lookup"><span data-stu-id="310ad-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="310ad-115">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="310ad-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="310ad-116">Задает максимальное число потоков, которые основное приложение может хранить в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="310ad-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="310ad-117">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="310ad-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="310ad-118">Задает минимальное количество свободных потоков, которые должен поддерживать узла обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="310ad-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="310ad-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="310ad-119">Remarks</span></span>  
 <span data-ttu-id="310ad-120">Узел не требуется настраивать пул потоков, используя значения, заданные в вызовах `SetMaxThreads` и `SetMinThreads` методы.</span><span class="sxs-lookup"><span data-stu-id="310ad-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="310ad-121">В этом случае узел должен возвращать значение HRESULT E_NOTIMPL из этих методов.</span><span class="sxs-lookup"><span data-stu-id="310ad-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="310ad-122">Требования</span><span class="sxs-lookup"><span data-stu-id="310ad-122">Requirements</span></span>  
 <span data-ttu-id="310ad-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="310ad-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="310ad-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="310ad-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="310ad-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="310ad-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="310ad-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="310ad-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="310ad-127">См. также</span><span class="sxs-lookup"><span data-stu-id="310ad-127">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="310ad-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="310ad-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
