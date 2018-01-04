---
title: "Интерфейс IHostSecurityManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44f2272c0f4e1423c222a004559d7bbd58237d82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="699bd-102">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="699bd-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="699bd-103">Предоставляет методы, обеспечивающие доступ и контроль над контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="699bd-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="699bd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="699bd-104">Methods</span></span>  
  
|<span data-ttu-id="699bd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="699bd-105">Method</span></span>|<span data-ttu-id="699bd-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="699bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="699bd-107">Метод GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="699bd-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="699bd-108">Возвращает запрошенный [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) хоста.</span><span class="sxs-lookup"><span data-stu-id="699bd-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="699bd-109">Метод ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="699bd-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="699bd-110">Запросы на выполнение кода с использованием учетных данных удостоверения текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="699bd-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="699bd-111">Метод OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="699bd-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="699bd-112">Открывает маркер доступом, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="699bd-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="699bd-113">Метод RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="699bd-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="699bd-114">Завершает олицетворение удостоверения текущего пользователя и возвращает исходный маркер потока.</span><span class="sxs-lookup"><span data-stu-id="699bd-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="699bd-115">Метод SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="699bd-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="699bd-116">Задает контекст безопасности для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="699bd-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="699bd-117">Метод SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="699bd-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="699bd-118">Задает дескриптор для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="699bd-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="699bd-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="699bd-119">Remarks</span></span>  
 <span data-ttu-id="699bd-120">Узел может управлять доступом кода к маркерам потока общеязыковая среда выполнения (CLR) и пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="699bd-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="699bd-121">Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="699bd-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="699bd-122">`IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="699bd-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="699bd-123">Среда CLR обрабатывает контекста потока внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="699bd-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="699bd-124">Он запрашивает относящиеся к процессу `IHostSecurityManager` в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="699bd-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="699bd-125">В потоке метода завершения во время выполнения метода завершения.</span><span class="sxs-lookup"><span data-stu-id="699bd-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="699bd-126">Во время выполнения конструктора класса и модуля.</span><span class="sxs-lookup"><span data-stu-id="699bd-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="699bd-127">В асинхронной точках в рабочем потоке, в вызовах [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="699bd-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="699bd-128">При обслуживании портов завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="699bd-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="699bd-129">Требования</span><span class="sxs-lookup"><span data-stu-id="699bd-129">Requirements</span></span>  
 <span data-ttu-id="699bd-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="699bd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="699bd-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="699bd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="699bd-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="699bd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="699bd-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="699bd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699bd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="699bd-134">See Also</span></span>  
 [<span data-ttu-id="699bd-135">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="699bd-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="699bd-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="699bd-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
