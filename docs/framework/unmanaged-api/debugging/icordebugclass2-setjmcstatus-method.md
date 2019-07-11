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
ms.openlocfilehash: 23f248625753c15a4798ea69a1eb3b377b79f95d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747751"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="e1801-102">Метод ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="e1801-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="e1801-103">Для каждого метода класса задает значение, указывающее, является ли метод определяемого пользователем кода.</span><span class="sxs-lookup"><span data-stu-id="e1801-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1801-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1801-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1801-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1801-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="e1801-106">[in] Значение `true` для указания, что метод определяется пользователем кода; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e1801-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1801-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1801-107">Remarks</span></span>  
 <span data-ttu-id="e1801-108">Только мой код (JMC) несопоставимого пропустит не пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="e1801-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="e1801-109">Пользовательский код должен представлять собой подмножество отлаживаемый код.</span><span class="sxs-lookup"><span data-stu-id="e1801-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="e1801-110">`SetJMCStatus` Возвращает значение HRESULT S_FALSE, если не удается задать значение для любого метода, даже если он успешно устанавливает значение для всех других методов.</span><span class="sxs-lookup"><span data-stu-id="e1801-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1801-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e1801-111">Requirements</span></span>  
 <span data-ttu-id="e1801-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1801-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1801-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1801-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1801-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1801-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1801-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1801-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
