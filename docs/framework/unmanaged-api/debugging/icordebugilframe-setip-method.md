---
title: Метод ICorDebugILFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2af3f58fa7714b3c2b0ba387b1da650f0638dd6c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758774"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="d6b2d-102">Метод ICorDebugILFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="d6b2d-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="d6b2d-103">Задает указатель инструкций в указанное расположение смещения в код на промежуточном языке (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d6b2d-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6b2d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6b2d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6b2d-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="d6b2d-106">Расположение смещения в MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6b2d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6b2d-107">Remarks</span></span>  
 <span data-ttu-id="d6b2d-108">Вызовы `SetIP` немедленно сделать недействительными все фреймы и цепочки для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="d6b2d-109">Если отладчику требуется сведения о кадре после вызова `SetIP`, он должен выполнить новую трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="d6b2d-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) попытается сохранить кадр стека в допустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="d6b2d-111">Тем не менее, даже если кадр находится в допустимом состоянии, по-прежнему может существовать проблем, таких как неинициализированных локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="d6b2d-112">Вызывающий объект несет ответственность за обеспечение согласованности выполняемой программы.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="d6b2d-113">На 64-разрядных платформах, нельзя перемещать указатель инструкций из `catch` или `finally` блока.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="d6b2d-114">Если `SetIP` вызывается для выполнения такого перемещения на 64-разрядной платформе, возвращается значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="d6b2d-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6b2d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d6b2d-115">Requirements</span></span>  
 <span data-ttu-id="d6b2d-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6b2d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6b2d-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6b2d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6b2d-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6b2d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6b2d-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6b2d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
