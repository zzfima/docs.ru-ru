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
ms.openlocfilehash: 444390622ca68244661b91dc85814b05556b12a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994322"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="fe834-102">Метод ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="fe834-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="fe834-103">Принуждает ICorDebugStepper выполнить один шаг через содержащую и при необходимости, чтобы продолжить, при пошаговом выполнении функций, которые вызываются в потоке.</span><span class="sxs-lookup"><span data-stu-id="fe834-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe834-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe834-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe834-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe834-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="fe834-106">[in] Значение `true` на шаг с заходом в функцию, которая вызывается в потоке.</span><span class="sxs-lookup"><span data-stu-id="fe834-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="fe834-107">Значение `false` на шаг с обходом функции.</span><span class="sxs-lookup"><span data-stu-id="fe834-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe834-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe834-108">Remarks</span></span>  
 <span data-ttu-id="fe834-109">Когда среда CLR выполняет следующую инструкцию управляемого кода в кадре средства пошагового завершения этого шага.</span><span class="sxs-lookup"><span data-stu-id="fe834-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="fe834-110">Если `Step` является вызывается для средства пошагового, который не находится в управляемом коде, шаг будет выполнен при выполнении следующей инструкции управляемого кода в потоке.</span><span class="sxs-lookup"><span data-stu-id="fe834-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe834-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fe834-111">Requirements</span></span>  
 <span data-ttu-id="fe834-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe834-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe834-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe834-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe834-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe834-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe834-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe834-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
