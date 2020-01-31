---
title: Метод ICorProfilerInfo2::GetClassIDInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
ms.openlocfilehash: 64d2cd76dafb1a51814b916b5ce73fb08cdcaef9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868864"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="186e4-102">Метод ICorProfilerInfo2::GetClassIDInfo2</span><span class="sxs-lookup"><span data-stu-id="186e4-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="186e4-103">Получает родительский модуль и маркер метаданных для открытого универсального определения указанного класса, `ClassID` его родительского класса и `ClassID` для каждого аргумента типа, если он имеется, класса.</span><span class="sxs-lookup"><span data-stu-id="186e4-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="186e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="186e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="186e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="186e4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="186e4-106">[in] Идентификатор класса, для которого будут извлекаться сведения.</span><span class="sxs-lookup"><span data-stu-id="186e4-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="186e4-107">заполняет Указатель на идентификатор родительского модуля для открытого универсального определения указанного класса.</span><span class="sxs-lookup"><span data-stu-id="186e4-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="186e4-108">заполняет Указатель на маркер метаданных для открытого универсального определения указанного класса.</span><span class="sxs-lookup"><span data-stu-id="186e4-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="186e4-109">[out] Указатель на идентификатор родительского класса.</span><span class="sxs-lookup"><span data-stu-id="186e4-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="186e4-110">[in] Размер массива `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="186e4-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="186e4-111">[out] Указатель на общее число доступных элементов.</span><span class="sxs-lookup"><span data-stu-id="186e4-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="186e4-112">[out] Массив значений `ClassID`, каждое из которых представляет идентификатор аргумента типа класса.</span><span class="sxs-lookup"><span data-stu-id="186e4-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="186e4-113">При возврате метода в массиве `typeArgs` будут содержаться все или некоторые доступные значения `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="186e4-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="186e4-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="186e4-114">Remarks</span></span>  
 <span data-ttu-id="186e4-115">Метод `GetClassIDInfo2` аналогичен методу [ICorProfilerInfo:: жетклассидинфо](icorprofilerinfo-getclassidinfo-method.md) , но `GetClassIDInfo2` получает дополнительные сведения о универсальном типе.</span><span class="sxs-lookup"><span data-stu-id="186e4-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="186e4-116">Чтобы получить интерфейс [метаданных](../../../../docs/framework/unmanaged-api/metadata/index.md) для заданного модуля, код профилировщика может вызвать метод [ICorProfilerInfo:: жетмодулеметадата](icorprofilerinfo-getmodulemetadata-method.md) .</span><span class="sxs-lookup"><span data-stu-id="186e4-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="186e4-117">Токен метаданных, возвращенный в расположение, на которое ссылается `pTypeDefToken`, можно впоследствии использовать для доступа к метаданным класса.</span><span class="sxs-lookup"><span data-stu-id="186e4-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="186e4-118">После возврата метода `GetClassIDInfo2` необходимо убедиться, что буфер `typeArgs` был достаточно велик, чтобы вместить в себя все значения `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="186e4-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="186e4-119">Для этого сравните значение, на которое указывает параметр `pcNumTypeArgs`, со значением параметра `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="186e4-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="186e4-120">Если параметр `pcNumTypeArgs` указывает на значение, превышающее значение `cNumTypeArgs`, выделите буфер `typeArgs` большего размера, обновите параметр `cNumTypeArgs`, задав новый, больший размер, и вызовите метод `GetClassIDInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="186e4-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="186e4-121">Кроме того, сначала можно вызвать метод `GetClassIDInfo2` с буфером `typeArgs` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="186e4-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="186e4-122">Затем можно задать размер буфера `typeArgs` равным значению, возвращенному в параметре `pcNumTypeArgs`, и вызвать метод `GetClassIDInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="186e4-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="186e4-123">Требования</span><span class="sxs-lookup"><span data-stu-id="186e4-123">Requirements</span></span>  
 <span data-ttu-id="186e4-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="186e4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="186e4-125">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="186e4-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="186e4-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="186e4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="186e4-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="186e4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186e4-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="186e4-128">See also</span></span>

- [<span data-ttu-id="186e4-129">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="186e4-129">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="186e4-130">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="186e4-130">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="186e4-131">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="186e4-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="186e4-132">Профилирование</span><span class="sxs-lookup"><span data-stu-id="186e4-132">Profiling</span></span>](index.md)
