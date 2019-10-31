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
ms.openlocfilehash: 60273d7cf91be04c5fc3041260e4bb146ce9a45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095435"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="585a4-102">Метод ICorDebugILFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="585a4-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="585a4-103">Задает указатель инструкции в указанном расположении смещения в коде промежуточного языка Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="585a4-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="585a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="585a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="585a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="585a4-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="585a4-106">Положение смещения в коде MSIL.</span><span class="sxs-lookup"><span data-stu-id="585a4-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="585a4-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="585a4-107">Remarks</span></span>  
 <span data-ttu-id="585a4-108">Вызовы `SetIP` немедленно делают недействительными все кадры и цепочки для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="585a4-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="585a4-109">Если отладчику требуются сведения о кадрах после вызова `SetIP`, он должен выполнить новую трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="585a4-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="585a4-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) попытается удержать кадр стека в допустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="585a4-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="585a4-111">Тем не менее, даже если кадр находится в допустимом состоянии, могут возникнуть проблемы, например неинициализированные локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="585a4-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="585a4-112">Вызывающий объект отвечает за обеспечение согласованности выполняющейся программы.</span><span class="sxs-lookup"><span data-stu-id="585a4-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="585a4-113">На 64-разрядных платформах указатель инструкции не может быть перемещен из `catch` или `finally` блока.</span><span class="sxs-lookup"><span data-stu-id="585a4-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="585a4-114">Если вызывается `SetIP`, чтобы выполнить такое перемещение на 64-разрядной платформе, он возвратит значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="585a4-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585a4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="585a4-115">Requirements</span></span>  
 <span data-ttu-id="585a4-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="585a4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585a4-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="585a4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="585a4-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="585a4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="585a4-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585a4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
