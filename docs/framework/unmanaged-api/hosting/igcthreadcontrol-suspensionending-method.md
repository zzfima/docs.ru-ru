---
title: "Метод IGCThreadControl::SuspensionEnding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4460d2b0eaf10d20ddd0c3641279a8ffc05c245
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="1752c-102">Метод IGCThreadControl::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="1752c-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="1752c-103">Уведомляет узел, что среда выполнения возобновляет выполнение после сборки мусора или по другой причине.</span><span class="sxs-lookup"><span data-stu-id="1752c-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1752c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1752c-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1752c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1752c-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="1752c-106">[in] Поколение, для которого был выполнен сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="1752c-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1752c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1752c-107">Remarks</span></span>  
 <span data-ttu-id="1752c-108">Не следует перепланировать каких-либо потоков во время `SuspensionEnding` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="1752c-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1752c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1752c-109">Requirements</span></span>  
 <span data-ttu-id="1752c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1752c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1752c-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1752c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1752c-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1752c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1752c-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1752c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1752c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1752c-114">See Also</span></span>  
 [<span data-ttu-id="1752c-115">Igcthreadcontrol-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1752c-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
