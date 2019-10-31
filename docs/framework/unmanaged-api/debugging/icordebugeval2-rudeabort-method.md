---
title: Метод ICorDebugEval2::RudeAbort
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: a486935d5d53a6fc7d862160ed1186c5774814c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084798"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="3a98d-102">Метод ICorDebugEval2::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="3a98d-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="3a98d-103">Прерывает вычисление, выполняемое в данный момент `ICorDebugEval2`.</span><span class="sxs-lookup"><span data-stu-id="3a98d-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a98d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a98d-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3a98d-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="3a98d-105">Remarks</span></span>  
 <span data-ttu-id="3a98d-106">`RudeAbort` не освобождает никакие блокировки, которые содержит средство оценки, поэтому сеанс отладки остается в ненадежном состоянии.</span><span class="sxs-lookup"><span data-stu-id="3a98d-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="3a98d-107">Вызывайте этот метод с особой осторожностью.</span><span class="sxs-lookup"><span data-stu-id="3a98d-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a98d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3a98d-108">Requirements</span></span>  
 <span data-ttu-id="3a98d-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a98d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a98d-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a98d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a98d-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a98d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a98d-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a98d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
