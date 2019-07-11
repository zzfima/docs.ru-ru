---
title: Метод ICorDebugStepper::StepOut
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36a33b74a692761d772a888ce918aa28a2d92678
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760556"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="90c72-102">Метод ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="90c72-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="90c72-103">Принуждает ICorDebugStepper выполнить один шаг через содержащую и для завершения текущего кадра возвращает управление в вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="90c72-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90c72-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="90c72-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="90c72-105">Remarks</span></span>  
 <span data-ttu-id="90c72-106">Объект `StepOut` операция будет выполнена после возврата в обычном режиме из текущего кадра на вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="90c72-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="90c72-107">Если `StepOut` вызывается, когда в неуправляемом коде, шаг будет выполнен при возврате текущего кадра в управляемый код, который вызвал ее.</span><span class="sxs-lookup"><span data-stu-id="90c72-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="90c72-108">В .NET Framework версии 2.0, не используйте `StepOut` с по умолчанию STOP_UNMANAGED флага stateful, так как его не удастся.</span><span class="sxs-lookup"><span data-stu-id="90c72-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="90c72-109">(Используйте [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) установить флаги для пошагового выполнения.) Отладчики взаимодействия необходимо шаг с выходом в машинный код самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="90c72-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c72-110">Требования</span><span class="sxs-lookup"><span data-stu-id="90c72-110">Requirements</span></span>  
 <span data-ttu-id="90c72-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90c72-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c72-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90c72-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90c72-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90c72-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90c72-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c72-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
