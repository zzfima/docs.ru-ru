---
title: "Метод ICorDebugCode::GetFunction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d05d5d7172a43ebaa04155fb42c2711eaf1ac085
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="9a6f6-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="9a6f6-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="9a6f6-103">Возвращает связанный с «ICorDebugCode» «ICorDebugFunction».</span><span class="sxs-lookup"><span data-stu-id="9a6f6-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a6f6-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a6f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a6f6-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="9a6f6-106">[out] Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="9a6f6-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a6f6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a6f6-107">Remarks</span></span>  
 <span data-ttu-id="9a6f6-108">`ICorDebugCode`и `ICorDebugFunction` Ведение отношение.</span><span class="sxs-lookup"><span data-stu-id="9a6f6-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9a6f6-109">Requirements</span></span>  
 <span data-ttu-id="9a6f6-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a6f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6f6-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a6f6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a6f6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a6f6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a6f6-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a6f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6f6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9a6f6-114">See Also</span></span>  
 
