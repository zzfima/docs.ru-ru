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
ms.openlocfilehash: 08cf2d0bb09080296fc1fcc69b5817f4d6118765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791729"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="b55e7-102">Метод ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="b55e7-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="b55e7-103">Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток и завершается, когда текущий кадр возвращает управление вызывающему кадру.</span><span class="sxs-lookup"><span data-stu-id="b55e7-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b55e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b55e7-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b55e7-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="b55e7-105">Remarks</span></span>  
 <span data-ttu-id="b55e7-106">Операция `StepOut` будет завершена после возврата в обычном режиме из текущего кадра в вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="b55e7-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="b55e7-107">Если `StepOut` вызывается в неуправляемом коде, шаг завершится, когда текущий кадр вернется в управляемый код, вызвавший его.</span><span class="sxs-lookup"><span data-stu-id="b55e7-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="b55e7-108">В .NET Framework версии 2,0 не используйте `StepOut` с установленным флагом STOP_UNMANAGED, так как он завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b55e7-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="b55e7-109">(Используйте [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) для установки флагов для пошагового выполнения.) Отладчики взаимодействия должны выполнять шаг с заходом в собственный код.</span><span class="sxs-lookup"><span data-stu-id="b55e7-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b55e7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b55e7-110">Requirements</span></span>  
 <span data-ttu-id="b55e7-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b55e7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b55e7-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b55e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b55e7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b55e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b55e7-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b55e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
