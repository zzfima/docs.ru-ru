---
title: "Метод ICorDebugILCode2::GetInstrumentedILMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetInstrumentedILMap
api_location: mscordbi.dll
api_type: COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b740f378b4fd15fe6bf4a9832348869878e2a4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="c66ab-102">Метод ICorDebugILCode2::GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="c66ab-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="c66ab-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="c66ab-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c66ab-104">Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c66ab-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c66ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c66ab-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c66ab-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c66ab-106">Parameters</span></span>  
 <span data-ttu-id="c66ab-107">cMap</span><span class="sxs-lookup"><span data-stu-id="c66ab-107">cMap</span></span>  
 <span data-ttu-id="c66ab-108">[в] Емкость хранилища массива `map`.</span><span class="sxs-lookup"><span data-stu-id="c66ab-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="c66ab-109">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="c66ab-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="c66ab-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="c66ab-110">pcMap</span></span>  
 <span data-ttu-id="c66ab-111">[out] Количество значений COR_IL_MAP, записанных в массив сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="c66ab-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="c66ab-112">map</span><span class="sxs-lookup"><span data-stu-id="c66ab-112">map</span></span>  
 <span data-ttu-id="c66ab-113">[out] Массив значений COR_IL_MAP, предоставляющие сведения о сопоставлении из Инструментированного профилировщиком промежуточного языка исходного метода.</span><span class="sxs-lookup"><span data-stu-id="c66ab-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c66ab-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c66ab-114">Remarks</span></span>  
 <span data-ttu-id="c66ab-115">Если профилировщик устанавливает сопоставление, вызывая [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) метода, отладчик может вызвать этот метод для извлечения сопоставление и использовать его при вычислении смещений промежуточного языка для стека трассировки и времени существования переменных.</span><span class="sxs-lookup"><span data-stu-id="c66ab-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="c66ab-116">Если `cMap` равно 0 и `pcMap` не является**null**, `pcMap` равно числу доступных COR_IL_MAP значений.</span><span class="sxs-lookup"><span data-stu-id="c66ab-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="c66ab-117">Если значение `cMap` не равно 0, оно обозначает емкость хранилища массива `map`.</span><span class="sxs-lookup"><span data-stu-id="c66ab-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="c66ab-118">При возвращении метода `map` содержит более `cMap` элементы, и `pcMap` равно числу значений COR_IL_MAP, фактически записанных `map` массива.</span><span class="sxs-lookup"><span data-stu-id="c66ab-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="c66ab-119">Если промежуточный язык не инструментирован или профилировщик не предоставил сопоставление, этот метод возвращает значение `S_OK` и присваивает `pcMap` значение 0.</span><span class="sxs-lookup"><span data-stu-id="c66ab-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c66ab-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c66ab-120">Requirements</span></span>  
 <span data-ttu-id="c66ab-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c66ab-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c66ab-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c66ab-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c66ab-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c66ab-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c66ab-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c66ab-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c66ab-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c66ab-125">See Also</span></span>  
 [<span data-ttu-id="c66ab-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="c66ab-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [<span data-ttu-id="c66ab-127">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="c66ab-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="c66ab-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c66ab-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
