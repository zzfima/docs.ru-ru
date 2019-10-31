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
ms.openlocfilehash: 1d978cab0817af68356d95d635f8d2bfa3fd546a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096739"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="03b4b-102">Метод ICorDebugNativeFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="03b4b-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="03b4b-103">Задает указатель инструкции в указанном расположении смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="03b4b-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03b4b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03b4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="03b4b-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="03b4b-106">окне Положение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="03b4b-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03b4b-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="03b4b-107">Remarks</span></span>  
 <span data-ttu-id="03b4b-108">Вызовы `SetIP` немедленно делают недействительными все кадры и цепочки для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="03b4b-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="03b4b-109">Если отладчику требуются сведения о кадрах после вызова `SetIP`, он должен выполнить новую трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="03b4b-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="03b4b-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) попытается удержать кадр стека в допустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="03b4b-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="03b4b-111">Однако даже если кадр находится в допустимом состоянии, то, что касается среды выполнения, могут возникнуть проблемы, например неинициализированные локальные переменные и т. д.</span><span class="sxs-lookup"><span data-stu-id="03b4b-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="03b4b-112">Вызывающий объект отвечает за выполнение согласованности выполняющейся программы.</span><span class="sxs-lookup"><span data-stu-id="03b4b-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="03b4b-113">На 64-разрядных платформах указатель инструкции не может быть перемещен из `catch` или `finally` блока.</span><span class="sxs-lookup"><span data-stu-id="03b4b-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="03b4b-114">Если вызывается `SetIP`, чтобы выполнить такое перемещение на 64-разрядной платформе, он возвратит значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="03b4b-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03b4b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="03b4b-115">Requirements</span></span>  
 <span data-ttu-id="03b4b-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03b4b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03b4b-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03b4b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03b4b-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03b4b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03b4b-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03b4b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b4b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="03b4b-120">See also</span></span>
