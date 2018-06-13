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
ms.openlocfilehash: d0986645a8ce4076c27f39f2ae8004ef20bb4bdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437756"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="7d5ca-102">Метод IGCThreadControl::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="7d5ca-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="7d5ca-103">Уведомляет узел, что среда выполнения возобновляет выполнение после сборки мусора или по другой причине.</span><span class="sxs-lookup"><span data-stu-id="7d5ca-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d5ca-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d5ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d5ca-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="7d5ca-106">[in] Поколение, для которого был выполнен сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="7d5ca-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d5ca-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d5ca-107">Remarks</span></span>  
 <span data-ttu-id="7d5ca-108">Не следует перепланировать каких-либо потоков во время `SuspensionEnding` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="7d5ca-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5ca-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7d5ca-109">Requirements</span></span>  
 <span data-ttu-id="7d5ca-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d5ca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d5ca-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d5ca-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d5ca-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d5ca-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d5ca-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d5ca-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5ca-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7d5ca-114">See Also</span></span>  
 [<span data-ttu-id="7d5ca-115">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="7d5ca-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
