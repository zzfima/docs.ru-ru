---
title: "Метод ICorDebugFunction3::GetActiveReJitRequestILCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugFunction3.GetActiveReJitRequestILCode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6459297a2a04728ca87801bfc8484acec384a45c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="b7676-102">Метод ICorDebugFunction3::GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="b7676-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="b7676-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="b7676-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b7676-104">Возвращает указатель интерфейса [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий промежуточный язык из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="b7676-104">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7676-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7676-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7676-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7676-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="b7676-107">Указатель на промежуточный язык из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="b7676-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7676-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7676-108">Remarks</span></span>  
 <span data-ttu-id="b7676-109">Если метод, представленный этим объектом `ICorDebugFunction3`, имеет активный запрос ReJIT, `ppReJitedILCode` возвращает указатель на его промежуточный язык.</span><span class="sxs-lookup"><span data-stu-id="b7676-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="b7676-110">Существует ли отсутствие активного запроса, которое затем становится обычной практикой, `ppReJitedILCode` — **null**.</span><span class="sxs-lookup"><span data-stu-id="b7676-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="b7676-111">Запрос ReJIT становится активным, только выполнение возвращается из [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) вызова метода.</span><span class="sxs-lookup"><span data-stu-id="b7676-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="b7676-112">Он еще не быть может скомпилирован JIT, а потоки могут по-прежнему выполняться в исходной версии кода.</span><span class="sxs-lookup"><span data-stu-id="b7676-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="b7676-113">Запрос ReJIT становится неактивным во время вызова профилировщика [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b7676-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="b7676-114">Даже после возврата промежуточного языка поток может все еще выполняться в коде, перекомпилированном JIT (ReJIT).</span><span class="sxs-lookup"><span data-stu-id="b7676-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7676-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b7676-115">Requirements</span></span>  
 <span data-ttu-id="b7676-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7676-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7676-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7676-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7676-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7676-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7676-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7676-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7676-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b7676-120">See Also</span></span>  
 [<span data-ttu-id="b7676-121">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="b7676-121">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [<span data-ttu-id="b7676-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b7676-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b7676-123">ReJIT: Практические руководства</span><span class="sxs-lookup"><span data-stu-id="b7676-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
