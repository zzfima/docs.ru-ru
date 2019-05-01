---
title: Интерфейс ICorProfilerFunctionControl
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 721ee27522b316a561e2f64a322c225cb85a44c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992177"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="8503f-102">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="8503f-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="8503f-103">Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.</span><span class="sxs-lookup"><span data-stu-id="8503f-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8503f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8503f-104">Methods</span></span>  
  
|<span data-ttu-id="8503f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8503f-105">Method</span></span>|<span data-ttu-id="8503f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8503f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8503f-107">Метод SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="8503f-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="8503f-108">Задает один или несколько флагов из [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) функция перекомпилировать перечисления с целью управления генерацией кода для just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="8503f-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="8503f-109">Метод SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="8503f-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="8503f-110">Заменяет тело метода на языке CIL.</span><span class="sxs-lookup"><span data-stu-id="8503f-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="8503f-111">Метод SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="8503f-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="8503f-112">Устанавливает карту кода для указанной функции с помощью указанных записей карты языка CIL.</span><span class="sxs-lookup"><span data-stu-id="8503f-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8503f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8503f-113">Remarks</span></span>  
 <span data-ttu-id="8503f-114">Интерфейс `ICorProfilerFunctionControl` предоставляет методы для генерации управляющего кода для одной перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="8503f-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="8503f-115">Профилировщик получает экземпляр этого интерфейса через [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="8503f-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="8503f-116">Каждый экземпляр `ICorProfilerFunctionControl` управляет всеми экземплярами одной функции.</span><span class="sxs-lookup"><span data-stu-id="8503f-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8503f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="8503f-117">Requirements</span></span>  
 <span data-ttu-id="8503f-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8503f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8503f-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8503f-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8503f-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8503f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8503f-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8503f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8503f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8503f-122">See also</span></span>

- [<span data-ttu-id="8503f-123">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="8503f-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="8503f-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="8503f-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="8503f-125">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="8503f-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
