---
title: Метод ICorDebugManagedCallback::EvalComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1261942865419762fa454eb8d4bc5e5d99e86d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995245"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="fc79b-102">Метод ICorDebugManagedCallback::EvalComplete</span><span class="sxs-lookup"><span data-stu-id="fc79b-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="fc79b-103">Уведомляет отладчик о завершении вычисления.</span><span class="sxs-lookup"><span data-stu-id="fc79b-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc79b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc79b-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc79b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc79b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fc79b-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором была выполнена оценка.</span><span class="sxs-lookup"><span data-stu-id="fc79b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fc79b-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором была выполнена оценка.</span><span class="sxs-lookup"><span data-stu-id="fc79b-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="fc79b-108">[in] Указатель на ICorDebugEval объект, представляющий код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="fc79b-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc79b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fc79b-109">Requirements</span></span>  
 <span data-ttu-id="fc79b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc79b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc79b-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc79b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc79b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc79b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc79b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc79b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc79b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fc79b-114">See also</span></span>

- [<span data-ttu-id="fc79b-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fc79b-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
