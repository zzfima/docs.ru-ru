---
title: Метод ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: 3011a8c7e5cf278768587633967b2e9491cf87ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137339"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="38591-102">Метод ICorDebugNativeFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="38591-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="38591-103">Возвращает расположение смещения машинного кода, в котором в данный момент установлен указатель инструкции.</span><span class="sxs-lookup"><span data-stu-id="38591-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38591-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38591-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38591-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38591-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="38591-106">заполняет Указатель на положение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="38591-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38591-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="38591-107">Remarks</span></span>  
 <span data-ttu-id="38591-108">Если кадр стека, представленный этим «ICorDebugNativeFrame», активен, то смещение — это адрес следующей инструкции, которая будет выполнена.</span><span class="sxs-lookup"><span data-stu-id="38591-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="38591-109">Если этот кадр стека неактивен, то смещение является адресом следующей инструкции, которая будет выполнена при повторной активации кадра стека.</span><span class="sxs-lookup"><span data-stu-id="38591-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38591-110">Требования</span><span class="sxs-lookup"><span data-stu-id="38591-110">Requirements</span></span>  
 <span data-ttu-id="38591-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38591-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38591-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38591-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38591-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38591-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38591-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38591-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38591-115">См. также</span><span class="sxs-lookup"><span data-stu-id="38591-115">See also</span></span>
