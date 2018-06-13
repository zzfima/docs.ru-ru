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
ms.openlocfilehash: 8d0e7f20be3f18e49dcc1b986460d5da0c3d7777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401944"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="8d365-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="8d365-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="8d365-103">Возвращает связанный с «ICorDebugCode» «ICorDebugFunction».</span><span class="sxs-lookup"><span data-stu-id="8d365-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d365-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d365-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d365-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d365-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="8d365-106">[out] Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="8d365-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d365-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d365-107">Remarks</span></span>  
 <span data-ttu-id="8d365-108">`ICorDebugCode` и `ICorDebugFunction` Ведение отношение.</span><span class="sxs-lookup"><span data-stu-id="8d365-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d365-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8d365-109">Requirements</span></span>  
 <span data-ttu-id="8d365-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d365-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d365-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d365-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d365-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d365-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d365-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d365-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d365-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8d365-114">See Also</span></span>  
 
