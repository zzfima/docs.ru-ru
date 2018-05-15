---
title: Метод ICorDebugEval::Abort
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 682d6684b6c86485530b9e5283d843f3b2eb7e46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="102be-102">Метод ICorDebugEval::Abort</span><span class="sxs-lookup"><span data-stu-id="102be-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="102be-103">Прерывает этот объект ICorDebugEval в настоящее время выполняет вычисление.</span><span class="sxs-lookup"><span data-stu-id="102be-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="102be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="102be-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="102be-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="102be-105">Remarks</span></span>  
 <span data-ttu-id="102be-106">Если оценка является вложенной и не является самым последним заданием `Abort` может произойти сбой метода.</span><span class="sxs-lookup"><span data-stu-id="102be-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="102be-107">Требования</span><span class="sxs-lookup"><span data-stu-id="102be-107">Requirements</span></span>  
 <span data-ttu-id="102be-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="102be-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="102be-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="102be-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="102be-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="102be-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="102be-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="102be-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
