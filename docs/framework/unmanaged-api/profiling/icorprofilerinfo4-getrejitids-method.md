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
ms.openlocfilehash: 1055366576f45a7ca137b6d8170d1786c2ba4492
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455345"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="4bdd0-102">Метод ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="4bdd0-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="4bdd0-103">Возвращает массив идентификаторов, определяющих все JIT-компилятора версии указанной функции, по-прежнему выделяются.</span><span class="sxs-lookup"><span data-stu-id="4bdd0-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="4bdd0-104">Это включает JIT-компилятора версии функций, которые впоследствии восстановить, но еще не освобождены (например, когда домен приложения, содержащей функцию, возвращенного в предыдущее состояние до сих пор используется).</span><span class="sxs-lookup"><span data-stu-id="4bdd0-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bdd0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bdd0-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bdd0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4bdd0-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4bdd0-107">[in] `FunctionID` Экземпляра функции для перечисления версий.</span><span class="sxs-lookup"><span data-stu-id="4bdd0-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="4bdd0-108">[in] Число идентификаторов JIT-компилятора, выделенных в `reJitIds` массива.</span><span class="sxs-lookup"><span data-stu-id="4bdd0-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="4bdd0-109">[out] Фактическое количество идентификаторов с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="4bdd0-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="4bdd0-110">[out] Выделенный вызывающим объектом массив, который будет содержать идентификаторы JIT-компилятора для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="4bdd0-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bdd0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bdd0-111">Remarks</span></span>  
 <span data-ttu-id="4bdd0-112">`GetReJITIDs` перечисляет идентификаторы active JIT-компилятора для экземпляра указанной функции.</span><span class="sxs-lookup"><span data-stu-id="4bdd0-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="4bdd0-113">Его после использования шаблона, аналогичного других `ICorProfilerInfo` функций, принимающих буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="4bdd0-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bdd0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4bdd0-114">Requirements</span></span>  
 <span data-ttu-id="4bdd0-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bdd0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bdd0-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4bdd0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4bdd0-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bdd0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bdd0-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bdd0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bdd0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4bdd0-119">See Also</span></span>  
 [<span data-ttu-id="4bdd0-120">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="4bdd0-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="4bdd0-121">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="4bdd0-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="4bdd0-122">Профилирование</span><span class="sxs-lookup"><span data-stu-id="4bdd0-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
