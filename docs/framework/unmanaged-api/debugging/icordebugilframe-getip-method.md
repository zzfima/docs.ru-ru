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
ms.openlocfilehash: bd421d705a96778159cb80ad92d9ac654e88985f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414070"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="79246-102">Метод ICorDebugILFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="79246-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="79246-103">Возвращает значение указателя инструкций и битовую комбинацию значение, которое описывает, каким образом было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="79246-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79246-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79246-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79246-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79246-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="79246-106">[out] Значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="79246-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="79246-107">[out] Указатель на побитовое сочетание значений перечисления CorDebugMappingResult, которые описывают, каким образом было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="79246-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79246-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="79246-108">Remarks</span></span>  
 <span data-ttu-id="79246-109">Значение указателя инструкций — смещение кадра стека функции код на промежуточном языке (MSIL).</span><span class="sxs-lookup"><span data-stu-id="79246-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="79246-110">Если кадр стека активен, этот адрес будет следующую инструкцию для выполнения.</span><span class="sxs-lookup"><span data-stu-id="79246-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="79246-111">Если кадр стека не активен, этот адрес будет следующую инструкцию для выполнения при повторной активации кадра стека.</span><span class="sxs-lookup"><span data-stu-id="79246-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="79246-112">Если этот кадр кадр скомпилированных just-in-time (JIT), значение указателя инструкций будет определяться обратного сопоставления фактического собственный указатель инструкции, поэтому значение может быть только приблизительным.</span><span class="sxs-lookup"><span data-stu-id="79246-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79246-113">Требования</span><span class="sxs-lookup"><span data-stu-id="79246-113">Requirements</span></span>  
 <span data-ttu-id="79246-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79246-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79246-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79246-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79246-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79246-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79246-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79246-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
