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
ms.openlocfilehash: e77344a99189ec8e234129262d45698c794dc249
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788517"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="304eb-102">Метод ICorDebugILFrame4::GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="304eb-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="304eb-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="304eb-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="304eb-104">Получает указатель на код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="304eb-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="304eb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="304eb-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="304eb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="304eb-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="304eb-107">окне Элемент перечисления [ILCodeKind](ilcodekind-enumeration.md) , указывающий, включается ли в кадр промежуточный язык (IL), определенный в запросе ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="304eb-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="304eb-108">заполняет Указатель на адрес объекта ICorDebugCode, который представляет код, который исполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="304eb-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="304eb-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="304eb-109">Remarks</span></span>  
 <span data-ttu-id="304eb-110">Этот метод аналогичен методу [ICorDebugFrame::-Code](icordebugframe-getcode-method.md) , за исключением того, что он дополнительно получает доступ к коду, определенному в запросе ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="304eb-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="304eb-111">Вызов этого метода с `flags` значением `ILCODE_ORIGINAL_IL` эквивалентно вызову метода " [код](icordebugframe-getcode-method.md)"; Если метод инструментирован, его IL будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="304eb-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="304eb-112">`ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="304eb-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="304eb-113">Если IL не инструментирован, `ppCode` имеет **значение NULL**, а метод возвращает `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="304eb-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="304eb-114">Требования</span><span class="sxs-lookup"><span data-stu-id="304eb-114">Requirements</span></span>  
 <span data-ttu-id="304eb-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="304eb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="304eb-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="304eb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="304eb-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="304eb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="304eb-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="304eb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="304eb-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="304eb-119">See also</span></span>

- [<span data-ttu-id="304eb-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="304eb-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="304eb-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="304eb-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="304eb-122">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="304eb-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
