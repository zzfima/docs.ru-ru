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
ms.openlocfilehash: 9ae1aa6590366468166916e6a92d0b356eb37c27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133143"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="0cdbb-102">Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="0cdbb-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="0cdbb-103">Уведомляет узел о том, что службы отладки собирается освободить все заблокированные потоки.</span><span class="sxs-lookup"><span data-stu-id="0cdbb-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cdbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cdbb-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="0cdbb-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="0cdbb-105">Remarks</span></span>  
 <span data-ttu-id="0cdbb-106">Метод `ReleaseAllRuntimeThreads` никогда не будет вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="0cdbb-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="0cdbb-107">Если в узле заблокирован поток среды выполнения, он должен освободить его сейчас.</span><span class="sxs-lookup"><span data-stu-id="0cdbb-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cdbb-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0cdbb-108">Requirements</span></span>  
 <span data-ttu-id="0cdbb-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cdbb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cdbb-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0cdbb-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cdbb-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0cdbb-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cdbb-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cdbb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cdbb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0cdbb-113">See also</span></span>

- [<span data-ttu-id="0cdbb-114">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="0cdbb-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
