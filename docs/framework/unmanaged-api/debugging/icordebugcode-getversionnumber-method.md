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
ms.openlocfilehash: 003b29501e8f22ed9010a9f16a4f7ee67bce03a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750141"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="9e4df-102">Метод ICorDebugCode::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="9e4df-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="9e4df-103">Получает номер от единицы, который определяет версию кода, который представляет этот «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="9e4df-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e4df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e4df-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e4df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e4df-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="9e4df-106">[out] Указатель на номер версии кода.</span><span class="sxs-lookup"><span data-stu-id="9e4df-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e4df-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e4df-107">Remarks</span></span>  
 <span data-ttu-id="9e4df-108">Номер версии увеличивается каждый раз, когда операция edit and continue (EnC) выполняется в коде.</span><span class="sxs-lookup"><span data-stu-id="9e4df-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e4df-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9e4df-109">Requirements</span></span>  
 <span data-ttu-id="9e4df-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e4df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e4df-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e4df-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e4df-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e4df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e4df-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e4df-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4df-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9e4df-114">See also</span></span>
