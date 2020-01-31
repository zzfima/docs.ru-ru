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
ms.openlocfilehash: 3ae93081bd201f745fa47bc01a9c6fcbf6e9f63c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781862"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="5fe64-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="5fe64-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="5fe64-103">Уведомляет отладчик о том, что вычисление завершено с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="5fe64-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fe64-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fe64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5fe64-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5fe64-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором завершается вычисление.</span><span class="sxs-lookup"><span data-stu-id="5fe64-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5fe64-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором завершено вычисление.</span><span class="sxs-lookup"><span data-stu-id="5fe64-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="5fe64-108">окне Указатель на объект ICorDebugEval, представляющий код, который выполнил вычисление.</span><span class="sxs-lookup"><span data-stu-id="5fe64-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fe64-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5fe64-109">Requirements</span></span>  
 <span data-ttu-id="5fe64-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fe64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fe64-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fe64-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fe64-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fe64-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fe64-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe64-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fe64-114">See also</span></span>

- [<span data-ttu-id="5fe64-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5fe64-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
