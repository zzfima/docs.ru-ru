---
title: Метод ICorDebugILFrame2::RemapFunction
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbec4a4ba05a7e6d50f9740582415219eafb1e57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621468"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="cea6d-102">Метод ICorDebugILFrame2::RemapFunction</span><span class="sxs-lookup"><span data-stu-id="cea6d-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="cea6d-103">Перераспределяет отредактированную функцию, указав новое смещение промежуточного языка MSIL Microsoft</span><span class="sxs-lookup"><span data-stu-id="cea6d-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cea6d-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cea6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cea6d-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="cea6d-106">[in] Кадр стека по которому должен быть помещен указатель инструкции новое смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="cea6d-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="cea6d-107">Это значение должно являться точкой следования.</span><span class="sxs-lookup"><span data-stu-id="cea6d-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="cea6d-108">Это обязанность вызывающего, чтобы обеспечить правильность этого значения.</span><span class="sxs-lookup"><span data-stu-id="cea6d-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="cea6d-109">Например смещение MSIL является недопустимым, если он находится за пределами функции.</span><span class="sxs-lookup"><span data-stu-id="cea6d-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cea6d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cea6d-110">Remarks</span></span>  
 <span data-ttu-id="cea6d-111">Когда функция фрейма был изменен, то отладчик может вызвать `RemapFunction` замену в последней версии функции фрейма, поэтому он может выполняться методом.</span><span class="sxs-lookup"><span data-stu-id="cea6d-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="cea6d-112">Выполнение кода начинается с заданного смещения MSIL.</span><span class="sxs-lookup"><span data-stu-id="cea6d-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cea6d-113">Вызов `RemapFunction`, например вызов [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), немедленно сделает недействительными все интерфейсы отладки, которые связаны с генерацией трассировки стека для потока.</span><span class="sxs-lookup"><span data-stu-id="cea6d-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="cea6d-114">Такие интерфейсы включают [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame и ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="cea6d-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="cea6d-115">`RemapFunction` Метод может вызываться только в контексте текущего кадра и только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="cea6d-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="cea6d-116">После получения [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) обратный вызов, который еще не был продолжен.</span><span class="sxs-lookup"><span data-stu-id="cea6d-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="cea6d-117">Когда выполнение кода остановлен из-за [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) событий для данного кадра.</span><span class="sxs-lookup"><span data-stu-id="cea6d-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cea6d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="cea6d-118">Requirements</span></span>  
 <span data-ttu-id="cea6d-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cea6d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea6d-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cea6d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cea6d-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cea6d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cea6d-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea6d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
