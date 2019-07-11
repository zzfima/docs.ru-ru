---
title: Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a88a6c19a5c8b45576dd6f632adf70f7ec2eed55
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751875"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="b232c-102">Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="b232c-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="b232c-103">Получает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любого типа аргументов.</span><span class="sxs-lookup"><span data-stu-id="b232c-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b232c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b232c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b232c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b232c-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="b232c-106">[in] Идентификатор модуля, в котором находится тип.</span><span class="sxs-lookup"><span data-stu-id="b232c-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="b232c-107">[in] `mdTypeDef` Токен метаданных, который ссылается на тип.</span><span class="sxs-lookup"><span data-stu-id="b232c-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="b232c-108">[in] Число параметров типа для заданного типа.</span><span class="sxs-lookup"><span data-stu-id="b232c-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="b232c-109">Это значение должно быть ноль для неуниверсальных типов.</span><span class="sxs-lookup"><span data-stu-id="b232c-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="b232c-110">[in] Массив `ClassID` значений, каждое из которых является аргументом типа.</span><span class="sxs-lookup"><span data-stu-id="b232c-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="b232c-111">Значение `typeArgs` может иметь значение NULL, если `cTypeArgs` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="b232c-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="b232c-112">[out] Указатель на `ClassID` указанного типа.</span><span class="sxs-lookup"><span data-stu-id="b232c-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b232c-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b232c-113">Remarks</span></span>  
 <span data-ttu-id="b232c-114">Вызов `GetClassFromTokenAndTypeArgs` метод с `mdTypeRef` вместо `mdTypeDef` токен метаданных может привести к непредсказуемым результатам; нужно будет разрешить вызывающим объектам `mdTypeRef` для `mdTypeDef` при передаче.</span><span class="sxs-lookup"><span data-stu-id="b232c-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="b232c-115">Если тип еще не загружено, вызов метода `GetClassFromTokenAndTypeArgs` активируют загрузки, которая является опасной операцией во многих контекстах.</span><span class="sxs-lookup"><span data-stu-id="b232c-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="b232c-116">Например вызов этого метода во время загрузки модулей или других типов может привести к бесконечный цикл, как среда выполнения пытается циклически загружать объекты.</span><span class="sxs-lookup"><span data-stu-id="b232c-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="b232c-117">Как правило, использование `GetClassFromTokenAndTypeArgs` не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="b232c-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="b232c-118">Если профилировщик интересуют события для определенного типа, их следует хранить `ModuleID` и `mdTypeDef` указанного типа, используйте [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) проверяемый ли заданный `ClassID` , — это требуемый тип.</span><span class="sxs-lookup"><span data-stu-id="b232c-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b232c-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b232c-119">Requirements</span></span>  
 <span data-ttu-id="b232c-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b232c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b232c-121">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b232c-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b232c-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b232c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b232c-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b232c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b232c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b232c-124">See also</span></span>

- [<span data-ttu-id="b232c-125">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b232c-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b232c-126">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="b232c-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
