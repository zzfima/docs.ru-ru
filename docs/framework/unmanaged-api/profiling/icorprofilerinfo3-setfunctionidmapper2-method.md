---
title: Метод ICorProfilerInfo3::SetFunctionIDMapper2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d04c15fa181d0e7bf8a92c1b6ecdef5b8b13bd7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182433"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="15f42-102">Метод ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="15f42-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="15f42-103">Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика.</span><span class="sxs-lookup"><span data-stu-id="15f42-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="15f42-104">Этот метод расширяет [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) метод с параметром дополнительные данные, которого профилировщики могут различать среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="15f42-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f42-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15f42-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15f42-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="15f42-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="15f42-107">[in] Указатель на [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) реализации, который будет вызываться для сопоставления `FunctionID` значений к значениям альтернативные.</span><span class="sxs-lookup"><span data-stu-id="15f42-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="15f42-108">[in] Указатель, который передается в каждый [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) функции вызова методом текущей среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="15f42-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="15f42-109">Профилировщик можно использовать эту информацию для однозначного определения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="15f42-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15f42-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="15f42-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15f42-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="15f42-111">Remarks</span></span>  
 <span data-ttu-id="15f42-112">Альтернативы FunctionID значения передаются обработчикам входа и выхода функции профилировщика ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), и [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) ; или [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), и [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)), которые заданы [ SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) или [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="15f42-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="15f42-113">`FunctionIDMapper2` Метода можно задать только один раз; мы рекомендуем задавать [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="15f42-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f42-114">Требования</span><span class="sxs-lookup"><span data-stu-id="15f42-114">Requirements</span></span>  
 <span data-ttu-id="15f42-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f42-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f42-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15f42-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15f42-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15f42-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="15f42-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="15f42-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15f42-119">См. также</span><span class="sxs-lookup"><span data-stu-id="15f42-119">See also</span></span>

- [<span data-ttu-id="15f42-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="15f42-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="15f42-121">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="15f42-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="15f42-122">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="15f42-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="15f42-123">Профилирование</span><span class="sxs-lookup"><span data-stu-id="15f42-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
