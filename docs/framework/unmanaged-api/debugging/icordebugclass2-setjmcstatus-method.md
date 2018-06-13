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
ms.openlocfilehash: d234e01e3d47a64b9a001591ee2b61074eea8afb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403398"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="bc015-102">Метод ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="bc015-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="bc015-103">Для каждого метода класса задает значение, указывающее, является ли метод пользовательским кодом.</span><span class="sxs-lookup"><span data-stu-id="bc015-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc015-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc015-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc015-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc015-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="bc015-106">[in] Значение `true` для указания, что метод является определяемой пользователем код; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="bc015-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc015-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc015-107">Remarks</span></span>  
 <span data-ttu-id="bc015-108">Только мой код (JMC) пошаговым пропустит не пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="bc015-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="bc015-109">Пользовательский код должен быть подмножеством отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="bc015-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="bc015-110">`SetJMCStatus` Возвращает значение HRESULT S_FALSE, если ему не удается задать значение для любого метода, даже если он успешно устанавливает значение для всех других методов.</span><span class="sxs-lookup"><span data-stu-id="bc015-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc015-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bc015-111">Requirements</span></span>  
 <span data-ttu-id="bc015-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc015-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc015-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc015-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc015-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc015-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc015-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc015-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
