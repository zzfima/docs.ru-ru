---
title: Метод IGCThreadControl::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cb58593a30b855c9fabf55a6ca0a50886dc371f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779484"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="5d043-102">Метод IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="5d043-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="5d043-103">Уведомляет основное приложение, то, что среда выполнения начала приостановку потока для сборки мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="5d043-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d043-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d043-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="5d043-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d043-105">Remarks</span></span>  
 <span data-ttu-id="5d043-106">Не повторного планирования во время обсуждения `SuspensionStarting` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5d043-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d043-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5d043-107">Requirements</span></span>  
 <span data-ttu-id="5d043-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d043-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d043-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d043-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d043-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d043-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d043-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d043-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d043-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5d043-112">See also</span></span>

- [<span data-ttu-id="5d043-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="5d043-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
