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
ms.openlocfilehash: c4b8bffeb71497a7dd8e2ed25b833f9216d8017e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142250"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="6f1cc-102">Метод ICorProfilerCallback8::DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="6f1cc-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="6f1cc-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="6f1cc-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="6f1cc-104">Уведомляет профилировщик, каждый раз, когда JIT-компиляция динамического метода запуска.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f1cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f1cc-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f1cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f1cc-106">Parameters</span></span>  
<span data-ttu-id="6f1cc-107">[in]</span><span class="sxs-lookup"><span data-stu-id="6f1cc-107">[in]</span></span> `functionId`  
<span data-ttu-id="6f1cc-108">Идентификатор функции в памяти, для которого JIT-компиляции запускается.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="6f1cc-109">[in]</span><span class="sxs-lookup"><span data-stu-id="6f1cc-109">[in]</span></span> `fIsSafeToBlock`   
`true` <span data-ttu-id="6f1cc-110">Чтобы указать, что блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-110">to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="6f1cc-111">[in]</span><span class="sxs-lookup"><span data-stu-id="6f1cc-111">[in]</span></span> `pILHeader`    
<span data-ttu-id="6f1cc-112">Указатель на первый байт метод IL заголовка.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="6f1cc-113">[in]</span><span class="sxs-lookup"><span data-stu-id="6f1cc-113">[in]</span></span> `cbILHeader`    
<span data-ttu-id="6f1cc-114">Число байтов в заголовке IL.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="6f1cc-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f1cc-115">Remarks</span></span>  

<span data-ttu-id="6f1cc-116">Этот обратный вызов активируется каждый раз, когда динамический метод является JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="6f1cc-117">Сюда входят различные заглушки IL и LCG методы.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="6f1cc-118">Его целью является предоставление модулей записи профилировщика достаточно информации для идентификации метода, скомпилированного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> `functionId` <span data-ttu-id="6f1cc-119">значения не может использоваться для разрешения на их токены метаданных, так как динамические методы имеют без метаданных.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-119">values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="6f1cc-120">`pILHeader` Указатель допустим только во время обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="6f1cc-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="6f1cc-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6f1cc-121">Requirements</span></span>  
 <span data-ttu-id="6f1cc-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f1cc-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f1cc-123">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f1cc-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f1cc-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f1cc-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6f1cc-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6f1cc-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f1cc-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6f1cc-126">See also</span></span>

- [<span data-ttu-id="6f1cc-127">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="6f1cc-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="6f1cc-128">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="6f1cc-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
