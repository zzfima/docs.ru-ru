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
ms.openlocfilehash: 7e3f8d04a47607958ff5d439b501a6de9bbc5b02
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="b2665-102">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="b2665-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="b2665-103">Предоставляет методы для уведомления узла о блокировании и разблокировании потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="b2665-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2665-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b2665-104">Methods</span></span>  
  
|<span data-ttu-id="b2665-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b2665-105">Method</span></span>|<span data-ttu-id="b2665-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b2665-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2665-107">Threadisblockingfordebugger-метод</span><span class="sxs-lookup"><span data-stu-id="b2665-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="b2665-108">Уведомляет узел, что поток, передающий данный обратный вызов о блок в службах отладки.</span><span class="sxs-lookup"><span data-stu-id="b2665-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="b2665-109">Releaseallruntimethreads-метод</span><span class="sxs-lookup"><span data-stu-id="b2665-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="b2665-110">Уведомляет узел, что службы отладки собираются разблокировать все заблокированные потоки.</span><span class="sxs-lookup"><span data-stu-id="b2665-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="b2665-111">Startblockingfordebugger-метод</span><span class="sxs-lookup"><span data-stu-id="b2665-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="b2665-112">Уведомляет узел, что службы отладки собираются начать блокирование всех потоков.</span><span class="sxs-lookup"><span data-stu-id="b2665-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2665-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b2665-113">Requirements</span></span>  
 <span data-ttu-id="b2665-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2665-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2665-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2665-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2665-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2665-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2665-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2665-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2665-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b2665-118">See Also</span></span>  
 [<span data-ttu-id="b2665-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b2665-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
