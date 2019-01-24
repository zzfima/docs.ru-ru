---
title: Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5e2501a5ab62c6aaef2b3f754f9eed10e4e4b97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505030"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="39e6d-102">Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="39e6d-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="39e6d-103">Уведомляет основное приложение, что службы отладки должны освободить все потоки, которые заблокированы.</span><span class="sxs-lookup"><span data-stu-id="39e6d-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39e6d-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="39e6d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="39e6d-105">Remarks</span></span>  
 <span data-ttu-id="39e6d-106">`ReleaseAllRuntimeThreads` Метод никогда не будет вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="39e6d-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="39e6d-107">Если узел имеет среды выполнения поток заблокирован, он должен освободить теперь.</span><span class="sxs-lookup"><span data-stu-id="39e6d-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39e6d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="39e6d-108">Requirements</span></span>  
 <span data-ttu-id="39e6d-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39e6d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39e6d-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39e6d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39e6d-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39e6d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39e6d-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39e6d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e6d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="39e6d-113">See also</span></span>
- [<span data-ttu-id="39e6d-114">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="39e6d-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
