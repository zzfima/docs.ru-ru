---
title: Метод ICorDebugStepper::SetInterceptMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: e88fa543eca39c14962f0dbbe8053829713401c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137584"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="0fbec-102">Метод ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="0fbec-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="0fbec-103">Задает значение, указывающее типы кода, в который выполняется пошаговое выполнение.</span><span class="sxs-lookup"><span data-stu-id="0fbec-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fbec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fbec-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fbec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fbec-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="0fbec-106">окне Сочетание значений перечисления CorDebugIntercept, определяющих типы кода.</span><span class="sxs-lookup"><span data-stu-id="0fbec-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fbec-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="0fbec-107">Remarks</span></span>  
 <span data-ttu-id="0fbec-108">Если задан бит для перехватчика, средство пошагового выполнения будет выполнено при обнаружении заданного типа перехвата кода.</span><span class="sxs-lookup"><span data-stu-id="0fbec-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="0fbec-109">Если бит сброшен, перехват кода будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="0fbec-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="0fbec-110">Метод `SetInterceptMask` может иметь непредвиденные взаимодействия с [ICorDebugStepper:: сетунмаппедстопмаск](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (от точки зрения пользователя).</span><span class="sxs-lookup"><span data-stu-id="0fbec-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="0fbec-111">Например, если только видимая (невнутренняя) часть кода инициализации класса не имеет сведений о сопоставлении и STOP_NO_MAPPING_INFO не задана (см [. метод ICorDebugStepper:: сетунмаппедстопмаск](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) и кордебугунмаппедстоп перечисление), средство организации пошагового прохода по инициализации класса.</span><span class="sxs-lookup"><span data-stu-id="0fbec-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="0fbec-112">По умолчанию будет использоваться только значение INTERCEPT_NONE перечисления `CorDebugIntercept`.</span><span class="sxs-lookup"><span data-stu-id="0fbec-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fbec-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0fbec-113">Requirements</span></span>  
 <span data-ttu-id="0fbec-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fbec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fbec-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fbec-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fbec-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fbec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fbec-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fbec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
