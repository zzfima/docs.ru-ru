---
title: Метод ICorProfilerInfo3::GetFunctionEnter3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 50d16b8036144d6ede349149fa4ae37344064d8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177024"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="901ba-102">Метод ICorProfilerInfo3::GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="901ba-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="901ba-103">Предоставляет стек кадра и аргумент информации о функции, которая в настоящее время сообщается профайлеру функции [FunctionEnter3WithInfo.](functionenter3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="901ba-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="901ba-104">Этот метод может быть вызван только во время обратного вызова `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="901ba-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="901ba-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="901ba-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="901ba-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="901ba-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="901ba-107">[in] `FunctionID` функции, которая вводится.</span><span class="sxs-lookup"><span data-stu-id="901ba-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="901ba-108">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="901ba-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="901ba-109">Профайлер должен предоставить то же `eltInfo` самое, что он был дан [функцией FunctionEnter3WithInfo.](functionenter3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="901ba-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="901ba-110">[out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="901ba-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="901ba-111">Этот дескриптор допустим только во время обратного вызова `FunctionEnter3WithInfo`, в котором профилировщик вызывал метод `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="901ba-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="901ba-112">(в, вне) Указатель на общий размер, в байтах, [структуры COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) (плюс любые дополнительные `pArgumentInfo` [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) структуры для аргумента диапазонов, указанных).</span><span class="sxs-lookup"><span data-stu-id="901ba-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="901ba-113">Если указанный размер недостаточен, то возвращается значение ERROR_INSUFFICIENT_BUFFER, и ожидаемый размер сохраняется в `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="901ba-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="901ba-114">Чтобы вызвать `GetFunctionEnter3Info` только для получения ожидаемого значения для `*pcbArgumentInfo`, установите `*pcbArgumentInfo`= 0 и `pArgumentInfo`= NULL.</span><span class="sxs-lookup"><span data-stu-id="901ba-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="901ba-115">(ваут) Указатель на [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) структуру, описывающий расположение аргументов функции в памяти, в порядке слева направо.</span><span class="sxs-lookup"><span data-stu-id="901ba-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="901ba-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="901ba-116">Remarks</span></span>  
 <span data-ttu-id="901ba-117">Профилировщик должен выделить достаточно места для структуры `COR_PRF_FUNCTION_ARGUMENT_INFO` проверяемой функции, и должен указать размер в параметре `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="901ba-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="901ba-118">Требования</span><span class="sxs-lookup"><span data-stu-id="901ba-118">Requirements</span></span>  
 <span data-ttu-id="901ba-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="901ba-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="901ba-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="901ba-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="901ba-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="901ba-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="901ba-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="901ba-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901ba-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="901ba-123">See also</span></span>

- [<span data-ttu-id="901ba-124">ФункцияEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="901ba-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="901ba-125">ФункцияLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="901ba-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="901ba-126">ФункцияTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="901ba-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="901ba-127">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="901ba-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="901ba-128">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="901ba-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- <span data-ttu-id="901ba-129">[Профилирование](index.md).</span><span class="sxs-lookup"><span data-stu-id="901ba-129">[Profiling](index.md)</span></span>
