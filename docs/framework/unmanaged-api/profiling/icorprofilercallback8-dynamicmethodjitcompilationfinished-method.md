---
title: Метод ICorProfilerCallback8::DynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b5ead8b5428d855b7dab81dced1de6325fd07b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="262c2-102">Метод ICorProfilerCallback8::DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="262c2-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="262c2-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="262c2-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="262c2-104">Уведомляет профилировщик, каждый раз, когда JIT-компиляции динамического метода завершения.</span><span class="sxs-lookup"><span data-stu-id="262c2-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="262c2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="262c2-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="262c2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="262c2-106">Parameters</span></span>  
<span data-ttu-id="262c2-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="262c2-107">[in] `functionId`</span></span>  
<span data-ttu-id="262c2-108">Идентификатор функции в памяти, для которого JIT-компилятора началом компиляции.</span><span class="sxs-lookup"><span data-stu-id="262c2-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="262c2-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="262c2-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="262c2-110">Значение, указывающее, успешно ли JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="262c2-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="262c2-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="262c2-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="262c2-112">`true` Чтобы указать, что блокировка может послужить причиной среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="262c2-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="262c2-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="262c2-113">Remarks</span></span>  

<span data-ttu-id="262c2-114">Этот обратный вызов будет запускаться при каждом завершении JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="262c2-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="262c2-115">Сюда входят различные заглушки IL и LCG методы.</span><span class="sxs-lookup"><span data-stu-id="262c2-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="262c2-116">Ее целью является предоставление модулей записи профилировщик с достаточно информации для идентификации метода, скомпилированного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="262c2-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="262c2-117">`functionId` значения не может использоваться для разрешения на их лексемы метаданных, поскольку динамические методы имеют без метаданных.</span><span class="sxs-lookup"><span data-stu-id="262c2-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="262c2-118">Требования</span><span class="sxs-lookup"><span data-stu-id="262c2-118">Requirements</span></span>  
 <span data-ttu-id="262c2-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="262c2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="262c2-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="262c2-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="262c2-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="262c2-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="262c2-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="262c2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262c2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="262c2-123">See Also</span></span>  
 [<span data-ttu-id="262c2-124">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="262c2-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
 [<span data-ttu-id="262c2-125">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="262c2-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
