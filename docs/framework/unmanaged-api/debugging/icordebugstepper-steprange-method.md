---
title: "Метод ICorDebugStepper::StepRange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72a68000691dd23a55b77265cae839bea8b4ae1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="1f317-102">Метод ICorDebugStepper::StepRange</span><span class="sxs-lookup"><span data-stu-id="1f317-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="1f317-103">В результате ICorDebugStepper выполнить один шаг через содержащую и возвратить при достижении кода за последним из указанных диапазонов.</span><span class="sxs-lookup"><span data-stu-id="1f317-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f317-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f317-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f317-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f317-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="1f317-106">[in] Значение `true` на шаг с заходом в функцию, которая вызывается в потоке.</span><span class="sxs-lookup"><span data-stu-id="1f317-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="1f317-107">Значение `false` на шаг с обходом функции.</span><span class="sxs-lookup"><span data-stu-id="1f317-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="1f317-108">[in] Массив структур COR_DEBUG_STEP_RANGE, каждый из которых задает диапазон.</span><span class="sxs-lookup"><span data-stu-id="1f317-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="1f317-109">[in] Размер массива `ranges`.</span><span class="sxs-lookup"><span data-stu-id="1f317-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f317-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f317-110">Remarks</span></span>  
 <span data-ttu-id="1f317-111">`StepRange` Действия метода [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) метода, за исключением того, что она не завершается до кода за пределами данного диапазона достигается.</span><span class="sxs-lookup"><span data-stu-id="1f317-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="1f317-112">Это может быть более эффективным, чем пошаговое выполнение одной инструкции за раз.</span><span class="sxs-lookup"><span data-stu-id="1f317-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="1f317-113">Диапазоны задаются в виде списка пар смещения от начала пошаговым кадра.</span><span class="sxs-lookup"><span data-stu-id="1f317-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="1f317-114">Диапазоны относятся к Microsoft кода промежуточного языка MSIL метода.</span><span class="sxs-lookup"><span data-stu-id="1f317-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="1f317-115">Вызовите [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) с `false` вносить диапазоны машинному коду метода.</span><span class="sxs-lookup"><span data-stu-id="1f317-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f317-116">Требования</span><span class="sxs-lookup"><span data-stu-id="1f317-116">Requirements</span></span>  
 <span data-ttu-id="1f317-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f317-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f317-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f317-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f317-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f317-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f317-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f317-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
