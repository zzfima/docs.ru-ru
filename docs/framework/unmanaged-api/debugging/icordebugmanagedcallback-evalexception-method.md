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
ms.openlocfilehash: ed64c7b28d60e966e836ac75e6dd7c0848304a38
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="0be9f-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="0be9f-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="0be9f-103">Уведомляет отладчик, что оценку завершилось с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="0be9f-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0be9f-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0be9f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0be9f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0be9f-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором Вычисление прервано.</span><span class="sxs-lookup"><span data-stu-id="0be9f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0be9f-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором Вычисление прервано.</span><span class="sxs-lookup"><span data-stu-id="0be9f-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="0be9f-108">[in] Указатель на объект ICorDebugEval, который представляет код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="0be9f-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be9f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0be9f-109">Requirements</span></span>  
 <span data-ttu-id="0be9f-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be9f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be9f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0be9f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0be9f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0be9f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0be9f-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be9f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be9f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0be9f-114">See Also</span></span>  
 [<span data-ttu-id="0be9f-115">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0be9f-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
