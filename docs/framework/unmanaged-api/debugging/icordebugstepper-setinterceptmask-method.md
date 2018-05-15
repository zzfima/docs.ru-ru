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
ms.openlocfilehash: 7654a91180dd0b4148cfb85b35bf1ce730764f28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="7371c-102">Метод ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="7371c-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="7371c-103">Задает значение, указывающее типы кода, который пошагово.</span><span class="sxs-lookup"><span data-stu-id="7371c-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7371c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7371c-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7371c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7371c-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="7371c-106">[in] Сочетание значений перечисления CorDebugIntercept, которое указывает типы кода.</span><span class="sxs-lookup"><span data-stu-id="7371c-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7371c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7371c-107">Remarks</span></span>  
 <span data-ttu-id="7371c-108">Если бит для перехватчика пошаговым будет выполнена при обнаружении данного типа перехват кода.</span><span class="sxs-lookup"><span data-stu-id="7371c-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="7371c-109">Если бит, перехватывающий код будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="7371c-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="7371c-110">`SetInterceptMask` Метод может иметь непредвиденные взаимодействий с [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (с точки зрения пользователя).</span><span class="sxs-lookup"><span data-stu-id="7371c-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="7371c-111">Например если только видимые (т. е: внутренняя) часть кода инициализации класса не имеет сведений о сопоставлении и STOP_NO_MAPPING_INFO не задано (в разделе [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) метод и Перечисление CorDebugUnmappedStop) пошаговым будет шаг с обходом инициализации класса.</span><span class="sxs-lookup"><span data-stu-id="7371c-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="7371c-112">По умолчанию только значение INTERCEPT_NONE `CorDebugIntercept` перечисления будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="7371c-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7371c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7371c-113">Requirements</span></span>  
 <span data-ttu-id="7371c-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7371c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7371c-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7371c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7371c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7371c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7371c-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7371c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
