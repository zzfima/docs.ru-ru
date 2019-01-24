---
title: Метод ICorDebugManagedCallback::EvalException
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1705b9d77d0d91196201d713cceb0ccf0f8635a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728019"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="c0853-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="c0853-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="c0853-103">Уведомляет отладчик о том, что оценку был завершен с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="c0853-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0853-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0853-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0853-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0853-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c0853-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором прерывание оценки.</span><span class="sxs-lookup"><span data-stu-id="c0853-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c0853-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором прерывание оценки.</span><span class="sxs-lookup"><span data-stu-id="c0853-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="c0853-108">[in] Указатель на ICorDebugEval объект, представляющий код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="c0853-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0853-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c0853-109">Requirements</span></span>  
 <span data-ttu-id="c0853-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0853-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0853-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0853-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0853-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0853-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0853-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0853-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0853-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c0853-114">See also</span></span>
- [<span data-ttu-id="c0853-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c0853-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
