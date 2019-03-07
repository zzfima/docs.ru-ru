---
title: Метод ICorDebugCode::IsIL
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78f246f90e7e3b7c9fff984092a0b5eefcba5a13
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478067"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="a0da0-102">Метод ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="a0da0-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="a0da0-103">Получает значение, указывающее, представляет ли этот «ICorDebugCode» код, который был скомпилирован в промежуточный язык Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="a0da0-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0da0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0da0-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0da0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0da0-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="a0da0-106">[out] `true` Если `ICorDebugCode` представляет код, скомпилированные в MSIL; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a0da0-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0da0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a0da0-107">Requirements</span></span>  
 <span data-ttu-id="a0da0-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0da0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0da0-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0da0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0da0-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0da0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0da0-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0da0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0da0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a0da0-112">See also</span></span>

