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
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792807"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="dca1a-102">Метод ICorDebugNativeFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="dca1a-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="dca1a-103">Возвращает значение HRESULT, указывающее, можно ли задать для указателя инструкций (IP) заданное положение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="dca1a-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dca1a-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dca1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dca1a-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="dca1a-106">окне Требуемый параметр для указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="dca1a-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dca1a-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="dca1a-107">Remarks</span></span>  
 <span data-ttu-id="dca1a-108">Перед вызовом метода [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) используйте метод `CanSetIP`.</span><span class="sxs-lookup"><span data-stu-id="dca1a-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="dca1a-109">Если `CanSetIP` возвращает любое значение HRESULT, отличное от S_OK, вы по-прежнему можете вызывать `ICorDebugNativeFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит безопасность и правильное выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="dca1a-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca1a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dca1a-110">Requirements</span></span>  
 <span data-ttu-id="dca1a-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dca1a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca1a-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dca1a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dca1a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dca1a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dca1a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca1a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca1a-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="dca1a-115">See also</span></span>
