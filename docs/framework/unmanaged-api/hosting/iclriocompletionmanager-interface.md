---
title: Интерфейс ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b71c177c7c0cb029fb7cfa734f54c87abf20b348
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557842"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="d951d-102">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="d951d-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="d951d-103">Реализует метод обратного вызова, позволяющий основному приложению уведомлять общеязыковой среды выполнения (CLR) о состоянии указанной операции ввода-вывода запросов.</span><span class="sxs-lookup"><span data-stu-id="d951d-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d951d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d951d-104">Methods</span></span>  
  
|<span data-ttu-id="d951d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d951d-105">Method</span></span>|<span data-ttu-id="d951d-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="d951d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d951d-107">Метод OnComplete</span><span class="sxs-lookup"><span data-stu-id="d951d-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="d951d-108">Уведомляет среду CLR о состоянии запроса ввода-вывода, которые были выполнены с помощью вызова [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d951d-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d951d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d951d-109">Remarks</span></span>  
 <span data-ttu-id="d951d-110">Сервер реализует интерфейс абстракции завершения ввода-вывода с помощью [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d951d-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="d951d-111">Среда CLR выполняет запросы ввода-вывода через этот интерфейс, и основное приложение уведомляет среду выполнения о результатах такого запроса с помощью `ICLRIoCompletionManager` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d951d-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d951d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d951d-112">Requirements</span></span>  
 <span data-ttu-id="d951d-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d951d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d951d-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d951d-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d951d-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d951d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d951d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d951d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d951d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d951d-117">See also</span></span>
- [<span data-ttu-id="d951d-118">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="d951d-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="d951d-119">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="d951d-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="d951d-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d951d-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
