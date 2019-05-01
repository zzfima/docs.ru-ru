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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992775"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="acd5a-102">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="acd5a-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="acd5a-103">Предоставляет методы для участия в планировании потоков, которые в противном случае был бы заблокирован для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="acd5a-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acd5a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="acd5a-104">Methods</span></span>  
  
|<span data-ttu-id="acd5a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="acd5a-105">Method</span></span>|<span data-ttu-id="acd5a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="acd5a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acd5a-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="acd5a-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="acd5a-108">Уведомляет основное приложение, что среда выполнения возобновляет выполнение после сбора мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="acd5a-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="acd5a-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="acd5a-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="acd5a-110">Уведомляет основное приложение, то, что среда выполнения начала приостановку потока для сборки мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="acd5a-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="acd5a-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="acd5a-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="acd5a-112">Уведомляет ведущее приложение, вызов которого поток заблокирован, возможно, для сбора мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="acd5a-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acd5a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="acd5a-113">Requirements</span></span>  
 <span data-ttu-id="acd5a-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acd5a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acd5a-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="acd5a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acd5a-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acd5a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acd5a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acd5a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd5a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="acd5a-118">See also</span></span>

- [<span data-ttu-id="acd5a-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="acd5a-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
