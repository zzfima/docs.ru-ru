---
title: "Метод ICorProfilerInfo::SetEventMask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetEventMask
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bb42be7f8e5722ec9924284c257e814a186564d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="a9d3f-102">Метод ICorProfilerInfo::SetEventMask</span><span class="sxs-lookup"><span data-stu-id="a9d3f-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="a9d3f-103">Определяет значение, указывающее типы событий, для которых профилировщик хочет получать уведомления от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9d3f-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9d3f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9d3f-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="a9d3f-106">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="a9d3f-107">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="a9d3f-108">Биты описаны в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9d3f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9d3f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9d3f-110">Необходимо вызвать [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) вместо этого метода.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="a9d3f-111">Несмотря на то что `SetEventMask` метод по-прежнему поддерживается, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) предоставляет дополнительные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="a9d3f-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d3f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a9d3f-112">Requirements</span></span>  
 <span data-ttu-id="a9d3f-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9d3f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9d3f-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9d3f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9d3f-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9d3f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9d3f-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9d3f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d3f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a9d3f-117">See Also</span></span>  
 [<span data-ttu-id="a9d3f-118">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a9d3f-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="a9d3f-119">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="a9d3f-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
