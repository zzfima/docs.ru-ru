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
ms.openlocfilehash: 4414bab535b63f55a580e93cc6de9cb0dedc073c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="c2087-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="c2087-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="c2087-103">Уведомляет отладчик, что оценку завершилось с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="c2087-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2087-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2087-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2087-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2087-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c2087-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором Вычисление прервано.</span><span class="sxs-lookup"><span data-stu-id="c2087-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c2087-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором Вычисление прервано.</span><span class="sxs-lookup"><span data-stu-id="c2087-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="c2087-108">[in] Указатель на объект ICorDebugEval, который представляет код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="c2087-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2087-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c2087-109">Requirements</span></span>  
 <span data-ttu-id="c2087-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2087-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2087-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2087-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2087-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2087-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2087-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2087-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2087-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c2087-114">See Also</span></span>  
 [<span data-ttu-id="c2087-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c2087-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
