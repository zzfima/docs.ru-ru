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
ms.openlocfilehash: 5ceb1d22500f73a29ffdfa6f16907478628358c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969395"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="bed07-102">Метод ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="bed07-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="bed07-103">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="bed07-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bed07-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bed07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bed07-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="bed07-106">заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bed07-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bed07-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bed07-107">Remarks</span></span>  
 <span data-ttu-id="bed07-108">Этот метод может пересекаться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bed07-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="bed07-109">Перечислитель, возвращаемый этим методом, не включает функции, загруженные из образов в машинном кодах, созданных с помощью Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="bed07-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bed07-110">Возвращаемое перечисление содержит только значение "0" для значения `COR_PRF_FUNCTION::reJitId` поля.</span><span class="sxs-lookup"><span data-stu-id="bed07-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="bed07-111">Если требуются допустимые `COR_PRF_FUNCTION::reJitId` значения, используйте метод [метод icorprofilerinfo4:: EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bed07-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bed07-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bed07-112">Requirements</span></span>  
 <span data-ttu-id="bed07-113">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bed07-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bed07-114">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="bed07-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bed07-115">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="bed07-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bed07-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bed07-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed07-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bed07-117">See also</span></span>

- [<span data-ttu-id="bed07-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="bed07-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="bed07-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="bed07-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="bed07-120">Профилирование</span><span class="sxs-lookup"><span data-stu-id="bed07-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
