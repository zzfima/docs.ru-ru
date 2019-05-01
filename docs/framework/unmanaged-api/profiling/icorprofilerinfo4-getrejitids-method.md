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
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049483"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="c6824-102">Метод ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="c6824-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="c6824-103">Возвращает массив идентификаторов, определяющих все перекомпиляции JIT версии указанной функции, по-прежнему выделяются.</span><span class="sxs-lookup"><span data-stu-id="c6824-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="c6824-104">Сюда входят перекомпиляции JIT версии функций, которые впоследствии отменены, но еще не освобождены (например, когда домен приложения, содержащей функцию, возвращенного в предыдущее состояние по-прежнему используется).</span><span class="sxs-lookup"><span data-stu-id="c6824-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6824-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6824-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6824-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6824-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c6824-107">[in] `FunctionID` Экземпляра функции для перечисления версий.</span><span class="sxs-lookup"><span data-stu-id="c6824-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="c6824-108">[in] Количество идентификаторов перекомпиляции JIT, выделенных в `reJitIds` массива.</span><span class="sxs-lookup"><span data-stu-id="c6824-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="c6824-109">[out] Фактическое число идентификаторов перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="c6824-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="c6824-110">[out] Выделенный вызывающим объектом массив, который будет содержать идентификаторы перекомпиляции JIT для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="c6824-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6824-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6824-111">Remarks</span></span>  
 <span data-ttu-id="c6824-112">`GetReJITIDs` перечисляет идентификаторы active перекомпиляции JIT для заданной функции экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c6824-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="c6824-113">Он используется та же схема использования как другой `ICorProfilerInfo` функции, принимающие буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="c6824-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6824-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c6824-114">Requirements</span></span>  
 <span data-ttu-id="c6824-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6824-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6824-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6824-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6824-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6824-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6824-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6824-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6824-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c6824-119">See also</span></span>

- [<span data-ttu-id="c6824-120">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="c6824-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="c6824-121">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="c6824-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c6824-122">Профилирование</span><span class="sxs-lookup"><span data-stu-id="c6824-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
