---
title: Метод ICorDebugFunction3::GetActiveReJitRequestILCode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6268019f2e65c7c9209e00c0b6065e91103980c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115886"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="c237c-102">Метод ICorDebugFunction3::GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="c237c-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="c237c-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="c237c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c237c-104">Получает указатель интерфейса на [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий промежуточный язык из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="c237c-104">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c237c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c237c-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c237c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c237c-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="c237c-107">Указатель на промежуточный язык из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="c237c-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c237c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c237c-108">Remarks</span></span>  
 <span data-ttu-id="c237c-109">Если метод, представленный этим объектом `ICorDebugFunction3`, имеет активный запрос ReJIT, `ppReJitedILCode` возвращает указатель на его промежуточный язык.</span><span class="sxs-lookup"><span data-stu-id="c237c-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="c237c-110">Есть ли отсутствие активного запроса, который чаще всего, затем `ppReJitedILCode` — **null**.</span><span class="sxs-lookup"><span data-stu-id="c237c-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="c237c-111">Запрос ReJIT становится активным, сразу после выполнения возвращает из [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) вызова метода.</span><span class="sxs-lookup"><span data-stu-id="c237c-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="c237c-112">Он еще не быть может скомпилирован JIT, а потоки могут по-прежнему выполняться в исходной версии кода.</span><span class="sxs-lookup"><span data-stu-id="c237c-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="c237c-113">Запрос ReJIT становится неактивным во время вызова профилировщика [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c237c-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="c237c-114">Даже после возврата промежуточного языка поток может все еще выполняться в коде, перекомпилированном JIT (ReJIT).</span><span class="sxs-lookup"><span data-stu-id="c237c-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c237c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c237c-115">Requirements</span></span>  
 <span data-ttu-id="c237c-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c237c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c237c-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c237c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c237c-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c237c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c237c-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c237c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c237c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c237c-120">See also</span></span>

- [<span data-ttu-id="c237c-121">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="c237c-121">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)
- [<span data-ttu-id="c237c-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c237c-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c237c-123">ReJIT: Практическое руководство</span><span class="sxs-lookup"><span data-stu-id="c237c-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
