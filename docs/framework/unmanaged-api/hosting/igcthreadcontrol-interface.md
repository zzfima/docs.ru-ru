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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c00f401bedc1a2810c4e9b3046a45e53a79f1ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134268"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="cb4d3-102">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="cb4d3-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="cb4d3-103">Предоставляет методы для участия в планировании потоков, которые в противном случае был бы заблокирован для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="cb4d3-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb4d3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cb4d3-104">Methods</span></span>  
  
|<span data-ttu-id="cb4d3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cb4d3-105">Method</span></span>|<span data-ttu-id="cb4d3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cb4d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb4d3-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="cb4d3-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="cb4d3-108">Уведомляет основное приложение, что среда выполнения возобновляет выполнение после сбора мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="cb4d3-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="cb4d3-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="cb4d3-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="cb4d3-110">Уведомляет основное приложение, то, что среда выполнения начала приостановку потока для сборки мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="cb4d3-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="cb4d3-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="cb4d3-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="cb4d3-112">Уведомляет ведущее приложение, вызов которого поток заблокирован, возможно, для сбора мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="cb4d3-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb4d3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cb4d3-113">Requirements</span></span>  
 <span data-ttu-id="cb4d3-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb4d3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb4d3-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb4d3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb4d3-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb4d3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cb4d3-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cb4d3-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb4d3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cb4d3-118">See also</span></span>

- [<span data-ttu-id="cb4d3-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="cb4d3-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
