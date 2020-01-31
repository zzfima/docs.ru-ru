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
ms.openlocfilehash: 164e042ab0f1a275ff07b917658024e22c2d7b0b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862040"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="76a35-102">Метод ICorProfilerInfo4::GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="76a35-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="76a35-103">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="76a35-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76a35-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76a35-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76a35-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="76a35-106">[in] Идентификатор функции, с которым связан машинный код.</span><span class="sxs-lookup"><span data-stu-id="76a35-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="76a35-107">[in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="76a35-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="76a35-108">[in] Размер массива `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="76a35-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="76a35-109">заполняет Указатель на общее число доступных структур [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="76a35-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="76a35-110">[out] Буфер, предоставляемый вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="76a35-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="76a35-111">После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.</span><span class="sxs-lookup"><span data-stu-id="76a35-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76a35-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="76a35-112">Remarks</span></span>  
 <span data-ttu-id="76a35-113">Метод `GetCodeInfo3` аналогичен [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md), за исключением того, что он получает JIT-перекомпилированный идентификатор функции, которая содержит указанный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="76a35-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76a35-114">`GetCodeInfo3` может запустить сборку мусора, в то время как [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) не будет.</span><span class="sxs-lookup"><span data-stu-id="76a35-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="76a35-115">Дополнительные сведения см. в [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="76a35-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="76a35-116">Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).</span><span class="sxs-lookup"><span data-stu-id="76a35-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="76a35-117">После того, как `GetCodeInfo3` возвращает, необходимо убедиться, что буфер `codeInfos` достаточно большой, чтобы вместить все [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="76a35-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="76a35-118">Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="76a35-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="76a35-119">Если `cCodeInfos` деленная на размер структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) меньше `pcCodeInfos`, выделите больший буфер `codeInfos`, обновите `cCodeInfos` с новым, большим размером и снова вызовите `GetCodeInfo3`.</span><span class="sxs-lookup"><span data-stu-id="76a35-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="76a35-120">Кроме того, сначала можно вызвать метод `GetCodeInfo3` с буфером `codeInfos` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="76a35-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="76a35-121">Затем можно присвоить `codeInfos` размеру буфера значение, возвращаемое в `pcCodeInfos`, умноженное на размер [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) структуры, и снова вызвать `GetCodeInfo3`.</span><span class="sxs-lookup"><span data-stu-id="76a35-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76a35-122">Требования</span><span class="sxs-lookup"><span data-stu-id="76a35-122">Requirements</span></span>  
 <span data-ttu-id="76a35-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76a35-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76a35-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76a35-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76a35-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76a35-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76a35-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a35-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a35-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="76a35-127">See also</span></span>

- [<span data-ttu-id="76a35-128">Метод GetCodeInfo2</span><span class="sxs-lookup"><span data-stu-id="76a35-128">GetCodeInfo2 Method</span></span>](icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="76a35-129">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="76a35-129">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="76a35-130">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="76a35-130">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="76a35-131">Профилирование</span><span class="sxs-lookup"><span data-stu-id="76a35-131">Profiling</span></span>](index.md)
