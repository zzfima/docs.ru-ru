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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31caa87b1eaa48532ffb20b46c593242379c7ae8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780346"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="f72c5-102">Метод ICorProfilerFunctionControl::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="f72c5-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="f72c5-103">Устанавливает карту кода для указанной функции с помощью указанных записей карты языка CIL.</span><span class="sxs-lookup"><span data-stu-id="f72c5-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f72c5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f72c5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f72c5-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="f72c5-106">[в] Количество записей в карте.</span><span class="sxs-lookup"><span data-stu-id="f72c5-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="f72c5-107">[in] Выделенный вызывающим объектом массив COR_IL_MAP записей.</span><span class="sxs-lookup"><span data-stu-id="f72c5-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="f72c5-108">Интерпретация этих записей зависит так же, как [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f72c5-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f72c5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f72c5-109">Remarks</span></span>  
 <span data-ttu-id="f72c5-110">Настройка сопоставления путем вызова этого метода позволяет отладчику получить сопоставление, вызывая [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span><span class="sxs-lookup"><span data-stu-id="f72c5-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="f72c5-111">Кроме того, он позволяет отладчику использовать сопоставление внутренним образом при вычислении смещений промежуточного языка для трассировок стека и времени существования переменных.</span><span class="sxs-lookup"><span data-stu-id="f72c5-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f72c5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f72c5-112">Requirements</span></span>  
 <span data-ttu-id="f72c5-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f72c5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72c5-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f72c5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f72c5-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f72c5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f72c5-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72c5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72c5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f72c5-117">See also</span></span>

- [<span data-ttu-id="f72c5-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f72c5-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
