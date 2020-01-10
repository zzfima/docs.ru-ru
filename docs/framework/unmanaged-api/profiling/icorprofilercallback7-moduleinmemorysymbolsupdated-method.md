---
title: 'Метод ICorProfilerCallback7:: Модулеинмеморисимболсупдатед'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: b9e404de96fa42509144904f5b2ff58e341578a9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740440"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="bf012-102">Метод ICorProfilerCallback7:: Модулеинмеморисимболсупдатед</span><span class="sxs-lookup"><span data-stu-id="bf012-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="bf012-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="bf012-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="bf012-104">Уведомляет профилировщик каждый раз, когда поток символов, связанный с модулем в памяти, обновляется.</span><span class="sxs-lookup"><span data-stu-id="bf012-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf012-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf012-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf012-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf012-106">Parameters</span></span>  
 <span data-ttu-id="bf012-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="bf012-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="bf012-108">Идентификатор модуля в памяти, чей поток символов обновлен.</span><span class="sxs-lookup"><span data-stu-id="bf012-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf012-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="bf012-109">Remarks</span></span>  
 <span data-ttu-id="bf012-110">Этот обратный вызов управляется путем установки флага [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) маски событий при вызове метода [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bf012-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf012-111">Это событие в данный момент не вызывается для символов, которые неявно создаются или изменяются с помощью <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="bf012-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="bf012-112">Даже если символы предоставляются перед вызовом одной из перегрузок управляемых методов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, которые включают `rawSymbolStore` аргумент для указания символов для сборки, среда выполнения может не связать символьные данные с модулем до тех пор, пока не будет вызван обратный вызов [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bf012-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="bf012-113">Это событие предоставляет более позднюю возможность собираются символы для таких модулей.</span><span class="sxs-lookup"><span data-stu-id="bf012-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf012-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bf012-114">Requirements</span></span>  
 <span data-ttu-id="bf012-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf012-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf012-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf012-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf012-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf012-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf012-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf012-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf012-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf012-119">See also</span></span>

- [<span data-ttu-id="bf012-120">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="bf012-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="bf012-121">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="bf012-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="bf012-122">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="bf012-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
