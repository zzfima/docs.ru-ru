---
title: "Метод ICorDebugNativeFrame::SetIP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25b4f42eb6f10ecade468824d9d790a2bce740a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="2f3c3-102">Метод ICorDebugNativeFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="2f3c3-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="2f3c3-103">Задает указатель инструкций заданное расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f3c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f3c3-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f3c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f3c3-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="2f3c3-106">[in] Расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f3c3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f3c3-107">Remarks</span></span>  
 <span data-ttu-id="2f3c3-108">Вызовы `SetIP` немедленно сделать недействительными все фреймы и цепочки для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="2f3c3-109">Если отладчик сведениях о кадрах после вызова `SetIP`, он должен выполнить новую трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="2f3c3-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) предпримет попытку сохранить кадр стека в допустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="2f3c3-111">Тем не менее даже если кадр находится в допустимом состоянии, как среды выполнения, по-прежнему возможно проблемы, такие как неинициализированных локальных переменных и т. д.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="2f3c3-112">Вызывающий объект отвечает за обеспечение согласованности выполняемой программы.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="2f3c3-113">На 64-разрядных платформах, не может быть перемещен указатель инструкций из `catch` или `finally` блока.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="2f3c3-114">Если `SetIP` вызывается для выполнения такого перемещения на 64-разрядной платформе, она возвратит значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="2f3c3-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f3c3-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2f3c3-115">Requirements</span></span>  
 <span data-ttu-id="2f3c3-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f3c3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f3c3-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f3c3-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f3c3-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f3c3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f3c3-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f3c3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3c3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2f3c3-120">See Also</span></span>  
 
