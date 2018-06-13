---
title: Метод ICorProfilerCallback8::DynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454754"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="46d01-102">Метод ICorProfilerCallback8::DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="46d01-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="46d01-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="46d01-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="46d01-104">Уведомляет профилировщик, каждый раз, когда запущен JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="46d01-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d01-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46d01-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46d01-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="46d01-106">Parameters</span></span>  
<span data-ttu-id="46d01-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="46d01-107">[in] `functionId`</span></span>  
<span data-ttu-id="46d01-108">Идентификатор функции в памяти, для которого JIT-компилятора началом компиляции.</span><span class="sxs-lookup"><span data-stu-id="46d01-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="46d01-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="46d01-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="46d01-110">`true` Чтобы указать, что блокировка может послужить причиной среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="46d01-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="46d01-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="46d01-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="46d01-112">Указатель на первый байт заголовок IL-код этого метода.</span><span class="sxs-lookup"><span data-stu-id="46d01-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="46d01-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="46d01-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="46d01-114">Число байтов в заголовке IL.</span><span class="sxs-lookup"><span data-stu-id="46d01-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="46d01-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="46d01-115">Remarks</span></span>  

<span data-ttu-id="46d01-116">Этот обратный вызов будет запускаться при каждом динамический метод является JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="46d01-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="46d01-117">Сюда входят различные заглушки IL и LCG методы.</span><span class="sxs-lookup"><span data-stu-id="46d01-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="46d01-118">Ее целью является предоставление модулей записи профилировщик с достаточно информации для идентификации метода, скомпилированного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="46d01-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="46d01-119">`functionId` значения не может использоваться для разрешения на их лексемы метаданных, поскольку динамические методы имеют без метаданных.</span><span class="sxs-lookup"><span data-stu-id="46d01-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="46d01-120">`pILHeader` Указатель действует только во время обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="46d01-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="46d01-121">Требования</span><span class="sxs-lookup"><span data-stu-id="46d01-121">Requirements</span></span>  
 <span data-ttu-id="46d01-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46d01-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d01-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46d01-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46d01-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46d01-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46d01-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46d01-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d01-126">См. также</span><span class="sxs-lookup"><span data-stu-id="46d01-126">See Also</span></span>  
 [<span data-ttu-id="46d01-127">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="46d01-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [<span data-ttu-id="46d01-128">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="46d01-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
