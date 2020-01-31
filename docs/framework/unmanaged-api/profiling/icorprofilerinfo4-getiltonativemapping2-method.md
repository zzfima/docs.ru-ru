---
title: Метод ICorProfilerInfo4::GetILToNativeMapping2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
ms.openlocfilehash: 4fccee3b94efd65312206afb22c87f30609f9e6b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868464"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="d7791-102">Метод ICorProfilerInfo4::GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="d7791-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="d7791-103">Получает сопоставление из смещений MSIL в собственные смещения для кода, содержащегося в версии указанной функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="d7791-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7791-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7791-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7791-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7791-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d7791-106">[in] Идентификатор функции, которая содержит код.</span><span class="sxs-lookup"><span data-stu-id="d7791-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="d7791-107">[in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="d7791-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="d7791-108">Удостоверение должно быть равно нулю в .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="d7791-108">The identity must be zero in the .NET Framework 4.5.</span></span>  
  
 `cMap`  
 <span data-ttu-id="d7791-109">[in] Максимальный размер массива `map`.</span><span class="sxs-lookup"><span data-stu-id="d7791-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="d7791-110">[out] Общее количество доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.</span><span class="sxs-lookup"><span data-stu-id="d7791-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="d7791-111">[out] Массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`, каждая из которых задает смещения.</span><span class="sxs-lookup"><span data-stu-id="d7791-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="d7791-112">После возврата метода `GetILToNativeMapping2` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="d7791-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7791-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="d7791-113">Remarks</span></span>  
 <span data-ttu-id="d7791-114">`GetILToNativeMapping2` похож на метод [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) , за исключением того, что он позволяет профилировщику указать идентификатор перекомпилированной функции в будущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="d7791-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7791-115">Метод [икорпрофилерфунктионконтрол:: сетилинструментедкодемап](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) не реализован в .NET Framework 4,5, поэтому функции, которые были JIT-скомпилированы, не могут иметь сопоставление с IL-кодом, которое отличается от первоначально скомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="d7791-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the .NET Framework 4.5, so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="d7791-116">Таким образом, `GetILToNativeMapping2` нельзя вызывать с ненулевым JIT-перекомпилированным ИДЕНТИФИКАТОРом в .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="d7791-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="d7791-117">Метод `GetILToNativeMapping2` возвращает массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="d7791-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="d7791-118">Чтобы убедиться в том, что определенные диапазоны машинных инструкций соответствуют специальным областям кода (например, прологу), элементу в массиве может быть присвоено `ilOffset` поле со значением перечисления [кордебугилтонативемаппингтипес](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d7791-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="d7791-119">После возврата метода `GetILToNativeMapping2` необходимо убедиться, что буфер `map` был достаточно велик, чтобы вместить в себя все структуры `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="d7791-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="d7791-120">Для этого сравните значение параметра `cMap` со значением параметра `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="d7791-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="d7791-121">Если значение `pcMap`, умноженное на размер структуры `COR_DEBUG_IL_TO_NATIVE_MAP`COR_PRF_CODE_INFO, больше значения `cMap`, выделите буфер `map` большего размера, обновите параметр `cMap`, задав новый, больший размер, и вызовите метод `GetILToNativeMapping2` снова.</span><span class="sxs-lookup"><span data-stu-id="d7791-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="d7791-122">Кроме того, сначала можно вызвать метод `GetILToNativeMapping2` с буфером `map` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="d7791-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="d7791-123">Затем можно задать размер буфера равным значению, возвращенному в параметре `pcMap`, и вызвать метод `GetILToNativeMapping2` снова.</span><span class="sxs-lookup"><span data-stu-id="d7791-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7791-124">Требования</span><span class="sxs-lookup"><span data-stu-id="d7791-124">Requirements</span></span>  
 <span data-ttu-id="d7791-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7791-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7791-126">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7791-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7791-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7791-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7791-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7791-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7791-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7791-129">See also</span></span>

- [<span data-ttu-id="d7791-130">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="d7791-130">GetILToNativeMapping Method</span></span>](icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="d7791-131">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="d7791-131">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="d7791-132">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="d7791-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d7791-133">Профилирование</span><span class="sxs-lookup"><span data-stu-id="d7791-133">Profiling</span></span>](index.md)
