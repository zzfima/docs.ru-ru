---
title: Метод IGCThreadControl::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cd6c1dff30bce8857b9fb4092670667109932c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094090"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="5553d-102">Метод IGCThreadControl::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="5553d-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="5553d-103">Уведомляет узел, что поток, который выполняет вызов заблокирован, возможно, для сбора мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="5553d-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5553d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5553d-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="5553d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="5553d-105">Remarks</span></span>  
 <span data-ttu-id="5553d-106">Выбрать узел в пределах `ThreadIsBlockingForSuspension` обратного вызова необходимость повторного планирования потока.</span><span class="sxs-lookup"><span data-stu-id="5553d-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5553d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5553d-107">Requirements</span></span>  
 <span data-ttu-id="5553d-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5553d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5553d-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5553d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5553d-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5553d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5553d-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5553d-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5553d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5553d-112">See also</span></span>

- [<span data-ttu-id="5553d-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="5553d-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
