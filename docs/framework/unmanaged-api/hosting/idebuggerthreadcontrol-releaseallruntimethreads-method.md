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
ms.openlocfilehash: 09895294c4678cdb1dd033076cfb42853aa06b2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780506"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="be32f-102">Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="be32f-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="be32f-103">Уведомляет основное приложение, что службы отладки должны освободить все потоки, которые заблокированы.</span><span class="sxs-lookup"><span data-stu-id="be32f-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be32f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be32f-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="be32f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="be32f-105">Remarks</span></span>  
 <span data-ttu-id="be32f-106">`ReleaseAllRuntimeThreads` Метод никогда не будет вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="be32f-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="be32f-107">Если узел имеет среды выполнения поток заблокирован, он должен освободить теперь.</span><span class="sxs-lookup"><span data-stu-id="be32f-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be32f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="be32f-108">Requirements</span></span>  
 <span data-ttu-id="be32f-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be32f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be32f-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be32f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be32f-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="be32f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be32f-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be32f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be32f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="be32f-113">See also</span></span>

- [<span data-ttu-id="be32f-114">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="be32f-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
