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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37b644227a6085352bed682f0ddd7c3455b54895
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760703"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="cbd14-102">Метод ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="cbd14-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="cbd14-103">Задает значение, указывающее типы кода, который осуществляется пошаговое.</span><span class="sxs-lookup"><span data-stu-id="cbd14-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd14-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbd14-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbd14-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbd14-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="cbd14-106">[in] Сочетание значений перечисления CorDebugIntercept, которое указывает типы кода.</span><span class="sxs-lookup"><span data-stu-id="cbd14-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbd14-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cbd14-107">Remarks</span></span>  
 <span data-ttu-id="cbd14-108">Если имеет значение бит для перехватчика, несопоставимого будет завершена при обнаружении данного типа перехват кода.</span><span class="sxs-lookup"><span data-stu-id="cbd14-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="cbd14-109">Если бит снят, перехватывающий код будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="cbd14-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="cbd14-110">`SetInterceptMask` Метод может иметь непредвиденные взаимодействия с [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (с точки зрения пользователя).</span><span class="sxs-lookup"><span data-stu-id="cbd14-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="cbd14-111">К примеру если только видимые (то есть не являющийся внутренним) часть кода инициализации класса не имеет сведений о сопоставлении и STOP_NO_MAPPING_INFO значение не задано (см. в разделе [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) метод и Перечисление CorDebugUnmappedStop), несопоставимого будет шаг с обходом инициализации класса.</span><span class="sxs-lookup"><span data-stu-id="cbd14-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="cbd14-112">По умолчанию только значение INTERCEPT_NONE `CorDebugIntercept` перечисления будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="cbd14-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbd14-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cbd14-113">Requirements</span></span>  
 <span data-ttu-id="cbd14-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbd14-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbd14-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbd14-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbd14-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbd14-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbd14-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbd14-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
