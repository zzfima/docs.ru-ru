---
title: "Метод ICorDebugStepper::StepOut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d6462f166e9c734dacc7ebee13cb82e3b12158b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="e85c4-102">Метод ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="e85c4-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="e85c4-103">В результате ICorDebugStepper выполнить один шаг через содержащую и для завершения текущего кадра возвращает управление в вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="e85c4-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e85c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e85c4-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e85c4-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e85c4-105">Remarks</span></span>  
 <span data-ttu-id="e85c4-106">Объект `StepOut` операция будет выполнена после возврата в обычном режиме из текущего кадра вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="e85c4-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="e85c4-107">Если `StepOut` вызывается, когда в неуправляемом коде шаг будет выполнен при возврате текущего кадра в управляемый код, который вызвал его.</span><span class="sxs-lookup"><span data-stu-id="e85c4-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="e85c4-108">В .NET Framework версии 2.0, не следует использовать `StepOut` с по умолчанию STOP_UNMANAGED значение флага, так как она завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="e85c4-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="e85c4-109">(Используйте [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) установить флаги для пошагового выполнения.) Отладчики взаимодействия необходимо выйти из машинного кода сами.</span><span class="sxs-lookup"><span data-stu-id="e85c4-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e85c4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e85c4-110">Requirements</span></span>  
 <span data-ttu-id="e85c4-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e85c4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e85c4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e85c4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e85c4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e85c4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e85c4-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e85c4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
