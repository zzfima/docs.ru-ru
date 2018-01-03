---
title: "Метод ICorDebugCode::IsIL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.IsIL
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3530b5a7a747816a12e76d00fa7c299acf7657c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="74887-102">Метод ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="74887-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="74887-103">Возвращает значение, указывающее, является ли «ICorDebugCode» представляет код, который был скомпилирован в промежуточный язык Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="74887-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74887-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74887-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74887-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74887-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="74887-106">[out] `true` при этом `ICorDebugCode` представляет собой код, скомпилированные в MSIL; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="74887-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74887-107">Требования</span><span class="sxs-lookup"><span data-stu-id="74887-107">Requirements</span></span>  
 <span data-ttu-id="74887-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74887-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74887-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74887-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74887-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74887-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74887-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74887-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74887-112">См. также</span><span class="sxs-lookup"><span data-stu-id="74887-112">See Also</span></span>  
 
