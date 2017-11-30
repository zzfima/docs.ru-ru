---
title: "Метод ICorDebugStepper::Step"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.Step
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 914773adefd2ed4c1aa98310fd27a0cbc829bf49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="93d8f-102">Метод ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="93d8f-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="93d8f-103">Принуждает ICorDebugStepper выполнить один шаг через содержащую и, при необходимости, чтобы продолжить, при пошаговом выполнении функций, которые вызываются в потоке.</span><span class="sxs-lookup"><span data-stu-id="93d8f-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93d8f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93d8f-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93d8f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93d8f-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="93d8f-106">[in] Значение `true` на шаг с заходом в функцию, которая вызывается в потоке.</span><span class="sxs-lookup"><span data-stu-id="93d8f-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="93d8f-107">Значение `false` на шаг с обходом функции.</span><span class="sxs-lookup"><span data-stu-id="93d8f-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93d8f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="93d8f-108">Remarks</span></span>  
 <span data-ttu-id="93d8f-109">Этот шаг завершается, если общеязыковая среда выполнения выполняет следующую инструкцию управляемого кода в кадре средства пошагового.</span><span class="sxs-lookup"><span data-stu-id="93d8f-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="93d8f-110">Если `Step` будет вызван для средства пошагового, который не находится в управляемого кода, шаг будет выполнен при выполнении потоком следующей инструкции управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="93d8f-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93d8f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="93d8f-111">Requirements</span></span>  
 <span data-ttu-id="93d8f-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93d8f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93d8f-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93d8f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93d8f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93d8f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93d8f-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93d8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
