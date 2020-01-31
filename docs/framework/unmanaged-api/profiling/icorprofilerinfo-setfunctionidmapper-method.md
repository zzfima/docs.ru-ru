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
ms.openlocfilehash: 52ab9a089b5def4f3db2f99abc5a718d66cca739
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863456"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="65793-102">Метод ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="65793-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="65793-103">Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика.</span><span class="sxs-lookup"><span data-stu-id="65793-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65793-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65793-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65793-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65793-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="65793-106">окне Указатель на реализацию [FunctionIDMapper](functionidmapper-function.md) , которая будет вызываться для соответствия значений `FunctionID` их альтернативным значениям.</span><span class="sxs-lookup"><span data-stu-id="65793-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65793-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="65793-107">Remarks</span></span>  
 <span data-ttu-id="65793-108">Альтернативы `FunctionID` значения будут переданы обработчикам входа и выхода функций профилировщика ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)и [FunctionTailcall2](functiontailcall2-function.md)), заданным методом [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="65793-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="65793-109">`FunctionIDMapper` можно задать только один раз, поэтому рекомендуется задать его в обратном вызове [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="65793-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65793-110">Требования</span><span class="sxs-lookup"><span data-stu-id="65793-110">Requirements</span></span>  
 <span data-ttu-id="65793-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65793-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65793-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65793-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65793-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65793-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65793-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65793-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65793-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="65793-115">See also</span></span>

- [<span data-ttu-id="65793-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="65793-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
