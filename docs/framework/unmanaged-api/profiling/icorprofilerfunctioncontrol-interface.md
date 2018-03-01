---
title: "Интерфейс ICorProfilerFunctionControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 043e97595ba29d0fb5320b8f1bdc4aad4f755067
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="011fe-102">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="011fe-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="011fe-103">Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.</span><span class="sxs-lookup"><span data-stu-id="011fe-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="011fe-104">Методы</span><span class="sxs-lookup"><span data-stu-id="011fe-104">Methods</span></span>  
  
|<span data-ttu-id="011fe-105">Метод</span><span class="sxs-lookup"><span data-stu-id="011fe-105">Method</span></span>|<span data-ttu-id="011fe-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="011fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="011fe-107">Метод SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="011fe-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="011fe-108">Задает один или несколько флагов из [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) перечисления с целью управления генерацией кода для just-in-time (JIT) перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="011fe-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="011fe-109">Метод SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="011fe-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="011fe-110">Заменяет тело метода на языке CIL.</span><span class="sxs-lookup"><span data-stu-id="011fe-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="011fe-111">Метод SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="011fe-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="011fe-112">Устанавливает карту кода для указанной функции с помощью указанных записей карты языка CIL.</span><span class="sxs-lookup"><span data-stu-id="011fe-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="011fe-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="011fe-113">Remarks</span></span>  
 <span data-ttu-id="011fe-114">Интерфейс `ICorProfilerFunctionControl` предоставляет методы для генерации управляющего кода для одной перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="011fe-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="011fe-115">Профилировщик получает экземпляр этого интерфейса через [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="011fe-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="011fe-116">Каждый экземпляр `ICorProfilerFunctionControl` управляет всеми экземплярами одной функции.</span><span class="sxs-lookup"><span data-stu-id="011fe-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="011fe-117">Требования</span><span class="sxs-lookup"><span data-stu-id="011fe-117">Requirements</span></span>  
 <span data-ttu-id="011fe-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="011fe-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="011fe-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="011fe-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="011fe-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="011fe-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="011fe-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="011fe-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011fe-122">См. также</span><span class="sxs-lookup"><span data-stu-id="011fe-122">See Also</span></span>  
 [<span data-ttu-id="011fe-123">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="011fe-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="011fe-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="011fe-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="011fe-125">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="011fe-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
