---
title: Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433211"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="34ee1-102">Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="34ee1-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="34ee1-103">Возвращает `FunctionID` функции с помощью указанного маркера метаданных, содержащего класс, и `ClassID` значений любых аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="34ee1-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ee1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34ee1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34ee1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34ee1-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="34ee1-106">окне Идентификатор модуля, в котором находится функция.</span><span class="sxs-lookup"><span data-stu-id="34ee1-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="34ee1-107">окне Токен метаданных `mdMethodDef`, ссылающийся на функцию.</span><span class="sxs-lookup"><span data-stu-id="34ee1-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="34ee1-108">окне Идентификатор содержащего класса функции.</span><span class="sxs-lookup"><span data-stu-id="34ee1-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="34ee1-109">окне Число параметров типа для данной функции.</span><span class="sxs-lookup"><span data-stu-id="34ee1-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="34ee1-110">Для неуниверсальных функций это значение должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="34ee1-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="34ee1-111">окне Массив значений `ClassID`, каждый из которых является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="34ee1-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="34ee1-112">Значение `typeArgs` может быть равно NULL, если `cTypeArgs` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="34ee1-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="34ee1-113">заполняет Указатель на `FunctionID` указанной функции.</span><span class="sxs-lookup"><span data-stu-id="34ee1-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34ee1-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="34ee1-114">Remarks</span></span>  
 <span data-ttu-id="34ee1-115">Вызов метода `GetFunctionFromTokenAndTypeArgs` с метаданными `mdMethodRef`, а не `mdMethodDef` маркером метаданных, может иметь непредсказуемые результаты.</span><span class="sxs-lookup"><span data-stu-id="34ee1-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="34ee1-116">Вызывающие объекты должны разрешить `mdMethodRef` в `mdMethodDef` при передаче.</span><span class="sxs-lookup"><span data-stu-id="34ee1-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="34ee1-117">Если функция еще не загружена, вызов `GetFunctionFromTokenAndTypeArgs` приведет к возникновению загрузки, что является опасной операцией во многих контекстах.</span><span class="sxs-lookup"><span data-stu-id="34ee1-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="34ee1-118">Например, вызов этого метода во время загрузки модулей или типов может привести к бесконечному циклу, так как среда выполнения пытается циклически загружать вещи.</span><span class="sxs-lookup"><span data-stu-id="34ee1-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="34ee1-119">В общем случае использование `GetFunctionFromTokenAndTypeArgs` не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="34ee1-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="34ee1-120">Если профилировщики заинтересованы в событиях для определенной функции, они должны хранить `ModuleID` и `mdMethodDef` этой функции, а также использовать [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) для проверки того, является ли данный `FunctionID` требуемой функцией.</span><span class="sxs-lookup"><span data-stu-id="34ee1-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34ee1-121">Требования</span><span class="sxs-lookup"><span data-stu-id="34ee1-121">Requirements</span></span>  
 <span data-ttu-id="34ee1-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34ee1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34ee1-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34ee1-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34ee1-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34ee1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34ee1-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34ee1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ee1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="34ee1-126">See also</span></span>

- [<span data-ttu-id="34ee1-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="34ee1-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="34ee1-128">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="34ee1-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
