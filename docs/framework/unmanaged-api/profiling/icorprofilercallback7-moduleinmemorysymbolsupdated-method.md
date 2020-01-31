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
ms.openlocfilehash: 6fbb86fc63a26599ae83c81817dbcb9abfb88cc8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864693"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="42f26-102">Метод ICorProfilerCallback7:: Модулеинмеморисимболсупдатед</span><span class="sxs-lookup"><span data-stu-id="42f26-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="42f26-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="42f26-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="42f26-104">Уведомляет профилировщик каждый раз, когда поток символов, связанный с модулем в памяти, обновляется.</span><span class="sxs-lookup"><span data-stu-id="42f26-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f26-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42f26-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42f26-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="42f26-106">Parameters</span></span>  
 <span data-ttu-id="42f26-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="42f26-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="42f26-108">Идентификатор модуля в памяти, чей поток символов обновлен.</span><span class="sxs-lookup"><span data-stu-id="42f26-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42f26-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="42f26-109">Remarks</span></span>  
 <span data-ttu-id="42f26-110">Этот обратный вызов управляется путем установки флага [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) маски событий при вызове метода [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="42f26-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42f26-111">Это событие в данный момент не вызывается для символов, которые неявно создаются или изменяются с помощью <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="42f26-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="42f26-112">Даже если символы предоставляются перед вызовом одной из перегрузок управляемых методов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, которые включают `rawSymbolStore` аргумент для указания символов для сборки, среда выполнения может не связать символьные данные с модулем до тех пор, пока не будет вызван обратный вызов [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="42f26-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="42f26-113">Это событие предоставляет более позднюю возможность собираются символы для таких модулей.</span><span class="sxs-lookup"><span data-stu-id="42f26-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42f26-114">Требования</span><span class="sxs-lookup"><span data-stu-id="42f26-114">Requirements</span></span>  
 <span data-ttu-id="42f26-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42f26-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42f26-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42f26-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42f26-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42f26-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42f26-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42f26-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f26-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="42f26-119">See also</span></span>

- [<span data-ttu-id="42f26-120">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="42f26-120">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="42f26-121">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="42f26-121">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="42f26-122">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="42f26-122">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)
