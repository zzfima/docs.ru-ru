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
ms.openlocfilehash: 0cb54a714b9da72e8620b39690b4dcc9a3c21c2e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496863"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="df888-102">Метод ICorProfilerCallback8::DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="df888-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="df888-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="df888-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="df888-104">Уведомляет профилировщик, каждый раз, когда JIT-компиляция динамического метода завершения.</span><span class="sxs-lookup"><span data-stu-id="df888-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df888-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df888-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df888-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="df888-106">Parameters</span></span>  
<span data-ttu-id="df888-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="df888-107">[in] `functionId`</span></span>  
<span data-ttu-id="df888-108">Идентификатор функции в памяти, для которого JIT-компиляции запускается.</span><span class="sxs-lookup"><span data-stu-id="df888-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="df888-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="df888-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="df888-110">Значение, указывающее, успешно ли JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="df888-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="df888-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="df888-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="df888-112">`true` Чтобы указать, что блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="df888-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="df888-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="df888-113">Remarks</span></span>  

<span data-ttu-id="df888-114">Этот обратный вызов активируется каждый раз, когда JIT-компиляция динамического метода завершения.</span><span class="sxs-lookup"><span data-stu-id="df888-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="df888-115">Сюда входят различные заглушки IL и LCG методы.</span><span class="sxs-lookup"><span data-stu-id="df888-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="df888-116">Его целью является предоставление модулей записи профилировщика достаточно информации для идентификации метода, скомпилированного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="df888-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="df888-117">`functionId` значения не может использоваться для разрешения на их токены метаданных, так как динамические методы имеют без метаданных.</span><span class="sxs-lookup"><span data-stu-id="df888-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="df888-118">Требования</span><span class="sxs-lookup"><span data-stu-id="df888-118">Requirements</span></span>  
 <span data-ttu-id="df888-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df888-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df888-120">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="df888-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df888-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df888-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df888-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="df888-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df888-123">См. также</span><span class="sxs-lookup"><span data-stu-id="df888-123">See also</span></span>
- [<span data-ttu-id="df888-124">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="df888-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="df888-125">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="df888-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
