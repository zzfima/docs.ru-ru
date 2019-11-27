---
title: Метод ICorProfilerInfo::SetFunctionIDMapper
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 4ba3c378b93e3ae1ef288c0edabfacfcfd7070d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438676"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="658fe-102">Метод ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="658fe-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="658fe-103">Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика.</span><span class="sxs-lookup"><span data-stu-id="658fe-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="658fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="658fe-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="658fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="658fe-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="658fe-106">окне Указатель на реализацию [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) , которая будет вызываться для соответствия значений `FunctionID` их альтернативным значениям.</span><span class="sxs-lookup"><span data-stu-id="658fe-106">[in] A pointer to the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="658fe-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="658fe-107">Remarks</span></span>  
 <span data-ttu-id="658fe-108">Альтернативы `FunctionID` значения будут переданы обработчикам входа и выхода функций профилировщика ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)), заданным методом [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="658fe-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="658fe-109">`FunctionIDMapper` можно задать только один раз, поэтому рекомендуется задать его в обратном вызове [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="658fe-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="658fe-110">Требования</span><span class="sxs-lookup"><span data-stu-id="658fe-110">Requirements</span></span>  
 <span data-ttu-id="658fe-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="658fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="658fe-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="658fe-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="658fe-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="658fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="658fe-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="658fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658fe-115">См. также</span><span class="sxs-lookup"><span data-stu-id="658fe-115">See also</span></span>

- [<span data-ttu-id="658fe-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="658fe-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
