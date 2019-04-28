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
ms.openlocfilehash: 0104a52c3aa206f86daff30d9d16298e6beae324
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750252"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="7ff8c-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="7ff8c-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="7ff8c-103">Возвращает «ICorDebugFunction», связанный с «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="7ff8c-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ff8c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ff8c-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ff8c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ff8c-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="7ff8c-106">[out] Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="7ff8c-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ff8c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ff8c-107">Remarks</span></span>  
 <span data-ttu-id="7ff8c-108">`ICorDebugCode` и `ICorDebugFunction` Ведение взаимно-однозначной связи.</span><span class="sxs-lookup"><span data-stu-id="7ff8c-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff8c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7ff8c-109">Requirements</span></span>  
 <span data-ttu-id="7ff8c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ff8c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff8c-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ff8c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ff8c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ff8c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ff8c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff8c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff8c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7ff8c-114">See also</span></span>
