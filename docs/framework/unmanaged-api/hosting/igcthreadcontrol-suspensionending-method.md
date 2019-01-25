---
title: Метод IGCThreadControl::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d77380e35d8f5eee1e50b1030493e0b17cbadfba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713292"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="6626f-102">Метод IGCThreadControl::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="6626f-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="6626f-103">Уведомляет основное приложение, что среда выполнения возобновляет выполнение после сбора мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="6626f-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6626f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6626f-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6626f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6626f-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="6626f-106">[in] Поколение, для которого был выполнен сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="6626f-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6626f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6626f-107">Remarks</span></span>  
 <span data-ttu-id="6626f-108">Не повторного планирования во время обсуждения `SuspensionEnding` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="6626f-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6626f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6626f-109">Requirements</span></span>  
 <span data-ttu-id="6626f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6626f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6626f-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6626f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6626f-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6626f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6626f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6626f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6626f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6626f-114">See also</span></span>
- [<span data-ttu-id="6626f-115">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="6626f-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
