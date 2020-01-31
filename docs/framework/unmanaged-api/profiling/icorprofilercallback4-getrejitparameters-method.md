---
title: Метод ICorProfilerCallback4::GetReJITParameters
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: 858d65783515a89a434cf719ef9d5a999643094c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865328"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="d7342-102">Метод ICorProfilerCallback4::GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="d7342-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="d7342-103">Позволяет профилировщику кода устанавливать альтернативные флаги создания кода для нового текста перекомпилированного метода.</span><span class="sxs-lookup"><span data-stu-id="d7342-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7342-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7342-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7342-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7342-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="d7342-106">окне Модуль, содержащий метод, для которого среда CLR требует параметры JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="d7342-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="d7342-107">окне `MethodDef` метода, для которого среда CLR требует параметры JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="d7342-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="d7342-108">окне Указатель на интерфейс [икорпрофилерфунктионконтрол](icorprofilerfunctioncontrol-interface.md) , который профилировщик может использовать для предоставления сведений о JIT-компиляции для метода, для которого выполняется повторная компиляция.</span><span class="sxs-lookup"><span data-stu-id="d7342-108">[in] A pointer to an [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7342-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="d7342-109">Remarks</span></span>  
 <span data-ttu-id="d7342-110">Среда CLR выдает ответный вызов `GetReJITParameters`, чтобы профилировщик мог указать параметры для перекомпиляции данного метода.</span><span class="sxs-lookup"><span data-stu-id="d7342-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="d7342-111">Обратный вызов `GetReJITParameters` выдается только один раз для каждой функции; параметры, предоставляемые профилировщиком, применяются ко всем экземплярам этой функции.</span><span class="sxs-lookup"><span data-stu-id="d7342-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7342-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d7342-112">Requirements</span></span>  
 <span data-ttu-id="d7342-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7342-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7342-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7342-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7342-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7342-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7342-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7342-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7342-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7342-117">See also</span></span>

- [<span data-ttu-id="d7342-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d7342-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d7342-119">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="d7342-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="d7342-120">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d7342-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="d7342-121">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d7342-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
