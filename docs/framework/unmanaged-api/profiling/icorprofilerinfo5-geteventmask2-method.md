---
title: "Метод ICorProfilerInfo5::GetEventMask2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorProfilerInfo5.GetEventMask2
api_location: mscorwks.dll
api_type: COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da1c4c11adaac21e9769330ee24beceff64e020b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="8266a-102">Метод ICorProfilerInfo5::GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="8266a-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="8266a-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="8266a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="8266a-104">Получает текущие категории событий, о которых профилировщик хочет получать уведомления из среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8266a-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="8266a-105">Он предоставляет функциональные возможности, не предоставляемые [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8266a-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8266a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8266a-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8266a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="8266a-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="8266a-108">[из] Указатель на 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="8266a-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="8266a-109">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="8266a-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="8266a-110">Биты описаны в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="8266a-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="8266a-111">[из] Указатель на 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="8266a-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="8266a-112">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="8266a-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="8266a-113">Биты описаны в [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="8266a-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8266a-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="8266a-114">Remarks</span></span>  
 <span data-ttu-id="8266a-115">Метод `GetEventMask2` используется для определения обратных вызовов, на которые подписался профилировщик.</span><span class="sxs-lookup"><span data-stu-id="8266a-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="8266a-116">Обычно для выполнения логического OR `pdwEventsLow` и `pdwEventsHigh` значения и новых битов, нужно установить, а затем вызвать [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8266a-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="8266a-117">Этот метод — это рекомендуемая альтернатива для [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8266a-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8266a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8266a-118">Requirements</span></span>  
 <span data-ttu-id="8266a-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8266a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8266a-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8266a-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8266a-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8266a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8266a-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8266a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8266a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8266a-123">See Also</span></span>  
 [<span data-ttu-id="8266a-124">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="8266a-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [<span data-ttu-id="8266a-125">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="8266a-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
