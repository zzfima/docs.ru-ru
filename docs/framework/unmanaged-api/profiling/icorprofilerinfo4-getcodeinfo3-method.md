---
title: Метод ICorProfilerInfo4::GetCodeInfo3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aefc9b21381f77fbe80db36da3e9932ad483750
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780838"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="fb98a-102">Метод ICorProfilerInfo4::GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="fb98a-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="fb98a-103">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="fb98a-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb98a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb98a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb98a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb98a-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="fb98a-106">[in] Идентификатор функции, с которым связан машинный код.</span><span class="sxs-lookup"><span data-stu-id="fb98a-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="fb98a-107">[in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="fb98a-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="fb98a-108">[in] Размер массива `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="fb98a-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="fb98a-109">[out] Указатель на общее число [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) доступных структур.</span><span class="sxs-lookup"><span data-stu-id="fb98a-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="fb98a-110">[out] Буфер, предоставляемый вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="fb98a-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="fb98a-111">После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.</span><span class="sxs-lookup"><span data-stu-id="fb98a-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb98a-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb98a-112">Remarks</span></span>  
 <span data-ttu-id="fb98a-113">`GetCodeInfo3` Метод аналогичен методу [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), за исключением того, что он будет получать перекомпиляции JIT идентификатор функции, которая содержит указанный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="fb98a-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb98a-114">`GetCodeInfo3` можно запустить сбор мусора, тогда как [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) не будет.</span><span class="sxs-lookup"><span data-stu-id="fb98a-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="fb98a-115">Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="fb98a-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="fb98a-116">Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).</span><span class="sxs-lookup"><span data-stu-id="fb98a-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="fb98a-117">После `GetCodeInfo3` возвращает, необходимо убедиться, что `codeInfos` буфер был достаточно велик для размещения всех [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="fb98a-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="fb98a-118">Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="fb98a-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="fb98a-119">Если `cCodeInfos` деленное на размер [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) структура меньше, чем `pcCodeInfos`, Выделение большего `codeInfos` буфера, обновите `cCodeInfos` задав новый, больший размер и вызовите метод `GetCodeInfo3` еще раз.</span><span class="sxs-lookup"><span data-stu-id="fb98a-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="fb98a-120">Кроме того, сначала можно вызвать метод `GetCodeInfo3` с буфером `codeInfos` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="fb98a-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="fb98a-121">Затем можно задать `codeInfos` размер равным значению, возвращенному в буфера `pcCodeInfos`, умноженному на размер [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) структуры и вызовите метод `GetCodeInfo3` еще раз.</span><span class="sxs-lookup"><span data-stu-id="fb98a-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb98a-122">Требования</span><span class="sxs-lookup"><span data-stu-id="fb98a-122">Requirements</span></span>  
 <span data-ttu-id="fb98a-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb98a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb98a-124">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb98a-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb98a-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb98a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb98a-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb98a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb98a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fb98a-127">See also</span></span>

- [<span data-ttu-id="fb98a-128">Метод GetCodeInfo2</span><span class="sxs-lookup"><span data-stu-id="fb98a-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="fb98a-129">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="fb98a-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="fb98a-130">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="fb98a-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fb98a-131">Профилирование</span><span class="sxs-lookup"><span data-stu-id="fb98a-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
