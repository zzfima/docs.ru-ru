---
title: "Интерфейс ICLRIoCompletionManager"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99dc183674abaff33047f070c14794150a8615f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="0d843-102">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="0d843-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="0d843-103">Реализует метод обратного вызова, позволяющий основному приложению уведомлять общеязыковой среды выполнения (CLR) состояния указанного операций ввода-вывода запросов.</span><span class="sxs-lookup"><span data-stu-id="0d843-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d843-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0d843-104">Methods</span></span>  
  
|<span data-ttu-id="0d843-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0d843-105">Method</span></span>|<span data-ttu-id="0d843-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="0d843-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d843-107">Метод OnComplete</span><span class="sxs-lookup"><span data-stu-id="0d843-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="0d843-108">Уведомляет среду CLR о состоянии запроса ввода-вывода, внесенных с помощью вызова [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0d843-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d843-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d843-109">Remarks</span></span>  
 <span data-ttu-id="0d843-110">Основное приложение реализует абстракцию завершения ввода-вывода с помощью [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d843-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="0d843-111">Среда CLR выполняет запросы ввода-вывода через этот интерфейс, и основное приложение уведомляет среду выполнения о результатах такого запроса с помощью `ICLRIoCompletionManager` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d843-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d843-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0d843-112">Requirements</span></span>  
 <span data-ttu-id="0d843-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d843-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d843-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d843-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d843-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d843-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d843-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d843-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d843-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0d843-117">See Also</span></span>  
 [<span data-ttu-id="0d843-118">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="0d843-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="0d843-119">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="0d843-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="0d843-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0d843-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
