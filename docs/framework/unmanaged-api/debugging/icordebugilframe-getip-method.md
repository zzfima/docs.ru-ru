---
title: "Метод ICorDebugILFrame::GetIP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79b18c6fe15e28b2cec07ef9dfaa06ee295ab42d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="74306-102">Метод ICorDebugILFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="74306-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="74306-103">Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, каким образом было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="74306-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74306-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74306-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74306-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74306-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="74306-106">[out] Значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="74306-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="74306-107">[out] Указатель на побитовое сочетание значений перечисления CorDebugMappingResult, которые описывают, каким образом было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="74306-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74306-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="74306-108">Remarks</span></span>  
 <span data-ttu-id="74306-109">Значение указателя инструкций — смещение кадра стека функции код на промежуточном языке (MSIL).</span><span class="sxs-lookup"><span data-stu-id="74306-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="74306-110">Если кадр стека активен, этот адрес будет следующую инструкцию для выполнения.</span><span class="sxs-lookup"><span data-stu-id="74306-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="74306-111">Если кадр стека не активен, этот адрес будет следующую инструкцию для выполнения при повторной активации кадра стека.</span><span class="sxs-lookup"><span data-stu-id="74306-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="74306-112">Если этот кадр кадр скомпилированных just-in-time (JIT), значение указателя инструкций будет определяться обратного сопоставления фактического собственный указатель инструкции, поэтому значение может быть только приблизительным.</span><span class="sxs-lookup"><span data-stu-id="74306-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74306-113">Требования</span><span class="sxs-lookup"><span data-stu-id="74306-113">Requirements</span></span>  
 <span data-ttu-id="74306-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74306-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74306-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74306-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74306-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74306-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74306-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74306-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
