---
title: Метод IDebuggerThreadControl::ThreadIsBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9324e1596913fdafb13239dbefd631cbe3c6ffe4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780490"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="2de94-102">Метод IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="2de94-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="2de94-103">Уведомляет основное приложение, что поток, который отправляет этот обратный вызов о блок в службах отладки.</span><span class="sxs-lookup"><span data-stu-id="2de94-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2de94-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2de94-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="2de94-105">Remarks</span></span>  
 <span data-ttu-id="2de94-106">`ThreadIsBlockingForDebugger` Метод всегда будет вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2de94-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="2de94-107">`ThreadIsBlockingForDebugger` Метод предоставляет узлу возможность выполнения другого действия, когда поток блокируется.</span><span class="sxs-lookup"><span data-stu-id="2de94-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2de94-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2de94-108">Requirements</span></span>  
 <span data-ttu-id="2de94-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2de94-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2de94-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2de94-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2de94-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2de94-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2de94-112">**Версии NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2de94-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de94-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2de94-113">See also</span></span>

- [<span data-ttu-id="2de94-114">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="2de94-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
