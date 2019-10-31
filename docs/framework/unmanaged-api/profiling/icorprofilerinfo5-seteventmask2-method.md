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
ms.openlocfilehash: 1e1779c0f4f36b2d7b81832bc90cf5aee0b8a7df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130399"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="2e2f3-102">Метод ICorProfilerInfo5::SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="2e2f3-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="2e2f3-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="2e2f3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2e2f3-104">Определяет значение, указывающее типы событий, для которых профилировщик хочет получать уведомления о событиях от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="2e2f3-105">Он предоставляет больше функций, чем метод [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2e2f3-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e2f3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e2f3-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e2f3-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e2f3-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="2e2f3-108">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="2e2f3-109">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="2e2f3-110">Биты описаны в перечислении [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2e2f3-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="2e2f3-111">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="2e2f3-112">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="2e2f3-113">Биты описаны в перечислении [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2e2f3-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e2f3-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="2e2f3-114">Remarks</span></span>  
 <span data-ttu-id="2e2f3-115">Метод `SetEventMask2` используется для установки обратных вызовов, на которые подписывается профилировщик.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="2e2f3-116">Как правило, вызывается метод [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) , чтобы определить, какие биты заданы, ВЫПОЛНЯЮТ логическое или `pdwEventsLow` и `pdwEventsHigh` значения и любые новые биты, которые необходимо задать, а затем вызовите метод `SetEventMask2`.</span><span class="sxs-lookup"><span data-stu-id="2e2f3-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="2e2f3-117">Этот метод является рекомендуемым альтернативой методу [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2e2f3-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e2f3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="2e2f3-118">Requirements</span></span>  
 <span data-ttu-id="2e2f3-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e2f3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e2f3-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e2f3-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e2f3-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e2f3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e2f3-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e2f3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e2f3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2e2f3-123">See also</span></span>

- [<span data-ttu-id="2e2f3-124">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="2e2f3-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="2e2f3-125">Метод GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="2e2f3-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
