---
title: Интерфейс IHostSecurityManager
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2c71f32dfd190e188bb28aad5d51c72160eb4bc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603230"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="211a1-102">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="211a1-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="211a1-103">Предоставляет методы, разрешающие доступ к и контроль над контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="211a1-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="211a1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="211a1-104">Methods</span></span>  
  
|<span data-ttu-id="211a1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="211a1-105">Method</span></span>|<span data-ttu-id="211a1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="211a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="211a1-107">Метод GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="211a1-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="211a1-108">Возвращает запрашиваемый [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) с узла.</span><span class="sxs-lookup"><span data-stu-id="211a1-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="211a1-109">Метод ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="211a1-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="211a1-110">Запросы на выполнение кода с использованием учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="211a1-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="211a1-111">Метод OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="211a1-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="211a1-112">Открывает токена доступа на уровне пользователей, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="211a1-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="211a1-113">Метод RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="211a1-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="211a1-114">Завершает олицетворение удостоверения текущего пользователя и возвращает исходный маркер потока.</span><span class="sxs-lookup"><span data-stu-id="211a1-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="211a1-115">Метод SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="211a1-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="211a1-116">Задает контекст безопасности для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="211a1-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="211a1-117">Метод SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="211a1-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="211a1-118">Задает дескриптор для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="211a1-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="211a1-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="211a1-119">Remarks</span></span>  
 <span data-ttu-id="211a1-120">Узел может управлять всем доступ кода к маркерам потока как среда CLR (CLR), так и пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="211a1-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="211a1-121">Также можно обеспечить, полную безопасность сведений о контексте передается через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="211a1-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="211a1-122">`IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, который является непрозрачным для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="211a1-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="211a1-123">Среда CLR обрабатывает контекста потока внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="211a1-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="211a1-124">Он запрашивает относящиеся к процессу `IHostSecurityManager` в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="211a1-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="211a1-125">В потоке метода завершения, во время выполнения метода завершения.</span><span class="sxs-lookup"><span data-stu-id="211a1-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="211a1-126">Во время выполнения конструктор класса и модуля.</span><span class="sxs-lookup"><span data-stu-id="211a1-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="211a1-127">В асинхронные точки в рабочем потоке, в вызовах [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="211a1-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="211a1-128">При обслуживании портов завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="211a1-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="211a1-129">Требования</span><span class="sxs-lookup"><span data-stu-id="211a1-129">Requirements</span></span>  
 <span data-ttu-id="211a1-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="211a1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="211a1-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="211a1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="211a1-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="211a1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="211a1-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="211a1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211a1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="211a1-134">See also</span></span>

- [<span data-ttu-id="211a1-135">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="211a1-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="211a1-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="211a1-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
