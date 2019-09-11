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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 805ceb60d2ac122df2382656b95b7bf5e7509bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855942"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="1e5df-102">Метод ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="1e5df-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="1e5df-103">Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены.</span><span class="sxs-lookup"><span data-stu-id="1e5df-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="1e5df-104">Сюда входят JIT-повторно скомпилированные версии функций, которые впоследствии были отменены, но еще не освобождены (например, если домен приложения, содержащий функцию, которая содержит возвращенные функции, все еще используется).</span><span class="sxs-lookup"><span data-stu-id="1e5df-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e5df-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e5df-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e5df-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e5df-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="1e5df-107">окне Объект `FunctionID` экземпляра функции, для которого требуется перечислить версии.</span><span class="sxs-lookup"><span data-stu-id="1e5df-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="1e5df-108">окне Число идентификаторов, перекомпилированных с помощью JIT-компилятора `reJitIds` , выделенных в массиве.</span><span class="sxs-lookup"><span data-stu-id="1e5df-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="1e5df-109">заполняет Фактическое число повторно скомпилированных идентификаторов с JIT-рекомпиляцией.</span><span class="sxs-lookup"><span data-stu-id="1e5df-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="1e5df-110">заполняет Выделенный вызывающим объектом массив, который будет содержать JIT-перекомпилированные идентификаторы для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="1e5df-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e5df-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e5df-111">Remarks</span></span>  
 <span data-ttu-id="1e5df-112">`GetReJITIDs`Перечисляет активные JIT-повторно скомпилированные идентификаторы для заданного экземпляра функции.</span><span class="sxs-lookup"><span data-stu-id="1e5df-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="1e5df-113">Он следует той же схеме использования, что `ICorProfilerInfo` и другие функции, принимающие буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="1e5df-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e5df-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1e5df-114">Requirements</span></span>  
 <span data-ttu-id="1e5df-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e5df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e5df-116">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1e5df-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e5df-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="1e5df-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e5df-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e5df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5df-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1e5df-119">See also</span></span>

- [<span data-ttu-id="1e5df-120">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="1e5df-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="1e5df-121">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="1e5df-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="1e5df-122">Профилирование</span><span class="sxs-lookup"><span data-stu-id="1e5df-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
