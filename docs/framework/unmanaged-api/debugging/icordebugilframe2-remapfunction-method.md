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
ms.openlocfilehash: f4f73b99b4cb48690a2a8611dbf5a5420adab5d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794353"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="77355-102">Метод ICorDebugILFrame2::RemapFunction</span><span class="sxs-lookup"><span data-stu-id="77355-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="77355-103">Повторно сопоставляет отредактированную функцию, указывая новое смещение MSIL</span><span class="sxs-lookup"><span data-stu-id="77355-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77355-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77355-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77355-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77355-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="77355-106">окне Новое смещение MSIL кадра стека, в которое следует поместить указатель инструкции.</span><span class="sxs-lookup"><span data-stu-id="77355-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="77355-107">Это значение должно быть точкой последовательности.</span><span class="sxs-lookup"><span data-stu-id="77355-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="77355-108">Для обеспечения допустимости этого значения отвечает вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="77355-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="77355-109">Например, смещение MSIL недопустимо, если оно находится вне границ функции.</span><span class="sxs-lookup"><span data-stu-id="77355-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77355-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="77355-110">Remarks</span></span>  
 <span data-ttu-id="77355-111">Когда функция кадра была изменена, отладчик может вызвать метод `RemapFunction` для замены последней версии функции кадра, чтобы ее можно было выполнить.</span><span class="sxs-lookup"><span data-stu-id="77355-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="77355-112">Выполнение кода начнется с заданного смещения MSIL.</span><span class="sxs-lookup"><span data-stu-id="77355-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77355-113">Вызов `RemapFunction`, например вызов [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md), немедленно сделает недействительными все интерфейсы отладки, связанные с формированием трассировки стека для потока.</span><span class="sxs-lookup"><span data-stu-id="77355-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="77355-114">К этим интерфейсам относятся [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame и ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="77355-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="77355-115">Метод `RemapFunction` можно вызывать только в контексте текущего кадра и только в одном из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="77355-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="77355-116">После получения обратного вызова [ICorDebugManagedCallback2:: FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) , который еще не был продолжен.</span><span class="sxs-lookup"><span data-stu-id="77355-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="77355-117">Пока выполнение кода остановлено из-за события [ICorDebugManagedCallback:: EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) для этого кадра.</span><span class="sxs-lookup"><span data-stu-id="77355-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77355-118">Требования</span><span class="sxs-lookup"><span data-stu-id="77355-118">Requirements</span></span>  
 <span data-ttu-id="77355-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77355-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77355-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77355-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77355-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77355-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77355-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77355-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
