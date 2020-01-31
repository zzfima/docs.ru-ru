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
ms.openlocfilehash: 945cf84e6f6201879514e29a21f7f5462aa33fdb
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868672"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="e3fd2-102">Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="e3fd2-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="e3fd2-103">Возвращает `FunctionID` функции с помощью указанного маркера метаданных, содержащего класс, и `ClassID` значений любых аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3fd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3fd2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3fd2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3fd2-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="e3fd2-106">окне Идентификатор модуля, в котором находится функция.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="e3fd2-107">окне Токен метаданных `mdMethodDef`, ссылающийся на функцию.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="e3fd2-108">окне Идентификатор содержащего класса функции.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="e3fd2-109">окне Число параметров типа для данной функции.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="e3fd2-110">Для неуниверсальных функций это значение должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="e3fd2-111">окне Массив значений `ClassID`, каждый из которых является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="e3fd2-112">Значение `typeArgs` может быть равно NULL, если `cTypeArgs` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="e3fd2-113">заполняет Указатель на `FunctionID` указанной функции.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3fd2-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="e3fd2-114">Remarks</span></span>  
 <span data-ttu-id="e3fd2-115">Вызов метода `GetFunctionFromTokenAndTypeArgs` с метаданными `mdMethodRef`, а не `mdMethodDef` маркером метаданных, может иметь непредсказуемые результаты.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="e3fd2-116">Вызывающие объекты должны разрешить `mdMethodRef` в `mdMethodDef` при передаче.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="e3fd2-117">Если функция еще не загружена, вызов `GetFunctionFromTokenAndTypeArgs` приведет к возникновению загрузки, что является опасной операцией во многих контекстах.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="e3fd2-118">Например, вызов этого метода во время загрузки модулей или типов может привести к бесконечному циклу, так как среда выполнения пытается циклически загружать вещи.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="e3fd2-119">В общем случае использование `GetFunctionFromTokenAndTypeArgs` не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="e3fd2-120">Если профилировщики заинтересованы в событиях для определенной функции, они должны хранить `ModuleID` и `mdMethodDef` этой функции, а также использовать [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) для проверки того, является ли данный `FunctionID` требуемой функцией.</span><span class="sxs-lookup"><span data-stu-id="e3fd2-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3fd2-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e3fd2-121">Requirements</span></span>  
 <span data-ttu-id="e3fd2-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3fd2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3fd2-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3fd2-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3fd2-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3fd2-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3fd2-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3fd2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3fd2-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3fd2-126">See also</span></span>

- [<span data-ttu-id="e3fd2-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e3fd2-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e3fd2-128">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="e3fd2-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
