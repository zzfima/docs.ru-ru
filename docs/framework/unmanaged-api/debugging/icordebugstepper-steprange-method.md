---
title: Метод ICorDebugStepper::StepRange
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b18474aeaa79224de5371df3ff0cac5ed9bf4ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994291"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="2347d-102">Метод ICorDebugStepper::StepRange</span><span class="sxs-lookup"><span data-stu-id="2347d-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="2347d-103">Принуждает ICorDebugStepper выполнить один шаг через содержащую и должны быть возвращены при достижении кода за последним из указанных диапазонов.</span><span class="sxs-lookup"><span data-stu-id="2347d-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2347d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2347d-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2347d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2347d-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="2347d-106">[in] Значение `true` на шаг с заходом в функцию, которая вызывается в потоке.</span><span class="sxs-lookup"><span data-stu-id="2347d-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="2347d-107">Значение `false` на шаг с обходом функции.</span><span class="sxs-lookup"><span data-stu-id="2347d-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="2347d-108">[in] Массив структур COR_DEBUG_STEP_RANGE, каждый из которых задает диапазон.</span><span class="sxs-lookup"><span data-stu-id="2347d-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="2347d-109">[in] Размер массива `ranges`.</span><span class="sxs-lookup"><span data-stu-id="2347d-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2347d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2347d-110">Remarks</span></span>  
 <span data-ttu-id="2347d-111">`StepRange` Метод работает подобно [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) метода, за исключением того, что она не завершается до кода за пределами данного диапазона будет достигнут.</span><span class="sxs-lookup"><span data-stu-id="2347d-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="2347d-112">Это может быть более эффективным, чем пошаговое выполнение одной инструкции одновременно.</span><span class="sxs-lookup"><span data-stu-id="2347d-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="2347d-113">Диапазоны задаются в виде списка пар смещения от начала несопоставимого кадра.</span><span class="sxs-lookup"><span data-stu-id="2347d-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="2347d-114">Диапазоны указываются относительно кода промежуточного языка MSIL Microsoft метода.</span><span class="sxs-lookup"><span data-stu-id="2347d-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="2347d-115">Вызовите [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) с `false` вносить диапазоны машинному коду метода.</span><span class="sxs-lookup"><span data-stu-id="2347d-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2347d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2347d-116">Requirements</span></span>  
 <span data-ttu-id="2347d-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2347d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2347d-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2347d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2347d-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2347d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2347d-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2347d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
