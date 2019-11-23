---
title: 'ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионфинишед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e04459614ca697908fb9b71ecc3931ac305a838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136584"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="a0e60-102">ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионфинишед</span><span class="sxs-lookup"><span data-stu-id="a0e60-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="a0e60-103">[Поддерживается в .NET Framework 4,7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="a0e60-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="a0e60-104">Уведомляет профилировщик о завершении JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="a0e60-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e60-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0e60-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0e60-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0e60-106">Parameters</span></span>  
<span data-ttu-id="a0e60-107">[входной] `functionId`</span><span class="sxs-lookup"><span data-stu-id="a0e60-107">[in] `functionId`</span></span>  
<span data-ttu-id="a0e60-108">Идентификатор функции в памяти, для которой запускается JIT-компиляция.</span><span class="sxs-lookup"><span data-stu-id="a0e60-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="a0e60-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="a0e60-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="a0e60-110">Значение, указывающее, была ли JIT-компиляция успешной.</span><span class="sxs-lookup"><span data-stu-id="a0e60-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="a0e60-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="a0e60-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="a0e60-112">`true`, чтобы указать, что блокировка может привести к ожиданию средой выполнения вызывающего потока от этого обратного вызова. `false`, чтобы указать, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0e60-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="a0e60-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0e60-113">Remarks</span></span>  

<span data-ttu-id="a0e60-114">Этот обратный вызов активируется каждый раз, когда JIT-компиляция динамического метода завершается.</span><span class="sxs-lookup"><span data-stu-id="a0e60-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="a0e60-115">Сюда входят различные суррогаты IL и методы LCG.</span><span class="sxs-lookup"><span data-stu-id="a0e60-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="a0e60-116">Его цель — предоставить средствам записи профилировщика достаточно информации для распознавания скомпилированного метода для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0e60-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="a0e60-117">`functionId` значения нельзя использовать для разрешения их маркеров метаданных, так как динамические методы не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="a0e60-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0e60-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a0e60-118">Requirements</span></span>  
 <span data-ttu-id="a0e60-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0e60-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0e60-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0e60-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0e60-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0e60-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0e60-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a0e60-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e60-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0e60-123">See also</span></span>

- [<span data-ttu-id="a0e60-124">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="a0e60-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="a0e60-125">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="a0e60-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
