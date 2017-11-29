---
title: "Метод ICorDebugILFrame4::GetCodeEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetLocalVariableEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc80882353bd7a9861f4db79b83493d1cef7bfee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="dd9af-102">Метод ICorDebugILFrame4::GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="dd9af-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="dd9af-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="dd9af-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dd9af-104">Получает указатель на код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="dd9af-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd9af-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd9af-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd9af-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd9af-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="dd9af-107">[in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) член перечисления, указывающее, включается ли в кадре промежуточного языка (IL), определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="dd9af-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="dd9af-108">[out] Указатель на адрес объекта «ICorDebugCode», который представляет код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="dd9af-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd9af-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd9af-109">Remarks</span></span>  
 <span data-ttu-id="dd9af-110">Этот метод аналогичен [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) за исключением того, что он дополнительно получает доступ к коду, определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="dd9af-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="dd9af-111">Вызов этого метода с `flags` значение `ILCODE_ORIGINAL_IL` эквивалентно вызову [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); Если этот метод инструментирован, его IL станут недоступны.</span><span class="sxs-lookup"><span data-stu-id="dd9af-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="dd9af-112">`ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="dd9af-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="dd9af-113">Если промежуточный язык не инструментирован, `ppCode` — **null**, а метод возвращает `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="dd9af-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd9af-114">Требования</span><span class="sxs-lookup"><span data-stu-id="dd9af-114">Requirements</span></span>  
 <span data-ttu-id="dd9af-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd9af-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd9af-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd9af-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd9af-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd9af-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd9af-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd9af-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9af-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dd9af-119">See Also</span></span>  
 [<span data-ttu-id="dd9af-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="dd9af-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="dd9af-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dd9af-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dd9af-122">ReJIT: Практические руководства</span><span class="sxs-lookup"><span data-stu-id="dd9af-122">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
