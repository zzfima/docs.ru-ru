---
title: "Метод ICorProfilerCallback7::ModuleInMemorySymbolsUpdated"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 898adf043e425c00d6e311e2f67c53ed65cacb33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="89fe2-102">Метод ICorProfilerCallback7::ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="89fe2-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="89fe2-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="89fe2-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="89fe2-104">Уведомляет профилировщик при каждом обновлении потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="89fe2-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89fe2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89fe2-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89fe2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="89fe2-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="89fe2-107">Идентификатор модуля в памяти, обновление которого поток символов.</span><span class="sxs-lookup"><span data-stu-id="89fe2-107">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89fe2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="89fe2-108">Remarks</span></span>  
 <span data-ttu-id="89fe2-109">Этот обратный вызов можно изменять, задавая [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) флага маски события при вызове [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="89fe2-109">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89fe2-110">Это событие не происходит в данный момент для символов, неявно созданного или измененного через <xref:System.Reflection.Emit> API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="89fe2-110">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="89fe2-111">Даже если символы предоставляются заранее при обращении к одной из перегрузок управляемых <xref:System.Reflection.Assembly.Load\*?displayProperty=nameWithType> методов, включая `rawSymbolStore` аргумент, чтобы указать символы для сборки, среда выполнения может не связать фактически символьных данных в модуле пока после [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) произошла обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="89fe2-111">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load\*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="89fe2-112">Это событие предоставляет более поздней версии возможность сбора символы для таких модулей.</span><span class="sxs-lookup"><span data-stu-id="89fe2-112">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89fe2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="89fe2-113">Requirements</span></span>  
 <span data-ttu-id="89fe2-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89fe2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89fe2-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89fe2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89fe2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89fe2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89fe2-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89fe2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89fe2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="89fe2-118">See Also</span></span>  
 [<span data-ttu-id="89fe2-119">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="89fe2-119">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="89fe2-120">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="89fe2-120">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="89fe2-121">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="89fe2-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
