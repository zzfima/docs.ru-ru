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
ms.openlocfilehash: a82606d90444c2d543065287780e42da4f8b4943
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180691"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="83821-102">Метод ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="83821-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="83821-103">Получает значение, указывающее, представляет ли этот «ICorDebugCode» код, который был скомпилирован в промежуточный язык Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="83821-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83821-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83821-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83821-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83821-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="83821-106">[out] `true` Если `ICorDebugCode` представляет код, скомпилированные в MSIL; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="83821-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83821-107">Требования</span><span class="sxs-lookup"><span data-stu-id="83821-107">Requirements</span></span>  
 <span data-ttu-id="83821-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83821-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83821-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83821-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83821-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83821-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83821-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83821-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83821-112">См. также</span><span class="sxs-lookup"><span data-stu-id="83821-112">See also</span></span>
