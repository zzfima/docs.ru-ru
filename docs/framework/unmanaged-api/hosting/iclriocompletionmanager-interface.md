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
ms.openlocfilehash: 7864bb81c3b457bf8ec07cd194d24b29a42bd441
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156069"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="28113-102">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="28113-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="28113-103">Реализует метод обратного вызова, позволяющий основному приложению уведомлять общеязыковой среды выполнения (CLR) о состоянии указанной операции ввода-вывода запросов.</span><span class="sxs-lookup"><span data-stu-id="28113-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28113-104">Методы</span><span class="sxs-lookup"><span data-stu-id="28113-104">Methods</span></span>  
  
|<span data-ttu-id="28113-105">Метод</span><span class="sxs-lookup"><span data-stu-id="28113-105">Method</span></span>|<span data-ttu-id="28113-106">Описание</span><span class="sxs-lookup"><span data-stu-id="28113-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28113-107">Метод OnComplete</span><span class="sxs-lookup"><span data-stu-id="28113-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="28113-108">Уведомляет среду CLR о состоянии запроса ввода-вывода, которые были выполнены с помощью вызова [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="28113-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28113-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="28113-109">Remarks</span></span>  
 <span data-ttu-id="28113-110">Сервер реализует интерфейс абстракции завершения ввода-вывода с помощью [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="28113-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="28113-111">Среда CLR выполняет запросы ввода-вывода через этот интерфейс, и основное приложение уведомляет среду выполнения о результатах такого запроса с помощью `ICLRIoCompletionManager` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="28113-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28113-112">Требования</span><span class="sxs-lookup"><span data-stu-id="28113-112">Requirements</span></span>  
 <span data-ttu-id="28113-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28113-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28113-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28113-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28113-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28113-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="28113-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="28113-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28113-117">См. также</span><span class="sxs-lookup"><span data-stu-id="28113-117">See also</span></span>

- [<span data-ttu-id="28113-118">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="28113-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="28113-119">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="28113-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="28113-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="28113-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
