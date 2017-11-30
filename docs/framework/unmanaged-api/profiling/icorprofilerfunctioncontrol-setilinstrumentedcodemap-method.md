---
title: "Метод ICorProfilerFunctionControl::SetILInstrumentedCodeMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f7f97a383cf6769d4449e7a5f6be8d31fe6e3b51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="cc8b8-102">Метод ICorProfilerFunctionControl::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="cc8b8-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="cc8b8-103">Устанавливает карту кода для указанной функции с помощью указанных записей карты общего промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc8b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc8b8-104">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc8b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc8b8-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="cc8b8-106">[в] Количество записей в карте.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="cc8b8-107">[in] Выделенный вызывающим объектом массив COR_IL_MAP записей.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="cc8b8-108">Интерпретация эти записи одинаково как для [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc8b8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc8b8-109">Remarks</span></span>  
 <span data-ttu-id="cc8b8-110">Настройка сопоставления путем вызова этого метода позволяет отладчику получить сопоставление, вызывая [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span><span class="sxs-lookup"><span data-stu-id="cc8b8-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="cc8b8-111">Кроме того, он позволяет отладчику использовать сопоставление внутренним образом при вычислении смещений промежуточного языка для трассировок стека и времени существования переменных.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc8b8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="cc8b8-112">Requirements</span></span>  
 <span data-ttu-id="cc8b8-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc8b8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc8b8-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc8b8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc8b8-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc8b8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc8b8-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc8b8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8b8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cc8b8-117">See Also</span></span>  
 [<span data-ttu-id="cc8b8-118">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="cc8b8-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
