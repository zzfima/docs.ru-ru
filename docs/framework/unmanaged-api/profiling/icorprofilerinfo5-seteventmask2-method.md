---
title: "Метод ICorProfilerInfo5::SetEventMask2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: IcorProfilerInfo5.SetEventMask2
api_location: mscorwks.dll
api_type: COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2cf383ef8100e096b8373b59231d4aef12725c3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="11f8b-102">Метод ICorProfilerInfo5::SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="11f8b-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="11f8b-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="11f8b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="11f8b-104">Определяет значение, указывающее типы событий, для которых профилировщик хочет получать уведомления о событиях от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="11f8b-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="11f8b-105">Он предоставляет больше возможностей, чем [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="11f8b-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f8b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11f8b-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11f8b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="11f8b-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="11f8b-108">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="11f8b-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="11f8b-109">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="11f8b-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="11f8b-110">Биты описаны в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="11f8b-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="11f8b-111">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="11f8b-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="11f8b-112">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="11f8b-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="11f8b-113">Биты описаны в [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="11f8b-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11f8b-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="11f8b-114">Remarks</span></span>  
 <span data-ttu-id="11f8b-115">Метод `SetEventMask2` используется для установки обратных вызовов, на которые подписывается профилировщик.</span><span class="sxs-lookup"><span data-stu-id="11f8b-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="11f8b-116">Как правило, можно вызвать [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) метод, чтобы определить, какие биты установлены, выполнять логическое или для его `pdwEventsLow` и `pdwEventsHigh` значения и новых битов, нужно установить, а затем вызвать `SetEventMask2` метод.</span><span class="sxs-lookup"><span data-stu-id="11f8b-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="11f8b-117">Этот метод — это рекомендуемая альтернатива для [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="11f8b-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11f8b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="11f8b-118">Requirements</span></span>  
 <span data-ttu-id="11f8b-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11f8b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11f8b-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11f8b-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11f8b-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11f8b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11f8b-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11f8b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f8b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="11f8b-123">See Also</span></span>  
 [<span data-ttu-id="11f8b-124">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="11f8b-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [<span data-ttu-id="11f8b-125">Метод GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="11f8b-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
