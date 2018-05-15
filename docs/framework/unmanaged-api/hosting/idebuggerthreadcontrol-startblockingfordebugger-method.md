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
ms.openlocfilehash: 48aa7452373f83465b3e5ec8a09a9a00c902a22c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="2421e-102">Метод IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="2421e-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="2421e-103">Уведомляет узел, что службы отладки собираются начать блокирование всех потоков.</span><span class="sxs-lookup"><span data-stu-id="2421e-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2421e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2421e-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2421e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2421e-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="2421e-106">[in] Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2421e-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2421e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2421e-107">Remarks</span></span>  
 <span data-ttu-id="2421e-108">`StartBlockingForDebugger` Можно вызвать метод в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2421e-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2421e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2421e-109">Requirements</span></span>  
 <span data-ttu-id="2421e-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2421e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2421e-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2421e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2421e-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2421e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2421e-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2421e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2421e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2421e-114">See Also</span></span>  
 [<span data-ttu-id="2421e-115">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="2421e-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
