---
title: Метод ICorProfilerCallback7::ModuleInMemorySymbolsUpdated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9aa690378a32ffee2def672f02dc8b5582647a5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455818"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="5a2b1-102">Метод ICorProfilerCallback7::ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="5a2b1-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="5a2b1-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="5a2b1-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="5a2b1-104">Уведомляет профилировщик при каждом обновлении потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="5a2b1-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a2b1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a2b1-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a2b1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a2b1-106">Parameters</span></span>  
 <span data-ttu-id="5a2b1-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="5a2b1-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="5a2b1-108">Идентификатор модуля в памяти, обновление которого поток символов.</span><span class="sxs-lookup"><span data-stu-id="5a2b1-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a2b1-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a2b1-109">Remarks</span></span>  
 <span data-ttu-id="5a2b1-110">Этот обратный вызов можно изменять, задавая [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) флага маски события при вызове [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="5a2b1-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a2b1-111">Это событие не происходит в данный момент для символов, неявно созданного или измененного через <xref:System.Reflection.Emit> API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="5a2b1-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="5a2b1-112">Даже если символы предоставляются заранее при обращении к одной из перегрузок управляемых <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> методов, включая `rawSymbolStore` аргумент, чтобы указать символы для сборки, среда выполнения может не связать фактически символьных данных в модуле пока после [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) произошла обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5a2b1-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="5a2b1-113">Это событие предоставляет более поздней версии возможность сбора символы для таких модулей.</span><span class="sxs-lookup"><span data-stu-id="5a2b1-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a2b1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5a2b1-114">Requirements</span></span>  
 <span data-ttu-id="5a2b1-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a2b1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a2b1-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a2b1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a2b1-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a2b1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a2b1-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a2b1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2b1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5a2b1-119">See Also</span></span>  
 [<span data-ttu-id="5a2b1-120">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="5a2b1-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="5a2b1-121">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="5a2b1-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="5a2b1-122">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="5a2b1-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
