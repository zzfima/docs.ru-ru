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
ms.openlocfilehash: dbf12612bb432f8935d08bdeac0bbcb471c38c54
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759640"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="842ef-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="842ef-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="842ef-103">Уведомляет отладчик о том, что оценку был завершен с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="842ef-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="842ef-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="842ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="842ef-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="842ef-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором прерывание оценки.</span><span class="sxs-lookup"><span data-stu-id="842ef-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="842ef-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором прерывание оценки.</span><span class="sxs-lookup"><span data-stu-id="842ef-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="842ef-108">[in] Указатель на ICorDebugEval объект, представляющий код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="842ef-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="842ef-109">Требования</span><span class="sxs-lookup"><span data-stu-id="842ef-109">Requirements</span></span>  
 <span data-ttu-id="842ef-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="842ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="842ef-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="842ef-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="842ef-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="842ef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="842ef-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="842ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842ef-114">См. также</span><span class="sxs-lookup"><span data-stu-id="842ef-114">See also</span></span>

- [<span data-ttu-id="842ef-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="842ef-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
