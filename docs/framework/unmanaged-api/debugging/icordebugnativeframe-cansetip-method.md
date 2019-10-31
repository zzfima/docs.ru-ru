---
title: Метод ICorDebugNativeFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: b3758ac1a84092b8bf2678f9cc2c19c9d9961690
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137327"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="657e1-102">Метод ICorDebugNativeFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="657e1-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="657e1-103">Возвращает значение HRESULT, указывающее, можно ли задать для указателя инструкций (IP) заданное положение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="657e1-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="657e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="657e1-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="657e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="657e1-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="657e1-106">окне Требуемый параметр для указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="657e1-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="657e1-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="657e1-107">Remarks</span></span>  
 <span data-ttu-id="657e1-108">Перед вызовом метода [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) используйте метод `CanSetIP`.</span><span class="sxs-lookup"><span data-stu-id="657e1-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="657e1-109">Если `CanSetIP` возвращает любое значение HRESULT, отличное от S_OK, вы по-прежнему можете вызывать `ICorDebugNativeFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит безопасность и правильное выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="657e1-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="657e1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="657e1-110">Requirements</span></span>  
 <span data-ttu-id="657e1-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="657e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="657e1-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="657e1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="657e1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="657e1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="657e1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="657e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657e1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="657e1-115">See also</span></span>
