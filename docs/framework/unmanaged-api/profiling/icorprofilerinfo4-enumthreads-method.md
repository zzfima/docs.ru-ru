---
title: "Метод ICorProfilerInfo4::EnumThreads"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.EnumThreads
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 20022a3b7353c0e43aaa44e368c06cd79906956e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="63669-102">Метод ICorProfilerInfo4::EnumThreads</span><span class="sxs-lookup"><span data-stu-id="63669-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="63669-103">Возвращает перечислитель, который предоставляет методы для последовательного перебора коллекции все управляемые потоки в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="63669-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63669-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63669-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63669-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="63669-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="63669-106">[out] Указатель на [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="63669-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63669-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="63669-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63669-108">Требования</span><span class="sxs-lookup"><span data-stu-id="63669-108">Requirements</span></span>  
 <span data-ttu-id="63669-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63669-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63669-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63669-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63669-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63669-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63669-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63669-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63669-113">См. также</span><span class="sxs-lookup"><span data-stu-id="63669-113">See Also</span></span>  
 [<span data-ttu-id="63669-114">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="63669-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="63669-115">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="63669-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="63669-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="63669-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="63669-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="63669-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
