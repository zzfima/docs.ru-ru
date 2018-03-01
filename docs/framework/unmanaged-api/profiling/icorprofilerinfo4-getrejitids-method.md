---
title: "Метод ICorProfilerInfo4::GetReJITIDs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fb1e507bea6f52e4959f241f1507807a76c0ec5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="87076-102">Метод ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="87076-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="87076-103">Возвращает массив идентификаторов, определяющих все JIT-компилятора версии указанной функции, по-прежнему выделяются.</span><span class="sxs-lookup"><span data-stu-id="87076-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="87076-104">Это включает JIT-компилятора версии функций, которые впоследствии восстановить, но еще не освобождены (например, когда домен приложения, содержащей функцию, возвращенного в предыдущее состояние до сих пор используется).</span><span class="sxs-lookup"><span data-stu-id="87076-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87076-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87076-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87076-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="87076-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="87076-107">[in] `FunctionID` Экземпляра функции для перечисления версий.</span><span class="sxs-lookup"><span data-stu-id="87076-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="87076-108">[in] Число идентификаторов JIT-компилятора, выделенных в `reJitIds` массива.</span><span class="sxs-lookup"><span data-stu-id="87076-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="87076-109">[out] Фактическое количество идентификаторов с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="87076-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="87076-110">[out] Выделенный вызывающим объектом массив, который будет содержать идентификаторы JIT-компилятора для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="87076-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87076-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="87076-111">Remarks</span></span>  
 <span data-ttu-id="87076-112">`GetReJITIDs`перечисляет идентификаторы active JIT-компилятора для экземпляра указанной функции.</span><span class="sxs-lookup"><span data-stu-id="87076-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="87076-113">Его после использования шаблона, аналогичного других `ICorProfilerInfo` функций, принимающих буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="87076-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87076-114">Требования</span><span class="sxs-lookup"><span data-stu-id="87076-114">Requirements</span></span>  
 <span data-ttu-id="87076-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87076-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87076-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87076-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87076-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87076-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87076-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87076-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87076-119">См. также</span><span class="sxs-lookup"><span data-stu-id="87076-119">See Also</span></span>  
 [<span data-ttu-id="87076-120">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="87076-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="87076-121">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="87076-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="87076-122">Профилирование</span><span class="sxs-lookup"><span data-stu-id="87076-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
