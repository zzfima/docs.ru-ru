---
title: Метод ICorProfilerInfo5::SetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266219894ffefa0d4066c6ca68c7cadf6265e098
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175816"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="f0b90-102">Метод ICorProfilerInfo5::SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="f0b90-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="f0b90-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="f0b90-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f0b90-104">Определяет значение, указывающее типы событий, для которых профилировщик хочет получать уведомления о событиях от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f0b90-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="f0b90-105">Он предоставляет больше возможностей, чем [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f0b90-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b90-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0b90-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0b90-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0b90-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="f0b90-108">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="f0b90-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="f0b90-109">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="f0b90-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="f0b90-110">Биты описаны в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="f0b90-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="f0b90-111">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="f0b90-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="f0b90-112">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="f0b90-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="f0b90-113">Биты описаны в [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="f0b90-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0b90-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0b90-114">Remarks</span></span>  
 <span data-ttu-id="f0b90-115">Метод `SetEventMask2` используется для установки обратных вызовов, на которые подписывается профилировщик.</span><span class="sxs-lookup"><span data-stu-id="f0b90-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="f0b90-116">Как правило, вызывается [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) метод, чтобы определить, какие биты установлены, выполнять логическое или для его `pdwEventsLow` и `pdwEventsHigh` значения и новых битов, вы хотите, а затем вызовите `SetEventMask2` метод.</span><span class="sxs-lookup"><span data-stu-id="f0b90-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="f0b90-117">Этот метод является рекомендуемой альтернативой для [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f0b90-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b90-118">Требования</span><span class="sxs-lookup"><span data-stu-id="f0b90-118">Requirements</span></span>  
 <span data-ttu-id="f0b90-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0b90-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b90-120">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0b90-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0b90-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0b90-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f0b90-122">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f0b90-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0b90-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f0b90-123">See also</span></span>

- [<span data-ttu-id="f0b90-124">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="f0b90-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="f0b90-125">Метод GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="f0b90-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
