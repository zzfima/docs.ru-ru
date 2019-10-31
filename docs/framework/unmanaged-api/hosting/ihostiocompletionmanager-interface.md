---
title: Интерфейс IHostIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133851"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="6ef12-102">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="6ef12-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="6ef12-103">Предоставляет методы, позволяющие среде CLR взаимодействовать с портами завершения ввода-вывода, предоставляемыми узлом.</span><span class="sxs-lookup"><span data-stu-id="6ef12-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ef12-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6ef12-104">Methods</span></span>  
  
|<span data-ttu-id="6ef12-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6ef12-105">Method</span></span>|<span data-ttu-id="6ef12-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6ef12-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ef12-107">Метод Bind</span><span class="sxs-lookup"><span data-stu-id="6ef12-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="6ef12-108">Привязывает маркер к порту завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="6ef12-109">Метод CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="6ef12-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="6ef12-110">Закрывает порт, созданный с помощью предыдущего вызова метода `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="6ef12-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="6ef12-111">Метод CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="6ef12-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="6ef12-112">Запрашивает создание узлом нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="6ef12-113">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="6ef12-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="6ef12-114">Возвращает число потоков завершения ввода-вывода, которые в настоящий момент не обрабатывают запросы.</span><span class="sxs-lookup"><span data-stu-id="6ef12-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="6ef12-115">Метод GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="6ef12-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="6ef12-116">Возвращает размер любых пользовательских данных, которые узел намеревается добавить к запросам ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="6ef12-117">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="6ef12-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="6ef12-118">Возвращает максимальное число потоков, которое узел может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="6ef12-119">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="6ef12-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="6ef12-120">Возвращает минимальное число потоков, предоставляемых узлом для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="6ef12-121">Метод InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="6ef12-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="6ef12-122">Предоставляет узлу возможность инициализировать любые пользовательские данные о запросе ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="6ef12-123">Метод SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="6ef12-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="6ef12-124">Предоставляет узлу указатель интерфейса на экземпляр [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) , РЕАЛИЗУЕМый средой CLR.</span><span class="sxs-lookup"><span data-stu-id="6ef12-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="6ef12-125">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="6ef12-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="6ef12-126">Задает максимальное число потоков, которое узел запрашивает для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="6ef12-127">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="6ef12-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="6ef12-128">Задает минимальное число потоков, которое узел должен выделить при завершении ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ef12-129">Заметки</span><span class="sxs-lookup"><span data-stu-id="6ef12-129">Remarks</span></span>  
 <span data-ttu-id="6ef12-130">`IHostIoCompletionManager` соответствует интерфейсу `ICLRIoCompletionManager`, реализуемому средой CLR.</span><span class="sxs-lookup"><span data-stu-id="6ef12-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="6ef12-131">Среда CLR вызывает методы `IHostIoCompletionManager` для привязки дескрипторов к портам, предоставляемым узлом, и узел вызывает методы `ICLRIoCompletionManager`, чтобы сообщить о завершении запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="6ef12-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef12-132">Требования</span><span class="sxs-lookup"><span data-stu-id="6ef12-132">Requirements</span></span>  
 <span data-ttu-id="6ef12-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ef12-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef12-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6ef12-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ef12-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6ef12-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ef12-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef12-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef12-137">См. также</span><span class="sxs-lookup"><span data-stu-id="6ef12-137">See also</span></span>

- [<span data-ttu-id="6ef12-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6ef12-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
