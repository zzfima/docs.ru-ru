---
title: Метод ICorDebugILFrame4::GetCodeEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178784"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="197c4-102">Метод ICorDebugILFrame4::GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="197c4-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="197c4-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="197c4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="197c4-104">Получает указатель на код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="197c4-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="197c4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="197c4-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="197c4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="197c4-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="197c4-107">(в) Участник [пересчета ILCodeKind,](ilcodekind-enumeration.md) который определяет, включен ли в кадр промежуточный язык (IL), определяемый запросом ReJIT профайлера.</span><span class="sxs-lookup"><span data-stu-id="197c4-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="197c4-108">(ваут) Указатель на адрес объекта "ICorDebugCode", представляющий код, который исполняется в этом стека.</span><span class="sxs-lookup"><span data-stu-id="197c4-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="197c4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="197c4-109">Remarks</span></span>  
 <span data-ttu-id="197c4-110">Этот метод аналогичен методу [ICorDebugFrame::GetCode,](icordebugframe-getcode-method.md) за исключением того, что он дополнительно получает доступ к коду, определенному запросом ReJIT профайлера.</span><span class="sxs-lookup"><span data-stu-id="197c4-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="197c4-111">Вызов этого метода `flags` `ILCODE_ORIGINAL_IL` со значением эквивалентно вызову [GetCode;](icordebugframe-getcode-method.md) если метод инструментальный, его IL не будет доступен.</span><span class="sxs-lookup"><span data-stu-id="197c4-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="197c4-112">`ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="197c4-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="197c4-113">Если IL не инструментальный, `ppCode` является **недействительным,** `S_OK`и метод возвращается .</span><span class="sxs-lookup"><span data-stu-id="197c4-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="197c4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="197c4-114">Requirements</span></span>  
 <span data-ttu-id="197c4-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="197c4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="197c4-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="197c4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="197c4-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="197c4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="197c4-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="197c4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="197c4-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="197c4-119">See also</span></span>

- [<span data-ttu-id="197c4-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="197c4-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="197c4-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="197c4-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="197c4-122">ReJIT: Как-к руководству</span><span class="sxs-lookup"><span data-stu-id="197c4-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
