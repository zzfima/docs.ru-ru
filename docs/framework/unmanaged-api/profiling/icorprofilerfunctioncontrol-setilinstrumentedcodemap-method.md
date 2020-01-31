---
title: Метод ICorProfilerFunctionControl::SetILInstrumentedCodeMap
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
ms.openlocfilehash: b2fca16b3b859df8bd7409149eb5a3cf7b011c5c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864587"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="d91f9-102">Метод ICorProfilerFunctionControl::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="d91f9-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="d91f9-103">Устанавливает карту кода для указанной функции с помощью указанных записей карты языка CIL.</span><span class="sxs-lookup"><span data-stu-id="d91f9-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d91f9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d91f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d91f9-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="d91f9-106">[в] Количество записей в карте.</span><span class="sxs-lookup"><span data-stu-id="d91f9-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="d91f9-107">[в] Массив записей COR_IL_MAP, выделенный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="d91f9-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="d91f9-108">Интерпретация этих записей такая же, как и для метода [ICorProfilerInfo:: сетилинструментедкодемап](icorprofilerinfo-setilinstrumentedcodemap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d91f9-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d91f9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="d91f9-109">Remarks</span></span>  
 <span data-ttu-id="d91f9-110">Установка сопоставления путем вызова этого метода позволяет отладчику получить сопоставление путем вызова [ICorDebugILCode2:: GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span><span class="sxs-lookup"><span data-stu-id="d91f9-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="d91f9-111">Кроме того, он позволяет отладчику использовать сопоставление внутренним образом при вычислении смещений промежуточного языка для трассировок стека и времени существования переменных.</span><span class="sxs-lookup"><span data-stu-id="d91f9-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d91f9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d91f9-112">Requirements</span></span>  
 <span data-ttu-id="d91f9-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d91f9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d91f9-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d91f9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d91f9-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d91f9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d91f9-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d91f9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91f9-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="d91f9-117">See also</span></span>

- [<span data-ttu-id="d91f9-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d91f9-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
