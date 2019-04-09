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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f152279a21f28b54acebbf0be7c65bb73efa70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150596"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="77acc-102">Метод ICorProfilerCallback4::ReJITError</span><span class="sxs-lookup"><span data-stu-id="77acc-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="77acc-103">Уведомляет профилировщик о том, что компилятор just-in-time (JIT) произошла ошибка в процессе повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="77acc-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77acc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77acc-104">Syntax</span></span>  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77acc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77acc-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="77acc-106">[in] `ModuleID` В которой была сделана попытка сбой повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="77acc-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="77acc-107">[in] `MethodDef` Метода, на котором была сделана попытка сбой повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="77acc-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="77acc-108">[in] Экземпляр функции, для которого выполняется повторная сборка или помечены для повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="77acc-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="77acc-109">Это значение может быть `NULL` Если произошел на каждого метода вместо конкретных экземпляров (например, если профилировщик указан маркер недопустимые метаданные для метода повторной компиляции).</span><span class="sxs-lookup"><span data-stu-id="77acc-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="77acc-110">[in] Значение HRESULT, указывающее характер ошибки.</span><span class="sxs-lookup"><span data-stu-id="77acc-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="77acc-111">См. в разделе значения HRESULT для состояния списка значений.</span><span class="sxs-lookup"><span data-stu-id="77acc-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77acc-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="77acc-112">Return Value</span></span>  
 <span data-ttu-id="77acc-113">Значения, возвращаемые из этого обратного вызова, игнорируются.</span><span class="sxs-lookup"><span data-stu-id="77acc-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="77acc-114">Значения HRESULT для состояния</span><span class="sxs-lookup"><span data-stu-id="77acc-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="77acc-115">Массив значений HRESULT для состояния</span><span class="sxs-lookup"><span data-stu-id="77acc-115">Status array HRESULT</span></span>|<span data-ttu-id="77acc-116">Описание</span><span class="sxs-lookup"><span data-stu-id="77acc-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="77acc-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="77acc-117">E_INVALIDARG</span></span>|<span data-ttu-id="77acc-118">`moduleID` Или `methodDef` маркер является `NULL`.</span><span class="sxs-lookup"><span data-stu-id="77acc-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="77acc-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="77acc-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="77acc-120">Модуль еще не полностью загружен или находится в процессе выгрузки.</span><span class="sxs-lookup"><span data-stu-id="77acc-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="77acc-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="77acc-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="77acc-122">Указанный модуль был создан динамически (например, с `Reflection.Emit`) и поэтому не поддерживается этим методом.</span><span class="sxs-lookup"><span data-stu-id="77acc-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="77acc-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="77acc-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="77acc-124">Метод создается в забираемой сборке и поэтому не может быть перекомпилирован.</span><span class="sxs-lookup"><span data-stu-id="77acc-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="77acc-125">Обратите внимание, что типы и функции, определенные в контексте, отличных от отражения (например, `List<MyCollectibleStruct>`) могут быть созданы в забираемой сборке.</span><span class="sxs-lookup"><span data-stu-id="77acc-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="77acc-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="77acc-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="77acc-127">Среда CLR не хватило памяти при попытке пометить указанный метод для перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="77acc-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="77acc-128">Другое</span><span class="sxs-lookup"><span data-stu-id="77acc-128">Other</span></span>|<span data-ttu-id="77acc-129">Операционная система возвратила сбой за пределами среды CLR.</span><span class="sxs-lookup"><span data-stu-id="77acc-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="77acc-130">Например если происходит сбой системного вызова изменения защиты доступа к странице памяти, отображается ошибка операционной системы.</span><span class="sxs-lookup"><span data-stu-id="77acc-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77acc-131">Требования</span><span class="sxs-lookup"><span data-stu-id="77acc-131">Requirements</span></span>  
 <span data-ttu-id="77acc-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77acc-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77acc-133">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="77acc-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="77acc-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77acc-134">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="77acc-135">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="77acc-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77acc-136">См. также</span><span class="sxs-lookup"><span data-stu-id="77acc-136">See also</span></span>

- [<span data-ttu-id="77acc-137">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="77acc-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="77acc-138">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="77acc-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
