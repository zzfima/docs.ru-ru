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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24be4507e8ad6cde1e9c50582e352f0fc9b12ed3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43886491"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="8c6b0-102">Метод ICorDebugILFrame4::GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="8c6b0-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="8c6b0-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="8c6b0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="8c6b0-104">Получает указатель на код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="8c6b0-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c6b0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c6b0-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c6b0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c6b0-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="8c6b0-107">[in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) член перечисления, указывающее, включается ли в кадр промежуточный язык (IL), определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8c6b0-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="8c6b0-108">[out] Указатель на адрес объекта «ICorDebugCode», который представляет код, который в этом кадре стека.</span><span class="sxs-lookup"><span data-stu-id="8c6b0-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c6b0-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c6b0-109">Remarks</span></span>  
 <span data-ttu-id="8c6b0-110">Этот метод аналогичен методу [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) за тем исключением, что он дополнительно получает доступ к коду, определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8c6b0-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="8c6b0-111">Вызов этого метода с `flags` значение `ILCODE_ORIGINAL_IL` эквивалентно вызову [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); Если этот метод инструментирован, его IL будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="8c6b0-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="8c6b0-112">`ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8c6b0-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="8c6b0-113">Если промежуточный язык не инструментирован, `ppCode` — **null**, а метод возвращает `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="8c6b0-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c6b0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8c6b0-114">Requirements</span></span>  
 <span data-ttu-id="8c6b0-115">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c6b0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c6b0-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c6b0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c6b0-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c6b0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c6b0-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c6b0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6b0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8c6b0-119">See Also</span></span>  
 [<span data-ttu-id="8c6b0-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="8c6b0-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="8c6b0-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c6b0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8c6b0-122">ReJIT: Практическое руководство</span><span class="sxs-lookup"><span data-stu-id="8c6b0-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
