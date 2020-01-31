---
title: Метод ICorDebugILCode2::GetInstrumentedILMap
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 728a6c83dc321fa28dc4ff84c4e874d886524b36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788562"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="0dd14-102">Метод ICorDebugILCode2::GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="0dd14-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="0dd14-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="0dd14-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0dd14-104">Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0dd14-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd14-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dd14-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dd14-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0dd14-106">Parameters</span></span>  
 <span data-ttu-id="0dd14-107">cMap</span><span class="sxs-lookup"><span data-stu-id="0dd14-107">cMap</span></span>  
 <span data-ttu-id="0dd14-108">[в] Емкость хранилища массива `map`.</span><span class="sxs-lookup"><span data-stu-id="0dd14-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="0dd14-109">Дополнительные сведения см. в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="0dd14-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="0dd14-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="0dd14-110">pcMap</span></span>  
 <span data-ttu-id="0dd14-111">[из] Количество значений COR_IL_MAP, записанных в массив сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="0dd14-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="0dd14-112">map</span><span class="sxs-lookup"><span data-stu-id="0dd14-112">map</span></span>  
 <span data-ttu-id="0dd14-113">[из] Массив значений COR_IL_MAP, предоставляющий информацию о сопоставлениях промежуточного языка, инструментированного профилировщиком, и промежуточного языка исходного метода.</span><span class="sxs-lookup"><span data-stu-id="0dd14-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dd14-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="0dd14-114">Remarks</span></span>  
 <span data-ttu-id="0dd14-115">Если профилировщик задает сопоставление путем вызова метода [ICorProfilerInfo:: сетилинструментедкодемап](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , отладчик может вызвать этот метод, чтобы получить сопоставление и использовать внутреннее сопоставление при вычислении смещений Il для трассировок стека и времени существования переменных.</span><span class="sxs-lookup"><span data-stu-id="0dd14-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="0dd14-116">Если `cMap` имеет значение 0, а `pcMap` не равно**null**, для `pcMap` задается количество доступных COR_IL_MAP значений.</span><span class="sxs-lookup"><span data-stu-id="0dd14-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="0dd14-117">Если значение `cMap` не равно 0, оно обозначает емкость хранилища массива `map`.</span><span class="sxs-lookup"><span data-stu-id="0dd14-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="0dd14-118">Когда метод возвращает значение, `map` содержит максимум `cMap` элементов, а `pcMap` задает количество COR_IL_MAP значений, фактически записанных в массив `map`.</span><span class="sxs-lookup"><span data-stu-id="0dd14-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="0dd14-119">Если промежуточный язык не инструментирован или профилировщик не предоставил сопоставление, этот метод возвращает значение `S_OK` и присваивает `pcMap` значение 0.</span><span class="sxs-lookup"><span data-stu-id="0dd14-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dd14-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0dd14-120">Requirements</span></span>  
 <span data-ttu-id="0dd14-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dd14-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dd14-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dd14-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dd14-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dd14-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dd14-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dd14-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd14-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="0dd14-125">See also</span></span>

- [<span data-ttu-id="0dd14-126">ICorProfilerInfo:: Сетилинструментедкодемап</span><span class="sxs-lookup"><span data-stu-id="0dd14-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="0dd14-127">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="0dd14-127">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="0dd14-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0dd14-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
