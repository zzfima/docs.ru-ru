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
ms.openlocfilehash: 052c467f5570119cd08b4719c768d178dd52aba2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752217"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="12935-102">Метод ICorDebugEval::Abort</span><span class="sxs-lookup"><span data-stu-id="12935-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="12935-103">Прерывает выполняемое вычисление этого объекта ICorDebugEval выполняющему в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="12935-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12935-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12935-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="12935-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="12935-105">Remarks</span></span>  
 <span data-ttu-id="12935-106">Если вычисление является вложенным, и это не самую последнюю из них, `Abort` может произойти сбой метода.</span><span class="sxs-lookup"><span data-stu-id="12935-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12935-107">Требования</span><span class="sxs-lookup"><span data-stu-id="12935-107">Requirements</span></span>  
 <span data-ttu-id="12935-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12935-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12935-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12935-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12935-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12935-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12935-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12935-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
