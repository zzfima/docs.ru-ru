---
title: "Метод ICorProfilerInfo2::GetFunctionInfo2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b0c288b88c868bc6e324ec57b3956344f03f34e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a><span data-ttu-id="c4d85-102">Метод ICorProfilerInfo2::GetFunctionInfo2</span><span class="sxs-lookup"><span data-stu-id="c4d85-102">ICorProfilerInfo2::GetFunctionInfo2 Method</span></span>
<span data-ttu-id="c4d85-103">Получает родительский класс, токен метаданных и `ClassID` для каждого аргумента типа функции при их наличии.</span><span class="sxs-lookup"><span data-stu-id="c4d85-103">Gets the parent class, the metadata token, and the `ClassID` of each type argument, if present, of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4d85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4d85-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4d85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4d85-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="c4d85-106">[входной] Идентификатор функции, для которой нужно получить родительский класс и другую информацию.</span><span class="sxs-lookup"><span data-stu-id="c4d85-106">[in] The ID of the function for which to get the parent class and other information.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="c4d85-107">[входной] Значение `COR_PRF_FRAME_INFO`, указывающее на информацию о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="c4d85-107">[in] A `COR_PRF_FRAME_INFO` value that points to information about a stack frame.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="c4d85-108">[выходной] Указатель на родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="c4d85-108">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="c4d85-109">[выходной] Указатель на модуль, в котором определен родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="c4d85-109">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="c4d85-110">[выходной] Указатель на токен метаданных функции.</span><span class="sxs-lookup"><span data-stu-id="c4d85-110">[out] A pointer to the metadata token for the function.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="c4d85-111">[in] Размер массива `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="c4d85-111">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcTypeArgs`  
 <span data-ttu-id="c4d85-112">[выходной] Указатель на общее количество значений `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="c4d85-112">[out] A pointer to the total number of `ClassID` values.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="c4d85-113">[выходной] Массив значений `ClassID`, каждое из которых является идентификатором аргумента типа функции.</span><span class="sxs-lookup"><span data-stu-id="c4d85-113">[out] An array of `ClassID` values, each of which is the ID of a type argument of the function.</span></span> <span data-ttu-id="c4d85-114">При возврате из метода в параметре `typeArgs` содержатся все или некоторые значения `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="c4d85-114">When the method returns, `typeArgs` will contain some or all of the `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4d85-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4d85-115">Remarks</span></span>  
 <span data-ttu-id="c4d85-116">Профилировщик кода может вызвать [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) для получения [метаданные](../../../../docs/framework/unmanaged-api/metadata/index.md) интерфейс для данного модуля.</span><span class="sxs-lookup"><span data-stu-id="c4d85-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="c4d85-117">Токен метаданных, возвращенный в расположение, на которое ссылается `pToken`, можно впоследствии использовать для доступа к метаданным функции.</span><span class="sxs-lookup"><span data-stu-id="c4d85-117">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="c4d85-118">Идентификатор класса и аргументы типа, возвращенные с помощью параметров `pClassId` и `typeArgs`, зависят от значения, переданного в параметре `frameInfo`, как показано в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="c4d85-118">The class ID and type arguments that are returned through the `pClassId` and `typeArgs` parameters depend on the value that is passed in the `frameInfo` parameter, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c4d85-119">Значение параметра `frameInfo`</span><span class="sxs-lookup"><span data-stu-id="c4d85-119">Value of the `frameInfo` parameter</span></span>|<span data-ttu-id="c4d85-120">Результат</span><span class="sxs-lookup"><span data-stu-id="c4d85-120">Result</span></span>|  
|----------------------------------------|------------|  
|<span data-ttu-id="c4d85-121">Значение `COR_PRF_FRAME_INFO`, полученное в результате обратного вызова `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="c4d85-121">A `COR_PRF_FRAME_INFO` value that was obtained from a `FunctionEnter2` callback</span></span>|<span data-ttu-id="c4d85-122">Значение `ClassID`, возвращенное в расположении, на которое ссылается параметр `pClassId`, и все аргументы типа, возвращенные в массиве `typeArgs`, будут точными.</span><span class="sxs-lookup"><span data-stu-id="c4d85-122">The `ClassID`, returned in the location referenced by `pClassId`, and all type arguments, returned in the `typeArgs` array, will be exact.</span></span>|  
|<span data-ttu-id="c4d85-123">Объект `COR_PRF_FRAME_INFO`, полученный из источника, отличного от обратного вызова `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="c4d85-123">A `COR_PRF_FRAME_INFO` that was obtained from a source other than a `FunctionEnter2` callback</span></span>|<span data-ttu-id="c4d85-124">Точное значение `ClassID` и аргументы типа определить нельзя.</span><span class="sxs-lookup"><span data-stu-id="c4d85-124">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="c4d85-125">То есть, `ClassID` может иметь значение NULL, а некоторые аргументы типа могут быть возвращены в виде объекта <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c4d85-125">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
|<span data-ttu-id="c4d85-126">Нуль</span><span class="sxs-lookup"><span data-stu-id="c4d85-126">Zero</span></span>|<span data-ttu-id="c4d85-127">Точное значение `ClassID` и аргументы типа определить нельзя.</span><span class="sxs-lookup"><span data-stu-id="c4d85-127">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="c4d85-128">То есть, `ClassID` может иметь значение NULL, а некоторые аргументы типа могут быть возвращены в виде объекта <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c4d85-128">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
  
 <span data-ttu-id="c4d85-129">После возврата из метода `GetFunctionInfo2` нужно убедиться в том, что буфер `typeArgs` был достаточно велик, чтобы вместить в себя все значения `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="c4d85-129">After `GetFunctionInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="c4d85-130">Для этого сравните значение, на которое указывает параметр `pcTypeArgs`, со значением параметра `cTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="c4d85-130">To do this, compare the value that `pcTypeArgs` points to with the value of the `cTypeArgs` parameter.</span></span> <span data-ttu-id="c4d85-131">Если параметр `pcTypeArgs` указывает на значение, превышающее значение `cTypeArgs`, деленное на размер значения `ClassID`, нужно выделить буфер `pcTypeArgs` большего размера, обновить параметр `cTypeArgs`, задав новый, больший размер и вызвать метод `GetFunctionInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="c4d85-131">If `pcTypeArgs` points to a value that is larger than `cTypeArgs` divided by the size of a `ClassID` value, allocate a larger `pcTypeArgs` buffer, update `cTypeArgs` with the new, larger size, and call `GetFunctionInfo2` again.</span></span>  
  
 <span data-ttu-id="c4d85-132">Кроме того, сначала можно вызвать метод `GetFunctionInfo2` с буфером `pcTypeArgs` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="c4d85-132">Alternatively, you can first call `GetFunctionInfo2` with a zero-length `pcTypeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c4d85-133">Затем можно задать размер буфера равным значению, возвращенному в параметре `pcTypeArgs`, деленному на размер значения `ClassID`, и вызвать метод `GetFunctionInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="c4d85-133">You can then set the buffer size to the value returned in `pcTypeArgs` divided by the size of a `ClassID` value, and call `GetFunctionInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4d85-134">Требования</span><span class="sxs-lookup"><span data-stu-id="c4d85-134">Requirements</span></span>  
 <span data-ttu-id="c4d85-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4d85-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4d85-136">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4d85-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4d85-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4d85-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4d85-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4d85-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d85-139">См. также</span><span class="sxs-lookup"><span data-stu-id="c4d85-139">See Also</span></span>  
 [<span data-ttu-id="c4d85-140">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c4d85-140">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="c4d85-141">ICorProfilerInfo2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c4d85-141">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="c4d85-142">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="c4d85-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c4d85-143">Профилирование</span><span class="sxs-lookup"><span data-stu-id="c4d85-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
