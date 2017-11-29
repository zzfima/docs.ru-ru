---
title: "Метод ICorDebugStepper::StepOut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepOut
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b3ceca69b6b4710a3f1b8e1e9bdb4baf574119c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="684e0-102">Метод ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="684e0-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="684e0-103">В результате ICorDebugStepper выполнить один шаг через содержащую и для завершения текущего кадра возвращает управление в вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="684e0-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="684e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="684e0-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="684e0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="684e0-105">Remarks</span></span>  
 <span data-ttu-id="684e0-106">Объект `StepOut` операция будет выполнена после возврата в обычном режиме из текущего кадра вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="684e0-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="684e0-107">Если `StepOut` вызывается, когда в неуправляемом коде шаг будет выполнен при возврате текущего кадра в управляемый код, который вызвал его.</span><span class="sxs-lookup"><span data-stu-id="684e0-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="684e0-108">В .NET Framework версии 2.0, не следует использовать `StepOut` с по умолчанию STOP_UNMANAGED значение флага, так как она завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="684e0-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="684e0-109">(Используйте [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) установить флаги для пошагового выполнения.) Отладчики взаимодействия необходимо выйти из машинного кода сами.</span><span class="sxs-lookup"><span data-stu-id="684e0-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="684e0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="684e0-110">Requirements</span></span>  
 <span data-ttu-id="684e0-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="684e0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="684e0-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="684e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="684e0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="684e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="684e0-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="684e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
