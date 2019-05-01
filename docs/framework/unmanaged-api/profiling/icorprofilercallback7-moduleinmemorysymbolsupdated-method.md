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
ms.openlocfilehash: 12414064bf0651eab443951bde2a50dcff7b2291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992099"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="3229e-102">Метод ICorProfilerCallback7::ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="3229e-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="3229e-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="3229e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="3229e-104">Уведомляет профилировщик, каждый раз, когда обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="3229e-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3229e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3229e-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3229e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3229e-106">Parameters</span></span>  
 <span data-ttu-id="3229e-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="3229e-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="3229e-108">Идентификатор модуля в памяти, обновляется, поток символов.</span><span class="sxs-lookup"><span data-stu-id="3229e-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3229e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3229e-109">Remarks</span></span>  
 <span data-ttu-id="3229e-110">Этот обратный вызов управляется заданием [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) флага маски события при вызове [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3229e-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3229e-111">Это событие не вызывается в настоящее время для символов неявно создан или изменен с помощью <xref:System.Reflection.Emit> API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="3229e-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="3229e-112">Даже если символы предоставляются поставлены во главу угла при вызове одной из перегрузок управляемых <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> методы, которые включает в себя `rawSymbolStore` аргумент указывать символы для сборки, среда выполнения может не связать фактически символьные данные с помощью модуля пока после [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) произошла обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="3229e-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="3229e-113">Это событие предоставляет более поздней версии возможность сбора символы для таких модулей.</span><span class="sxs-lookup"><span data-stu-id="3229e-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3229e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3229e-114">Requirements</span></span>  
 <span data-ttu-id="3229e-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3229e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3229e-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3229e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3229e-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3229e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3229e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3229e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3229e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3229e-119">See also</span></span>

- [<span data-ttu-id="3229e-120">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="3229e-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="3229e-121">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="3229e-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="3229e-122">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="3229e-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
