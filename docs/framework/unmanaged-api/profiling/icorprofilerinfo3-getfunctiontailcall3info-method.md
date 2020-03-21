---
title: Метод ICorProfilerInfo3::GetFunctionTailcall3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: 5346792cb2a1309268cb4ba48625aa559777fbaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176998"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="816cd-102">Метод ICorProfilerInfo3::GetFunctionTailcall3Info</span><span class="sxs-lookup"><span data-stu-id="816cd-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="816cd-103">Обеспечивает стек кадр функции, которая сообщается профайлеру функцией [FunctionTailcall3WithInfo.](functiontailcall3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="816cd-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="816cd-104">Этот метод может быть вызван только во время обратного вызова `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="816cd-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="816cd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="816cd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="816cd-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="816cd-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="816cd-107">(в) Функция, `FunctionID` которая возвращается.</span><span class="sxs-lookup"><span data-stu-id="816cd-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="816cd-108">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="816cd-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="816cd-109">Профайлер должен предоставить то же `eltInfo` самое, `FunctionTailcall3WithInfo` что было дано профайлеру функцией.</span><span class="sxs-lookup"><span data-stu-id="816cd-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="816cd-110">[out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="816cd-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="816cd-111">Этот дескриптор допустим только во время обратного вызова `FunctionTailcall3WithInfo`, в котором профилировщик вызывал метод `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="816cd-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="816cd-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="816cd-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="816cd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="816cd-113">Requirements</span></span>  
 <span data-ttu-id="816cd-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="816cd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="816cd-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="816cd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="816cd-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="816cd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="816cd-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="816cd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="816cd-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="816cd-118">See also</span></span>

- [<span data-ttu-id="816cd-119">ФункцияEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="816cd-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="816cd-120">ФункцияLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="816cd-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="816cd-121">ФункцияTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="816cd-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="816cd-122">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="816cd-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="816cd-123">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="816cd-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- <span data-ttu-id="816cd-124">[Профилирование](index.md).</span><span class="sxs-lookup"><span data-stu-id="816cd-124">[Profiling](index.md)</span></span>
