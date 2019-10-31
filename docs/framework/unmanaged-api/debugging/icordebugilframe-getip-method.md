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
ms.openlocfilehash: 7e1605eede55360e72d65da6744bc1dcce4f107f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130988"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="5ca31-102">Метод ICorDebugILFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="5ca31-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="5ca31-103">Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="5ca31-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ca31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ca31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ca31-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="5ca31-106">заполняет Значение указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="5ca31-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="5ca31-107">заполняет Указатель на побитовую комбинацию значений перечисления Кордебугмаппингресулт, описывающих, как было получено значение указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="5ca31-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ca31-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="5ca31-108">Remarks</span></span>  
 <span data-ttu-id="5ca31-109">Значение указателя инструкции является смещением кадра стека в коде MSIL для функции.</span><span class="sxs-lookup"><span data-stu-id="5ca31-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="5ca31-110">Если кадр стека активен, то этот адрес является следующей инструкцией для выполнения.</span><span class="sxs-lookup"><span data-stu-id="5ca31-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="5ca31-111">Если кадр стека неактивен, этот адрес является следующей инструкцией для выполнения при повторной активации кадра стека.</span><span class="sxs-lookup"><span data-stu-id="5ca31-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="5ca31-112">Если этот кадр является JIT-скомпилированным кадром, то значение указателя инструкции будет определяться в обратном направлении от фактического указателя инструкций в машинном виде, поэтому значение может быть только приблизительным.</span><span class="sxs-lookup"><span data-stu-id="5ca31-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ca31-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5ca31-113">Requirements</span></span>  
 <span data-ttu-id="5ca31-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ca31-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ca31-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ca31-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ca31-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ca31-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ca31-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca31-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
