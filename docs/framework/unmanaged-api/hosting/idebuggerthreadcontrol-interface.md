---
title: Интерфейс IDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a551d3cc6ab3dd3887f232018f8201de4036d1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096840"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="51d3a-102">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="51d3a-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="51d3a-103">Предоставляет методы для уведомления узла о блокировании и разблокировании потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="51d3a-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51d3a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="51d3a-104">Methods</span></span>  
  
|<span data-ttu-id="51d3a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="51d3a-105">Method</span></span>|<span data-ttu-id="51d3a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="51d3a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51d3a-107">Метод ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="51d3a-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="51d3a-108">Уведомляет основное приложение, что поток, который отправляет этот обратный вызов о блок в службах отладки.</span><span class="sxs-lookup"><span data-stu-id="51d3a-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="51d3a-109">Метод ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="51d3a-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="51d3a-110">Уведомляет основное приложение, что службы отладки должны освободить все потоки, которые заблокированы.</span><span class="sxs-lookup"><span data-stu-id="51d3a-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="51d3a-111">Метод StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="51d3a-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="51d3a-112">Уведомляет основное приложение, что службы отладки будут вскоре запущены блокировку всех потоков.</span><span class="sxs-lookup"><span data-stu-id="51d3a-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51d3a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="51d3a-113">Requirements</span></span>  
 <span data-ttu-id="51d3a-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51d3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51d3a-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51d3a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51d3a-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51d3a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="51d3a-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="51d3a-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51d3a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="51d3a-118">See also</span></span>

- [<span data-ttu-id="51d3a-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="51d3a-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
