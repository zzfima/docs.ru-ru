---
title: Метод ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed6570e11008e52d4b1f97c2dc90e2ccbef2e35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471391"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="08a93-102">Метод ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="08a93-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="08a93-103">Для каждого метода класса задает значение, указывающее, является ли метод определяемого пользователем кода.</span><span class="sxs-lookup"><span data-stu-id="08a93-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08a93-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08a93-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08a93-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="08a93-106">[in] Значение `true` для указания, что метод определяется пользователем кода; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="08a93-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08a93-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="08a93-107">Remarks</span></span>  
 <span data-ttu-id="08a93-108">Только мой код (JMC) несопоставимого пропустит не пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="08a93-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="08a93-109">Пользовательский код должен представлять собой подмножество отлаживаемый код.</span><span class="sxs-lookup"><span data-stu-id="08a93-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="08a93-110">`SetJMCStatus` Возвращает значение HRESULT S_FALSE, если не удается задать значение для любого метода, даже если он успешно устанавливает значение для всех других методов.</span><span class="sxs-lookup"><span data-stu-id="08a93-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08a93-111">Требования</span><span class="sxs-lookup"><span data-stu-id="08a93-111">Requirements</span></span>  
 <span data-ttu-id="08a93-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08a93-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08a93-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08a93-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08a93-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08a93-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08a93-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08a93-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
