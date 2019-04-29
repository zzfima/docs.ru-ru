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
ms.openlocfilehash: b92885d2a6514839a864d6a345dd8af8b07b90c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946527"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="27076-102">Метод ICorDebugILFrame2::RemapFunction</span><span class="sxs-lookup"><span data-stu-id="27076-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="27076-103">Перераспределяет отредактированную функцию, указав новое смещение промежуточного языка MSIL Microsoft</span><span class="sxs-lookup"><span data-stu-id="27076-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27076-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27076-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27076-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27076-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="27076-106">[in] Кадр стека по которому должен быть помещен указатель инструкции новое смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="27076-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="27076-107">Это значение должно являться точкой следования.</span><span class="sxs-lookup"><span data-stu-id="27076-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="27076-108">Это обязанность вызывающего, чтобы обеспечить правильность этого значения.</span><span class="sxs-lookup"><span data-stu-id="27076-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="27076-109">Например смещение MSIL является недопустимым, если он находится за пределами функции.</span><span class="sxs-lookup"><span data-stu-id="27076-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27076-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="27076-110">Remarks</span></span>  
 <span data-ttu-id="27076-111">Когда функция фрейма был изменен, то отладчик может вызвать `RemapFunction` замену в последней версии функции фрейма, поэтому он может выполняться методом.</span><span class="sxs-lookup"><span data-stu-id="27076-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="27076-112">Выполнение кода начинается с заданного смещения MSIL.</span><span class="sxs-lookup"><span data-stu-id="27076-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27076-113">Вызов `RemapFunction`, например вызов [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), немедленно сделает недействительными все интерфейсы отладки, которые связаны с генерацией трассировки стека для потока.</span><span class="sxs-lookup"><span data-stu-id="27076-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="27076-114">Такие интерфейсы включают [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame и ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="27076-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="27076-115">`RemapFunction` Метод может вызываться только в контексте текущего кадра и только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="27076-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="27076-116">После получения [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) обратный вызов, который еще не был продолжен.</span><span class="sxs-lookup"><span data-stu-id="27076-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="27076-117">Когда выполнение кода остановлен из-за [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) событий для данного кадра.</span><span class="sxs-lookup"><span data-stu-id="27076-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27076-118">Требования</span><span class="sxs-lookup"><span data-stu-id="27076-118">Requirements</span></span>  
 <span data-ttu-id="27076-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27076-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27076-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27076-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27076-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27076-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27076-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27076-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
