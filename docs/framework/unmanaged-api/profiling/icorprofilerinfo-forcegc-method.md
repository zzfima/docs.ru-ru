---
title: Метод ICorProfilerInfo::ForceGC
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5672d1b89b4260d1ebfbf444deb2702f215a0e95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078087"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="72cd8-102">Метод ICorProfilerInfo::ForceGC</span><span class="sxs-lookup"><span data-stu-id="72cd8-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="72cd8-103">Принудительно запускает сборку мусора в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="72cd8-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72cd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72cd8-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="72cd8-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="72cd8-105">Remarks</span></span>  
 <span data-ttu-id="72cd8-106">`ForceGC` Метод должен вызываться только из потока, который ни никогда не выполняет управляемый код и не поддерживает обратные вызовы профилировщика в стеке.</span><span class="sxs-lookup"><span data-stu-id="72cd8-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="72cd8-107">Наиболее удобным реализация заключается в создании отдельного потока в профилировщике, который вызывает `ForceGC` при получении сигнала.</span><span class="sxs-lookup"><span data-stu-id="72cd8-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72cd8-108">Требования</span><span class="sxs-lookup"><span data-stu-id="72cd8-108">Requirements</span></span>  
 <span data-ttu-id="72cd8-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72cd8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72cd8-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72cd8-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72cd8-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72cd8-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="72cd8-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="72cd8-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72cd8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="72cd8-113">See also</span></span>

- [<span data-ttu-id="72cd8-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="72cd8-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
