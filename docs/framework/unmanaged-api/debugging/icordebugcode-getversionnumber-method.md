---
title: Метод ICorDebugCode::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3d4609d79bb424cabc011122480f952f0f877f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="e30e5-102">Метод ICorDebugCode::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="e30e5-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="e30e5-103">Возвращает номер от единицы, определяющий версию кода, который представляет «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="e30e5-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e30e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e30e5-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e30e5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e30e5-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="e30e5-106">[out] Указатель на номер версии кода.</span><span class="sxs-lookup"><span data-stu-id="e30e5-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e30e5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e30e5-107">Remarks</span></span>  
 <span data-ttu-id="e30e5-108">Номер версии увеличивается каждый раз операции edit and continue (EnC) выполняется в коде.</span><span class="sxs-lookup"><span data-stu-id="e30e5-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e30e5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e30e5-109">Requirements</span></span>  
 <span data-ttu-id="e30e5-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e30e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e30e5-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e30e5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e30e5-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e30e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e30e5-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e30e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30e5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e30e5-114">See Also</span></span>  
 
