---
title: Метод ICorDebugStepper::Step
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2d282e27ec5068fa6fe7f58ba95458fdc219972
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="65671-102">Метод ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="65671-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="65671-103">Принуждает ICorDebugStepper выполнить один шаг через содержащую и, при необходимости, чтобы продолжить, при пошаговом выполнении функций, которые вызываются в потоке.</span><span class="sxs-lookup"><span data-stu-id="65671-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65671-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65671-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65671-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65671-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="65671-106">[in] Значение `true` на шаг с заходом в функцию, которая вызывается в потоке.</span><span class="sxs-lookup"><span data-stu-id="65671-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="65671-107">Значение `false` на шаг с обходом функции.</span><span class="sxs-lookup"><span data-stu-id="65671-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65671-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="65671-108">Remarks</span></span>  
 <span data-ttu-id="65671-109">Этот шаг завершается, если общеязыковая среда выполнения выполняет следующую инструкцию управляемого кода в кадре средства пошагового.</span><span class="sxs-lookup"><span data-stu-id="65671-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="65671-110">Если `Step` будет вызван для средства пошагового, который не находится в управляемого кода, шаг будет выполнен при выполнении потоком следующей инструкции управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="65671-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65671-111">Требования</span><span class="sxs-lookup"><span data-stu-id="65671-111">Requirements</span></span>  
 <span data-ttu-id="65671-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65671-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65671-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65671-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65671-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65671-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65671-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65671-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
