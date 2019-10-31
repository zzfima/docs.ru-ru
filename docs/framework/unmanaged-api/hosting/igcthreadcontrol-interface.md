---
title: Интерфейс IGCThreadControl
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134802"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="e321b-102">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="e321b-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="e321b-103">Предоставляет методы для участия в планировании потоков, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e321b-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e321b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e321b-104">Methods</span></span>  
  
|<span data-ttu-id="e321b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e321b-105">Method</span></span>|<span data-ttu-id="e321b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e321b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e321b-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="e321b-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="e321b-108">Уведомляет узел о том, что среда выполнения возобновляет потоки после сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="e321b-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="e321b-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="e321b-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="e321b-110">Уведомляет узел о том, что среда выполнения начинает приостановку потока для сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="e321b-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="e321b-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="e321b-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="e321b-112">Уведомляет узел о том, что поток, выполняющий вызов, будет заблокирован, возможно, для сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="e321b-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e321b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e321b-113">Requirements</span></span>  
 <span data-ttu-id="e321b-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e321b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e321b-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e321b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e321b-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e321b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e321b-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e321b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e321b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e321b-118">See also</span></span>

- [<span data-ttu-id="e321b-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e321b-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
