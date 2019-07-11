---
title: Метод ICorDebugStepper::SetRangeIL
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610225708bf990850fce73d6d7ff66c556e24e5d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760603"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="fbae1-102">Метод ICorDebugStepper::SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="fbae1-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="fbae1-103">Задает значение, указывающее ли вызовы [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) передать аргумент, код языка MSIL метода, который является в настоящее время шаг на промежуточном машинному коду или относительно Microsoft значений через.</span><span class="sxs-lookup"><span data-stu-id="fbae1-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbae1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbae1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbae1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbae1-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="fbae1-106">[in] Значение `true` для указания, что диапазоны относительны MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="fbae1-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="fbae1-107">Значение `false` для указания, что диапазоны относительны машинный код.</span><span class="sxs-lookup"><span data-stu-id="fbae1-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="fbae1-108">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="fbae1-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbae1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fbae1-109">Requirements</span></span>  
 <span data-ttu-id="fbae1-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbae1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbae1-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbae1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbae1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbae1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbae1-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbae1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
