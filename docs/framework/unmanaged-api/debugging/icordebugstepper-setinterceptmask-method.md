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
ms.openlocfilehash: 25a9d287e6520f1fc7826d85dfbcd8e9a6da22f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987640"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="ab71c-102">Метод ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="ab71c-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="ab71c-103">Задает значение, указывающее типы кода, который осуществляется пошаговое.</span><span class="sxs-lookup"><span data-stu-id="ab71c-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab71c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab71c-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab71c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab71c-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="ab71c-106">[in] Сочетание значений перечисления CorDebugIntercept, которое указывает типы кода.</span><span class="sxs-lookup"><span data-stu-id="ab71c-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab71c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab71c-107">Remarks</span></span>  
 <span data-ttu-id="ab71c-108">Если имеет значение бит для перехватчика, несопоставимого будет завершена при обнаружении данного типа перехват кода.</span><span class="sxs-lookup"><span data-stu-id="ab71c-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="ab71c-109">Если бит снят, перехватывающий код будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="ab71c-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="ab71c-110">`SetInterceptMask` Метод может иметь непредвиденные взаимодействия с [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (с точки зрения пользователя).</span><span class="sxs-lookup"><span data-stu-id="ab71c-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="ab71c-111">К примеру если только видимые (то есть не являющийся внутренним) часть кода инициализации класса не имеет сведений о сопоставлении и STOP_NO_MAPPING_INFO значение не задано (см. в разделе [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) метод и Перечисление CorDebugUnmappedStop), несопоставимого будет шаг с обходом инициализации класса.</span><span class="sxs-lookup"><span data-stu-id="ab71c-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="ab71c-112">По умолчанию только значение INTERCEPT_NONE `CorDebugIntercept` перечисления будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="ab71c-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab71c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ab71c-113">Requirements</span></span>  
 <span data-ttu-id="ab71c-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab71c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab71c-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab71c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab71c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab71c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab71c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab71c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
