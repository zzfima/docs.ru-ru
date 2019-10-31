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
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141028"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="26078-102">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="26078-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="26078-103">Реализует метод обратного вызова, который позволяет узлу уведомлять среду CLR о состоянии указанных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="26078-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26078-104">Методы</span><span class="sxs-lookup"><span data-stu-id="26078-104">Methods</span></span>  
  
|<span data-ttu-id="26078-105">Метод</span><span class="sxs-lookup"><span data-stu-id="26078-105">Method</span></span>|<span data-ttu-id="26078-106">Описание</span><span class="sxs-lookup"><span data-stu-id="26078-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26078-107">Метод OnComplete</span><span class="sxs-lookup"><span data-stu-id="26078-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="26078-108">Сообщает среде CLR о состоянии запроса ввода-вывода, сделанного с помощью вызова метода [IHostIoCompletionManager:: BIND](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="26078-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26078-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="26078-109">Remarks</span></span>  
 <span data-ttu-id="26078-110">Узел реализует абстракцию завершения ввода-вывода с помощью интерфейса [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="26078-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="26078-111">Среда CLR делает запросы ввода-вывода через этот интерфейс, и узел уведомляет среду выполнения о результатах таких запросов с помощью интерфейса `ICLRIoCompletionManager`.</span><span class="sxs-lookup"><span data-stu-id="26078-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26078-112">Требования</span><span class="sxs-lookup"><span data-stu-id="26078-112">Requirements</span></span>  
 <span data-ttu-id="26078-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26078-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26078-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="26078-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26078-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="26078-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26078-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26078-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26078-117">См. также</span><span class="sxs-lookup"><span data-stu-id="26078-117">See also</span></span>

- [<span data-ttu-id="26078-118">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="26078-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="26078-119">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="26078-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="26078-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="26078-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
