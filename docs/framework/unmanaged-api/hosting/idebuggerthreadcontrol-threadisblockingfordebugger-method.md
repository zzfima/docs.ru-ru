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
ms.openlocfilehash: 067d4e844055206543e5c7fb409296b0d0a7a549
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134941"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="f622b-102">Метод IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="f622b-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="f622b-103">Уведомляет узел о том, что поток, отправляющий этот обратный вызов, будет заблокирован в службах отладки.</span><span class="sxs-lookup"><span data-stu-id="f622b-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f622b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f622b-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="f622b-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="f622b-105">Remarks</span></span>  
 <span data-ttu-id="f622b-106">Метод `ThreadIsBlockingForDebugger` всегда будет вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f622b-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="f622b-107">Метод `ThreadIsBlockingForDebugger` дает узлу возможность выполнить еще одно действие, пока блокируется поток.</span><span class="sxs-lookup"><span data-stu-id="f622b-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f622b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f622b-108">Requirements</span></span>  
 <span data-ttu-id="f622b-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f622b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f622b-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f622b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f622b-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f622b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f622b-112">**Версии .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f622b-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f622b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f622b-113">See also</span></span>

- [<span data-ttu-id="f622b-114">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="f622b-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
