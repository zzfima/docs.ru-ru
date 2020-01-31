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
ms.openlocfilehash: d29f4095a1d615285f4c4ff30e36b91404036949
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788411"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="06211-102">Метод ICorDebugManagedCallback::EvalComplete</span><span class="sxs-lookup"><span data-stu-id="06211-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="06211-103">Уведомляет отладчик о завершении оценки.</span><span class="sxs-lookup"><span data-stu-id="06211-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06211-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06211-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06211-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06211-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="06211-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором была выполнена оценка.</span><span class="sxs-lookup"><span data-stu-id="06211-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="06211-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором выполнялась оценка.</span><span class="sxs-lookup"><span data-stu-id="06211-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="06211-108">окне Указатель на объект ICorDebugEval, представляющий код, который выполнил вычисление.</span><span class="sxs-lookup"><span data-stu-id="06211-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06211-109">Требования</span><span class="sxs-lookup"><span data-stu-id="06211-109">Requirements</span></span>  
 <span data-ttu-id="06211-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06211-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06211-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06211-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06211-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06211-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06211-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06211-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06211-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="06211-114">See also</span></span>

- [<span data-ttu-id="06211-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="06211-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
