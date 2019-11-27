---
title: Метод ICorProfilerCallback4::ReJITError
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 6ea9dee6e83870d1f2e0fdccffa53f16e6f18dba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430105"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="455ec-102">Метод ICorProfilerCallback4::ReJITError</span><span class="sxs-lookup"><span data-stu-id="455ec-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="455ec-103">Уведомляет профилировщик о том, что компилятор JIT обнаружил ошибку в процессе перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="455ec-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="455ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="455ec-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="455ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="455ec-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="455ec-106">окне `ModuleID`, в котором была выполнена попытка повторной компиляции с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="455ec-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="455ec-107">окне `MethodDef` метода, для которого была выполнена попытка повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="455ec-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="455ec-108">окне Экземпляр функции, который перекомпилируется или помечен для повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="455ec-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="455ec-109">Это значение может быть `NULL`, если ошибка возникла для каждого метода, а не для отдельных экземпляров (например, если профилировщик указал недопустимый токен метаданных для повторной компиляции метода).</span><span class="sxs-lookup"><span data-stu-id="455ec-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="455ec-110">окне Значение HRESULT, указывающее природу сбоя.</span><span class="sxs-lookup"><span data-stu-id="455ec-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="455ec-111">Список значений см. в разделе Status HRESULTs.</span><span class="sxs-lookup"><span data-stu-id="455ec-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="455ec-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="455ec-112">Return Value</span></span>  
 <span data-ttu-id="455ec-113">Значения, возвращаемые из этого обратного вызова, игнорируются.</span><span class="sxs-lookup"><span data-stu-id="455ec-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="455ec-114">Значения HRESULT для состояния</span><span class="sxs-lookup"><span data-stu-id="455ec-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="455ec-115">Массив значений HRESULT для состояния</span><span class="sxs-lookup"><span data-stu-id="455ec-115">Status array HRESULT</span></span>|<span data-ttu-id="455ec-116">Описание</span><span class="sxs-lookup"><span data-stu-id="455ec-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="455ec-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="455ec-117">E_INVALIDARG</span></span>|<span data-ttu-id="455ec-118">Маркер `moduleID` или `methodDef` `NULL`.</span><span class="sxs-lookup"><span data-stu-id="455ec-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="455ec-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="455ec-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="455ec-120">Модуль еще не полностью загружен или находится в процессе выгрузки.</span><span class="sxs-lookup"><span data-stu-id="455ec-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="455ec-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="455ec-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="455ec-122">Указанный модуль был динамически создан (например, с `Reflection.Emit`) и поэтому не поддерживается этим методом.</span><span class="sxs-lookup"><span data-stu-id="455ec-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="455ec-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="455ec-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="455ec-124">Экземпляр метода создается в собираемой сборке и поэтому не может быть перекомпилирован.</span><span class="sxs-lookup"><span data-stu-id="455ec-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="455ec-125">Обратите внимание, что типы и функции, определенные в контексте без отражения (например, `List<MyCollectibleStruct>`), можно создать в собираемой сборке.</span><span class="sxs-lookup"><span data-stu-id="455ec-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="455ec-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="455ec-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="455ec-127">В среде CLR возникла нехватка памяти при попытке пометить указанный метод для повторной компиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="455ec-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="455ec-128">Прочее</span><span class="sxs-lookup"><span data-stu-id="455ec-128">Other</span></span>|<span data-ttu-id="455ec-129">Операционная система возвратила сбой за пределами среды CLR.</span><span class="sxs-lookup"><span data-stu-id="455ec-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="455ec-130">Например, если системный вызов для изменения защиты доступа к странице памяти завершается ошибкой, отображается сообщение об ошибке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="455ec-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="455ec-131">Требования</span><span class="sxs-lookup"><span data-stu-id="455ec-131">Requirements</span></span>  
 <span data-ttu-id="455ec-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="455ec-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="455ec-133">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="455ec-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="455ec-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="455ec-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="455ec-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="455ec-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455ec-136">См. также</span><span class="sxs-lookup"><span data-stu-id="455ec-136">See also</span></span>

- [<span data-ttu-id="455ec-137">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="455ec-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="455ec-138">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="455ec-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
