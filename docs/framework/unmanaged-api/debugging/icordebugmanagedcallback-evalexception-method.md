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
ms.openlocfilehash: 70ae72968c3411a6732b09c0afe3d82931410cb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130805"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="f5b05-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="f5b05-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="f5b05-103">Уведомляет отладчик о том, что вычисление завершено с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="f5b05-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5b05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5b05-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5b05-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5b05-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f5b05-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором завершается вычисление.</span><span class="sxs-lookup"><span data-stu-id="f5b05-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f5b05-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором завершено вычисление.</span><span class="sxs-lookup"><span data-stu-id="f5b05-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="f5b05-108">окне Указатель на объект ICorDebugEval, представляющий код, который выполнил вычисление.</span><span class="sxs-lookup"><span data-stu-id="f5b05-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5b05-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f5b05-109">Requirements</span></span>  
 <span data-ttu-id="f5b05-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5b05-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5b05-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5b05-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5b05-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5b05-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5b05-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5b05-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b05-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f5b05-114">See also</span></span>

- [<span data-ttu-id="f5b05-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="f5b05-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
