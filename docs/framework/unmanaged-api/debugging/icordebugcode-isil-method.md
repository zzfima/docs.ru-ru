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
ms.openlocfilehash: ccebe01c853677f7c78731e757ef7a5f090d6919
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="98e1e-102">Метод ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="98e1e-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="98e1e-103">Возвращает значение, указывающее, является ли «ICorDebugCode» представляет код, который был скомпилирован в промежуточный язык Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="98e1e-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98e1e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98e1e-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98e1e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98e1e-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="98e1e-106">[out] `true` при этом `ICorDebugCode` представляет собой код, скомпилированные в MSIL; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="98e1e-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98e1e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="98e1e-107">Requirements</span></span>  
 <span data-ttu-id="98e1e-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98e1e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98e1e-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98e1e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98e1e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98e1e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98e1e-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98e1e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e1e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="98e1e-112">See Also</span></span>  
 
