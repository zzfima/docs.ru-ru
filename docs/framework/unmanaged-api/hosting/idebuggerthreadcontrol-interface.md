---
title: "Интерфейс IDebuggerThreadControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IDebuggerThreadControl
helpviewer_keywords: IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 297a66f9466b00dec4d32f7d8a6e2bd13b6e5655
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="0fd2b-102">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="0fd2b-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="0fd2b-103">Предоставляет методы для уведомления узла о блокировании и разблокировании потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="0fd2b-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0fd2b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0fd2b-104">Methods</span></span>  
  
|<span data-ttu-id="0fd2b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0fd2b-105">Method</span></span>|<span data-ttu-id="0fd2b-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="0fd2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0fd2b-107">Метод ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="0fd2b-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="0fd2b-108">Уведомляет узел, что поток, передающий данный обратный вызов о блок в службах отладки.</span><span class="sxs-lookup"><span data-stu-id="0fd2b-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="0fd2b-109">Метод ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="0fd2b-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="0fd2b-110">Уведомляет узел, что службы отладки собираются разблокировать все заблокированные потоки.</span><span class="sxs-lookup"><span data-stu-id="0fd2b-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="0fd2b-111">Метод StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="0fd2b-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="0fd2b-112">Уведомляет узел, что службы отладки собираются начать блокирование всех потоков.</span><span class="sxs-lookup"><span data-stu-id="0fd2b-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fd2b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0fd2b-113">Requirements</span></span>  
 <span data-ttu-id="0fd2b-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fd2b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fd2b-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0fd2b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0fd2b-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0fd2b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0fd2b-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fd2b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd2b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0fd2b-118">See Also</span></span>  
 [<span data-ttu-id="0fd2b-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0fd2b-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
