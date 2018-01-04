---
title: "Метод ICorDebugManagedCallback::EvalException"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3aa26c9458796dd20af0e22dd4a9961225b59bfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="c2879-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="c2879-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="c2879-103">Уведомляет отладчик, что оценку завершилось с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="c2879-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2879-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2879-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2879-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2879-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c2879-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором Вычисление прервано.</span><span class="sxs-lookup"><span data-stu-id="c2879-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c2879-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором Вычисление прервано.</span><span class="sxs-lookup"><span data-stu-id="c2879-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="c2879-108">[in] Указатель на объект ICorDebugEval, который представляет код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="c2879-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2879-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c2879-109">Requirements</span></span>  
 <span data-ttu-id="c2879-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2879-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2879-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2879-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2879-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2879-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2879-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2879-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2879-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c2879-114">See Also</span></span>  
 [<span data-ttu-id="c2879-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c2879-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
