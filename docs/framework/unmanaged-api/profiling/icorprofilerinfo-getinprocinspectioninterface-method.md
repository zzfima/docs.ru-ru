---
title: Метод ICorProfilerInfo::GetInprocInspectionInterface
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 456dd8aedf11b1b27ee4926988fc615ebb7a76d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209935"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="269b7-102">Метод ICorProfilerInfo::GetInprocInspectionInterface</span><span class="sxs-lookup"><span data-stu-id="269b7-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="269b7-103">Возвращает объект, который можно запросить для интерфейса «ICorDebugProcess».</span><span class="sxs-lookup"><span data-stu-id="269b7-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="269b7-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="269b7-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269b7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="269b7-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="269b7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="269b7-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="269b7-107">[out](/cpp/atl/iunknown) объект, который можно запросить для `ICorDebugProcess` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="269b7-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="269b7-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="269b7-108">Remarks</span></span>  
 <span data-ttu-id="269b7-109">Общеязыковой среды выполнения (CLR), API отладки поддерживается только в процессе отладки в .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="269b7-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="269b7-110">В процессе отладки включить профилировщик для использования для проверки часть API отладки.</span><span class="sxs-lookup"><span data-stu-id="269b7-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="269b7-111">В результате отзывов в процессе отладки удален из .NET Framework версии 2.0 и заменены набором функциональных возможностей, которые лучше соответствуют API профилирования.</span><span class="sxs-lookup"><span data-stu-id="269b7-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="269b7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="269b7-112">Requirements</span></span>  
 <span data-ttu-id="269b7-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="269b7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="269b7-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="269b7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="269b7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="269b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="269b7-116">**Версии платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="269b7-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269b7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="269b7-117">See also</span></span>

- [<span data-ttu-id="269b7-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="269b7-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
