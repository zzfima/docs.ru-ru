---
title: Метод ICorDebugNativeFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 604486a074c3dbe3d19b741df28499ee03e1b2e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193282"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="d27b2-102">Метод ICorDebugNativeFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="d27b2-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="d27b2-103">Задает указатель инструкций в указанное расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="d27b2-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d27b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d27b2-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d27b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d27b2-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="d27b2-106">[in] Расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="d27b2-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d27b2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d27b2-107">Remarks</span></span>  
 <span data-ttu-id="d27b2-108">Вызовы `SetIP` немедленно сделать недействительными все фреймы и цепочки для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="d27b2-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="d27b2-109">Если отладчику требуется сведения о кадре после вызова `SetIP`, он должен выполнить новую трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="d27b2-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="d27b2-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) попытается сохранить кадр стека в допустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="d27b2-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="d27b2-111">Тем не менее, даже если кадр находится в допустимом состоянии, как среды выполнения, по-прежнему может существовать проблемы, такие как неинициализированных локальных переменных и т. д.</span><span class="sxs-lookup"><span data-stu-id="d27b2-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="d27b2-112">Вызывающий объект несет ответственность за обеспечение согласованности выполняемой программы.</span><span class="sxs-lookup"><span data-stu-id="d27b2-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="d27b2-113">На 64-разрядных платформах, нельзя перемещать указатель инструкций из `catch` или `finally` блока.</span><span class="sxs-lookup"><span data-stu-id="d27b2-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="d27b2-114">Если `SetIP` вызывается для выполнения такого перемещения на 64-разрядной платформе, возвращается значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="d27b2-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d27b2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d27b2-115">Requirements</span></span>  
 <span data-ttu-id="d27b2-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d27b2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27b2-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d27b2-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d27b2-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d27b2-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d27b2-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d27b2-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d27b2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d27b2-120">See also</span></span>
