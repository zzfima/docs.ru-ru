---
title: Метод ICorDebugManagedCallback::EditAndContinueRemap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
ms.openlocfilehash: 3fd1686eb268b9d4e347fe28e067a5321327dbd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137390"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="18f1f-102">Метод ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="18f1f-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="18f1f-103">Этот метод использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="18f1f-103">This method has been deprecated.</span></span> <span data-ttu-id="18f1f-104">Он уведомляет отладчик о том, что событие повторного сопоставления было отправлено в интегрированную среду разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="18f1f-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f1f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18f1f-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="18f1f-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="18f1f-106">Remarks</span></span>  
 <span data-ttu-id="18f1f-107">Метод `EditAndContinueRemap` вызывается при попыток выполнения кода в старой версии обновленной функции.</span><span class="sxs-lookup"><span data-stu-id="18f1f-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="18f1f-108">Среда CLR вызывает метод `EditAndContinueRemap` для отправки события повторного сопоставления в интегрированную среду разработки.</span><span class="sxs-lookup"><span data-stu-id="18f1f-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f1f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="18f1f-109">Requirements</span></span>  
 <span data-ttu-id="18f1f-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18f1f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f1f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18f1f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18f1f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18f1f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18f1f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f1f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f1f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="18f1f-114">See also</span></span>

- [<span data-ttu-id="18f1f-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="18f1f-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
