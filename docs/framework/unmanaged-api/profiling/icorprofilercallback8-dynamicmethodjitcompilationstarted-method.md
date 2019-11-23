---
title: 'ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионстартед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136466"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="7577e-102">ICorProfilerCallback8: метод:D Инамикмесоджиткомпилатионстартед</span><span class="sxs-lookup"><span data-stu-id="7577e-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="7577e-103">[Поддерживается в .NET Framework 4,7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="7577e-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="7577e-104">Уведомляет профилировщик каждый раз, когда запускается JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="7577e-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7577e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7577e-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7577e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7577e-106">Parameters</span></span>  
<span data-ttu-id="7577e-107">[входной] `functionId`</span><span class="sxs-lookup"><span data-stu-id="7577e-107">[in] `functionId`</span></span>  
<span data-ttu-id="7577e-108">Идентификатор функции в памяти, для которой запускается JIT-компиляция.</span><span class="sxs-lookup"><span data-stu-id="7577e-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="7577e-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="7577e-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="7577e-110">`true`, чтобы указать, что блокировка может привести к ожиданию средой выполнения вызывающего потока от этого обратного вызова. `false`, чтобы указать, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7577e-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="7577e-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="7577e-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="7577e-112">Указатель на первый байт заголовка IL метода.</span><span class="sxs-lookup"><span data-stu-id="7577e-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="7577e-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="7577e-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="7577e-114">Число байтов в заголовке IL.</span><span class="sxs-lookup"><span data-stu-id="7577e-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="7577e-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="7577e-115">Remarks</span></span>  

<span data-ttu-id="7577e-116">Этот обратный вызов активируется всякий раз, когда динамический метод компилируется JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="7577e-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="7577e-117">Сюда входят различные суррогаты IL и методы LCG.</span><span class="sxs-lookup"><span data-stu-id="7577e-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="7577e-118">Его цель — предоставить средствам записи профилировщика достаточно информации для распознавания скомпилированного метода для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7577e-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="7577e-119">`functionId` значения нельзя использовать для разрешения их маркеров метаданных, так как динамические методы не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="7577e-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="7577e-120">Указатель `pILHeader` допустим только во время обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="7577e-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="7577e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7577e-121">Requirements</span></span>  
 <span data-ttu-id="7577e-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7577e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7577e-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7577e-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7577e-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7577e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7577e-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7577e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7577e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7577e-126">See also</span></span>

- [<span data-ttu-id="7577e-127">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7577e-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="7577e-128">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="7577e-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
