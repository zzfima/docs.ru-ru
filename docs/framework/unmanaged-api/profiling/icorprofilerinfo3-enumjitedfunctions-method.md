---
title: Метод ICorProfilerInfo3::EnumJITedFunctions
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7525d107fec7229d9b86eee63bde2aaf2d701b1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000653"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="47452-102">Метод ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="47452-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="47452-103">Возвращает перечислитель для всех функций, которые были ранее JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="47452-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47452-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47452-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47452-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47452-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="47452-106">[out] Указатель на [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) перечислителя.</span><span class="sxs-lookup"><span data-stu-id="47452-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47452-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="47452-107">Remarks</span></span>  
 <span data-ttu-id="47452-108">Этот метод может перекрываться с `JITCompilation` обратные вызовы, такие как [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="47452-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="47452-109">Перечислитель, который возвращается этим методом не включает функции, загруженные из собственных образов, созданных с помощью Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="47452-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47452-110">Включает только «0» для значение возвращенного перечисления `COR_PRF_FUNCTION::reJitId` поля.</span><span class="sxs-lookup"><span data-stu-id="47452-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="47452-111">Если требуется допустимый `COR_PRF_FUNCTION::reJitId` значения, используйте [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="47452-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47452-112">Требования</span><span class="sxs-lookup"><span data-stu-id="47452-112">Requirements</span></span>  
 <span data-ttu-id="47452-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47452-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47452-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47452-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47452-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47452-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47452-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47452-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47452-117">См. также</span><span class="sxs-lookup"><span data-stu-id="47452-117">See also</span></span>

- [<span data-ttu-id="47452-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="47452-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="47452-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="47452-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="47452-120">Профилирование</span><span class="sxs-lookup"><span data-stu-id="47452-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
