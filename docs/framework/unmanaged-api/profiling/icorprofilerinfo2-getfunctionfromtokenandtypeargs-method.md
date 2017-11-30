---
title: "Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bc89ca6213008192c0af8e519ae255c13e9763c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="39192-102">Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="39192-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="39192-103">Возвращает `FunctionID` функции, используя указанный токен метаданных, содержащий класс, и `ClassID` значения любого типа аргументов.</span><span class="sxs-lookup"><span data-stu-id="39192-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39192-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39192-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39192-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="39192-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="39192-106">[in] Идентификатор модуля, в которой находится функция.</span><span class="sxs-lookup"><span data-stu-id="39192-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="39192-107">[in] `mdMethodDef` Токен метаданных, который ссылается на функцию.</span><span class="sxs-lookup"><span data-stu-id="39192-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="39192-108">[in] Идентификатор содержащего класса функции.</span><span class="sxs-lookup"><span data-stu-id="39192-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="39192-109">[in] Число параметров типа для данной функции.</span><span class="sxs-lookup"><span data-stu-id="39192-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="39192-110">Это значение должно быть ноль для функций, не являющимися универсальными.</span><span class="sxs-lookup"><span data-stu-id="39192-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="39192-111">[in] Массив `ClassID` значений, каждое из которых является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="39192-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="39192-112">Значение `typeArgs` может иметь значение NULL, если `cTypeArgs` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="39192-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="39192-113">[out] Указатель на `FunctionID` указанной функции.</span><span class="sxs-lookup"><span data-stu-id="39192-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39192-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="39192-114">Remarks</span></span>  
 <span data-ttu-id="39192-115">Вызов `GetFunctionFromTokenAndTypeArgs` метод с `mdMethodRef` метаданные вместо `mdMethodDef` токен метаданных может привести к непредсказуемым результатам.</span><span class="sxs-lookup"><span data-stu-id="39192-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="39192-116">Вызывающие объекты должны устранить `mdMethodRef` для `mdMethodDef` во время передачи.</span><span class="sxs-lookup"><span data-stu-id="39192-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="39192-117">Если функция еще не загружено, вызов метода `GetFunctionFromTokenAndTypeArgs` приведет к загрузке могла выполняться, который является опасной операцией во множестве контекстов.</span><span class="sxs-lookup"><span data-stu-id="39192-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="39192-118">Например вызов этого метода во время загрузки модулей или типов может привести к бесконечному циклу, как среда выполнения пытается циклически загрузить объекты.</span><span class="sxs-lookup"><span data-stu-id="39192-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="39192-119">Как правило, использование `GetFunctionFromTokenAndTypeArgs` не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="39192-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="39192-120">Если профилировщик интересуют события для определенной функции, их следует хранить `ModuleID` и `mdMethodDef` этой функции, а также использовать [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) для проверки ли данный `FunctionID` — с нужной функции.</span><span class="sxs-lookup"><span data-stu-id="39192-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39192-121">Требования</span><span class="sxs-lookup"><span data-stu-id="39192-121">Requirements</span></span>  
 <span data-ttu-id="39192-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39192-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39192-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39192-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39192-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39192-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39192-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39192-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39192-126">См. также</span><span class="sxs-lookup"><span data-stu-id="39192-126">See Also</span></span>  
 [<span data-ttu-id="39192-127">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="39192-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="39192-128">ICorProfilerInfo2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="39192-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
