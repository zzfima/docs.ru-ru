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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e5d9c9596d0bb5e61bd7aed4caaa986759cfa54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455739"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="b304f-102">Метод ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="b304f-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="b304f-103">Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика.</span><span class="sxs-lookup"><span data-stu-id="b304f-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b304f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b304f-104">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b304f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b304f-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="b304f-106">[in] Указатель на [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) реализацию, которая будет вызвана для сопоставления `FunctionID` значения для их альтернативных значений.</span><span class="sxs-lookup"><span data-stu-id="b304f-106">[in] A pointer to the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b304f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b304f-107">Remarks</span></span>  
 <span data-ttu-id="b304f-108">Альтернативы `FunctionID` значения будут передаваться обработчикам входа и выхода для функции профилировщика ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) которые заданы в [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b304f-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="b304f-109">`FunctionIDMapper` Можно задать только один раз, и рекомендуется задать в [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="b304f-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b304f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b304f-110">Requirements</span></span>  
 <span data-ttu-id="b304f-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b304f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b304f-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b304f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b304f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b304f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b304f-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b304f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b304f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b304f-115">See Also</span></span>  
 [<span data-ttu-id="b304f-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b304f-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
