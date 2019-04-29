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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c3bebe8eabd4d5fd5faec21e0b0efc408353bc2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796836"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="2357f-102">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2357f-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="2357f-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с помощью портов завершения ввода-вывода, предоставленный средой размещения.</span><span class="sxs-lookup"><span data-stu-id="2357f-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2357f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2357f-104">Methods</span></span>  
  
|<span data-ttu-id="2357f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2357f-105">Method</span></span>|<span data-ttu-id="2357f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2357f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2357f-107">Метод Bind</span><span class="sxs-lookup"><span data-stu-id="2357f-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="2357f-108">Привязывает дескриптор к порту завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="2357f-109">Метод CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="2357f-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="2357f-110">Закрывает порт, который был создан при помощи предыдущими вызовами `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="2357f-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="2357f-111">Метод CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="2357f-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="2357f-112">Запросы на создание нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="2357f-113">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="2357f-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="2357f-114">Получает количество потоков завершения ввода-вывода, которые в настоящий момент не обрабатывает запросы.</span><span class="sxs-lookup"><span data-stu-id="2357f-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="2357f-115">Метод GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="2357f-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="2357f-116">Получает размер любых пользовательских данных, которые узел должен добавить запросы ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="2357f-117">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="2357f-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="2357f-118">Возвращает максимальное число потоков, которые основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="2357f-119">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="2357f-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="2357f-120">Получает минимальное количество потоков, предоставляемых хостом для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="2357f-121">Метод InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="2357f-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="2357f-122">Узел предоставляет пользователям возможность инициализировать любые пользовательские данные о запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="2357f-123">Метод SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2357f-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="2357f-124">Предоставляет указатель интерфейса на узле [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемых средой CLR.</span><span class="sxs-lookup"><span data-stu-id="2357f-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="2357f-125">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="2357f-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="2357f-126">Задает максимальное количество потоков, выделяемых основным приложением для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="2357f-127">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="2357f-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="2357f-128">Задает минимальное количество потоков, которые основное приложение должно выделить для завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2357f-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="2357f-129">Remarks</span></span>  
 <span data-ttu-id="2357f-130">`IHostIoCompletionManager` соответствует `ICLRIoCompletionManager` интерфейс, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="2357f-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="2357f-131">Среда CLR вызывает методы `IHostIoCompletionManager` для привязки к портам, которые предоставляет узел и узел вызывает методы дескрипторы `ICLRIoCompletionManager` для сообщает о завершении запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2357f-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2357f-132">Требования</span><span class="sxs-lookup"><span data-stu-id="2357f-132">Requirements</span></span>  
 <span data-ttu-id="2357f-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2357f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2357f-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2357f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2357f-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2357f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2357f-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2357f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2357f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="2357f-137">See also</span></span>

- [<span data-ttu-id="2357f-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="2357f-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
