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
ms.openlocfilehash: 602bcd12d1fd4c5806de6db81252731baa447b7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120020"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="5073a-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="5073a-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="5073a-103">Уведомляет отладчик о том, что оценку был завершен с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="5073a-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5073a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5073a-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5073a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5073a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5073a-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором прерывание оценки.</span><span class="sxs-lookup"><span data-stu-id="5073a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5073a-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором прерывание оценки.</span><span class="sxs-lookup"><span data-stu-id="5073a-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="5073a-108">[in] Указатель на ICorDebugEval объект, представляющий код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="5073a-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5073a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5073a-109">Requirements</span></span>  
 <span data-ttu-id="5073a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5073a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5073a-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5073a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5073a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5073a-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5073a-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5073a-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5073a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5073a-114">See also</span></span>

- [<span data-ttu-id="5073a-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5073a-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
