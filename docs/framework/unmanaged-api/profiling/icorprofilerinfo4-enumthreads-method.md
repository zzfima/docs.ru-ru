---
title: Метод ICorProfilerInfo4::EnumThreads
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd0a4149b6dc6023579e8bc5b40751d23416e3a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202369"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="74651-102">Метод ICorProfilerInfo4::EnumThreads</span><span class="sxs-lookup"><span data-stu-id="74651-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="74651-103">Возвращает перечислитель, который предоставляет методы для последовательного перебора коллекции все управляемые потоки в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="74651-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74651-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74651-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74651-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74651-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="74651-106">[out] Указатель на [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="74651-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74651-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="74651-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74651-108">Требования</span><span class="sxs-lookup"><span data-stu-id="74651-108">Requirements</span></span>  
 <span data-ttu-id="74651-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74651-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74651-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74651-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74651-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74651-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="74651-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="74651-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74651-113">См. также</span><span class="sxs-lookup"><span data-stu-id="74651-113">See also</span></span>

- [<span data-ttu-id="74651-114">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="74651-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="74651-115">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="74651-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="74651-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="74651-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="74651-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="74651-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
