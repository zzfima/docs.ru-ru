---
title: Метод ICorProfilerInfo5::GetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8ebddf9a16b2eddbbc58342f68b517064e8d794
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214641"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="325a1-102">Метод ICorProfilerInfo5::GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="325a1-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="325a1-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="325a1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="325a1-104">Получает текущие категории событий, о которых профилировщик хочет получать уведомления из среды CLR.</span><span class="sxs-lookup"><span data-stu-id="325a1-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="325a1-105">Она обеспечивает функциональные возможности, не предоставляемые [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="325a1-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325a1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="325a1-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="325a1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="325a1-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="325a1-108">[из] Указатель на 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="325a1-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="325a1-109">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="325a1-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="325a1-110">Биты описаны в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="325a1-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="325a1-111">[из] Указатель на 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="325a1-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="325a1-112">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="325a1-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="325a1-113">Биты описаны в [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="325a1-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="325a1-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="325a1-114">Remarks</span></span>  
 <span data-ttu-id="325a1-115">Метод `GetEventMask2` используется для определения обратных вызовов, на которые подписался профилировщик.</span><span class="sxs-lookup"><span data-stu-id="325a1-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="325a1-116">Как правило, выполняется логический оператор или из `pdwEventsLow` и `pdwEventsHigh` значения и новых битов, вы хотите, а затем вызовите [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="325a1-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="325a1-117">Этот метод является рекомендуемой альтернативой для [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="325a1-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="325a1-118">Требования</span><span class="sxs-lookup"><span data-stu-id="325a1-118">Requirements</span></span>  
 <span data-ttu-id="325a1-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="325a1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="325a1-120">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="325a1-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="325a1-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="325a1-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="325a1-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="325a1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325a1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="325a1-123">See also</span></span>

- [<span data-ttu-id="325a1-124">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="325a1-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="325a1-125">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="325a1-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
