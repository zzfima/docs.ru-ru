---
title: Метод ICorDebugCode::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10ab92c660353bea85bbd0918a25f716898ef837
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747534"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="d72e0-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="d72e0-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="d72e0-103">Возвращает «ICorDebugFunction», связанный с «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="d72e0-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d72e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d72e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d72e0-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="d72e0-106">[out] Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="d72e0-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d72e0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d72e0-107">Remarks</span></span>  
 <span data-ttu-id="d72e0-108">`ICorDebugCode` и `ICorDebugFunction` Ведение взаимно-однозначной связи.</span><span class="sxs-lookup"><span data-stu-id="d72e0-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d72e0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d72e0-109">Requirements</span></span>  
 <span data-ttu-id="d72e0-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d72e0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d72e0-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d72e0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d72e0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d72e0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d72e0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d72e0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72e0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d72e0-114">See also</span></span>
