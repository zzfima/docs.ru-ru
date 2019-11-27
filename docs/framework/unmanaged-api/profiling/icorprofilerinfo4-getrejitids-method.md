---
title: Метод ICorProfilerInfo4::GetReJITIDs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: f6d26abba649b608858fde8beaac750600493869
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442865"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="cb31b-102">Метод ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="cb31b-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="cb31b-103">Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены.</span><span class="sxs-lookup"><span data-stu-id="cb31b-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="cb31b-104">Сюда входят JIT-повторно скомпилированные версии функций, которые впоследствии были отменены, но еще не освобождены (например, если домен приложения, содержащий функцию, которая содержит возвращенные функции, все еще используется).</span><span class="sxs-lookup"><span data-stu-id="cb31b-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb31b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb31b-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb31b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb31b-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="cb31b-107">окне `FunctionID` экземпляра функции, для которой перечисляются версии.</span><span class="sxs-lookup"><span data-stu-id="cb31b-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="cb31b-108">окне Число идентификаторов с JIT-рекомпиляцией, выделенных в массиве `reJitIds`.</span><span class="sxs-lookup"><span data-stu-id="cb31b-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="cb31b-109">заполняет Фактическое число повторно скомпилированных идентификаторов с JIT-рекомпиляцией.</span><span class="sxs-lookup"><span data-stu-id="cb31b-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="cb31b-110">заполняет Выделенный вызывающим объектом массив, который будет содержать JIT-перекомпилированные идентификаторы для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="cb31b-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb31b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb31b-111">Remarks</span></span>  
 <span data-ttu-id="cb31b-112">`GetReJITIDs` перечисляет активные JIT-повторно скомпилированные идентификаторы для данного экземпляра функции.</span><span class="sxs-lookup"><span data-stu-id="cb31b-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="cb31b-113">Она соответствует той же схеме использования, что и другие функции `ICorProfilerInfo`, принимающие буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="cb31b-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb31b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cb31b-114">Requirements</span></span>  
 <span data-ttu-id="cb31b-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb31b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb31b-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb31b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb31b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb31b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb31b-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb31b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb31b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cb31b-119">See also</span></span>

- [<span data-ttu-id="cb31b-120">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="cb31b-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="cb31b-121">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="cb31b-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="cb31b-122">Профилирование</span><span class="sxs-lookup"><span data-stu-id="cb31b-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
