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
ms.openlocfilehash: 5a60f074ce0081df07a61d0b832d542c8873776f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757981"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="5e278-102">Метод ICorProfilerCallback8::DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="5e278-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="5e278-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="5e278-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="5e278-104">Уведомляет профилировщик, каждый раз, когда JIT-компиляция динамического метода запуска.</span><span class="sxs-lookup"><span data-stu-id="5e278-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e278-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e278-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e278-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e278-106">Parameters</span></span>  
<span data-ttu-id="5e278-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="5e278-107">[in] `functionId`</span></span>  
<span data-ttu-id="5e278-108">Идентификатор функции в памяти, для которого JIT-компиляции запускается.</span><span class="sxs-lookup"><span data-stu-id="5e278-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="5e278-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="5e278-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="5e278-110">`true` Чтобы указать, что блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5e278-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="5e278-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="5e278-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="5e278-112">Указатель на первый байт метод IL заголовка.</span><span class="sxs-lookup"><span data-stu-id="5e278-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="5e278-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="5e278-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="5e278-114">Число байтов в заголовке IL.</span><span class="sxs-lookup"><span data-stu-id="5e278-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="5e278-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e278-115">Remarks</span></span>  

<span data-ttu-id="5e278-116">Этот обратный вызов активируется каждый раз, когда динамический метод является JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="5e278-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="5e278-117">Сюда входят различные заглушки IL и LCG методы.</span><span class="sxs-lookup"><span data-stu-id="5e278-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="5e278-118">Его целью является предоставление модулей записи профилировщика достаточно информации для идентификации метода, скомпилированного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5e278-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="5e278-119">`functionId` значения не может использоваться для разрешения на их токены метаданных, так как динамические методы имеют без метаданных.</span><span class="sxs-lookup"><span data-stu-id="5e278-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="5e278-120">`pILHeader` Указатель допустим только во время обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5e278-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e278-121">Требования</span><span class="sxs-lookup"><span data-stu-id="5e278-121">Requirements</span></span>  
 <span data-ttu-id="5e278-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e278-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e278-123">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e278-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e278-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e278-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e278-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5e278-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e278-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5e278-126">See also</span></span>

- [<span data-ttu-id="5e278-127">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="5e278-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="5e278-128">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="5e278-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
