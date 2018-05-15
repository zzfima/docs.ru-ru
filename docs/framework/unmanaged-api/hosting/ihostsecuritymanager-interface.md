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
ms.openlocfilehash: 13f60730fedef4876f81f078f811104777050175
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="bced0-102">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="bced0-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="bced0-103">Предоставляет методы, обеспечивающие доступ и контроль над контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="bced0-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bced0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bced0-104">Methods</span></span>  
  
|<span data-ttu-id="bced0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bced0-105">Method</span></span>|<span data-ttu-id="bced0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bced0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bced0-107">Метод GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="bced0-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="bced0-108">Возвращает запрошенный [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) хоста.</span><span class="sxs-lookup"><span data-stu-id="bced0-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="bced0-109">Метод ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="bced0-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="bced0-110">Запросы на выполнение кода с использованием учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="bced0-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="bced0-111">Метод OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="bced0-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="bced0-112">Открывает маркер доступом, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="bced0-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="bced0-113">Метод RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="bced0-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="bced0-114">Завершает олицетворение удостоверения текущего пользователя и возвращает исходный маркер потока.</span><span class="sxs-lookup"><span data-stu-id="bced0-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="bced0-115">Метод SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="bced0-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="bced0-116">Задает контекст безопасности для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="bced0-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="bced0-117">Метод SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="bced0-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="bced0-118">Задает дескриптор для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="bced0-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bced0-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="bced0-119">Remarks</span></span>  
 <span data-ttu-id="bced0-120">Узел может управлять доступом кода к маркерам потока общеязыковая среда выполнения (CLR) и пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="bced0-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="bced0-121">Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="bced0-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="bced0-122">`IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bced0-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="bced0-123">Среда CLR обрабатывает контекста потока внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="bced0-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="bced0-124">Он запрашивает относящиеся к процессу `IHostSecurityManager` в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="bced0-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="bced0-125">В потоке метода завершения во время выполнения метода завершения.</span><span class="sxs-lookup"><span data-stu-id="bced0-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="bced0-126">Во время выполнения конструктора класса и модуля.</span><span class="sxs-lookup"><span data-stu-id="bced0-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="bced0-127">В асинхронной точках в рабочем потоке, в вызовах [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="bced0-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="bced0-128">При обслуживании портов завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="bced0-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bced0-129">Требования</span><span class="sxs-lookup"><span data-stu-id="bced0-129">Requirements</span></span>  
 <span data-ttu-id="bced0-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bced0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bced0-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bced0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bced0-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bced0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bced0-133">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bced0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bced0-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bced0-134">See Also</span></span>  
 [<span data-ttu-id="bced0-135">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="bced0-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="bced0-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="bced0-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
