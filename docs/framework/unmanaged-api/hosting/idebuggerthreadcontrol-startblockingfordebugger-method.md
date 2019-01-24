---
title: Метод IDebuggerThreadControl::StartBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 746b61a303869ff03d41cd6005ca0f5635ac0fd5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521729"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="a41f9-102">Метод IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="a41f9-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="a41f9-103">Уведомляет основное приложение, что службы отладки будут вскоре запущены блокировку всех потоков.</span><span class="sxs-lookup"><span data-stu-id="a41f9-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a41f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a41f9-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a41f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a41f9-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="a41f9-106">[in] Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="a41f9-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a41f9-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a41f9-107">Remarks</span></span>  
 <span data-ttu-id="a41f9-108">`StartBlockingForDebugger` Метод может вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a41f9-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a41f9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a41f9-109">Requirements</span></span>  
 <span data-ttu-id="a41f9-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a41f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a41f9-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a41f9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a41f9-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a41f9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a41f9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a41f9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41f9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a41f9-114">See also</span></span>
- [<span data-ttu-id="a41f9-115">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="a41f9-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
