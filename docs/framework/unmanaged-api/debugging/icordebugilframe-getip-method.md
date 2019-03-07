---
title: Метод ICorDebugILFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a7b8985e7580282d0e38205f9b1d6078f86cee6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479770"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="83d0b-102">Метод ICorDebugILFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="83d0b-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="83d0b-103">Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, как было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="83d0b-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83d0b-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83d0b-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="83d0b-106">[out] Значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="83d0b-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="83d0b-107">[out] Указатель на побитовое сочетание значений перечисления CorDebugMappingResult, которые описывают, каким образом было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="83d0b-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83d0b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="83d0b-108">Remarks</span></span>  
 <span data-ttu-id="83d0b-109">Значение указателя инструкций — это смещение кадра стека в код на промежуточном языке (MSIL) функции.</span><span class="sxs-lookup"><span data-stu-id="83d0b-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="83d0b-110">Если кадр стека активен, этот адрес является следующей инструкции для выполнения.</span><span class="sxs-lookup"><span data-stu-id="83d0b-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="83d0b-111">Если кадр стека не активен, этот адрес соответствует следующей инструкции для выполнения при повторной активации кадра стека.</span><span class="sxs-lookup"><span data-stu-id="83d0b-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="83d0b-112">Если этого кадра кадр скомпилированного just-in-time (JIT), значение указателя инструкций будет определяться путем обратного сопоставления фактического собственный указатель инструкции, поэтому значение может быть только приблизительное.</span><span class="sxs-lookup"><span data-stu-id="83d0b-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d0b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="83d0b-113">Requirements</span></span>  
 <span data-ttu-id="83d0b-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83d0b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83d0b-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83d0b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83d0b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83d0b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83d0b-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83d0b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
