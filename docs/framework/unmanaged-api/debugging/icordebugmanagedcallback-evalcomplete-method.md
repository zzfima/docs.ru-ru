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
ms.openlocfilehash: 3243429f52bda58953296c4bb32624440792ad02
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636473"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="ad2a2-102">Метод ICorDebugManagedCallback::EvalComplete</span><span class="sxs-lookup"><span data-stu-id="ad2a2-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="ad2a2-103">Уведомляет отладчик о завершении вычисления.</span><span class="sxs-lookup"><span data-stu-id="ad2a2-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad2a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad2a2-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad2a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad2a2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ad2a2-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором была выполнена оценка.</span><span class="sxs-lookup"><span data-stu-id="ad2a2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ad2a2-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором была выполнена оценка.</span><span class="sxs-lookup"><span data-stu-id="ad2a2-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="ad2a2-108">[in] Указатель на ICorDebugEval объект, представляющий код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="ad2a2-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad2a2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ad2a2-109">Requirements</span></span>  
 <span data-ttu-id="ad2a2-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad2a2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad2a2-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad2a2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad2a2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad2a2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad2a2-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad2a2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad2a2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ad2a2-114">See also</span></span>
- [<span data-ttu-id="ad2a2-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ad2a2-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
