---
title: "Метод ICorProfilerInfo::SetILInstrumentedCodeMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 127f6d76e85ed30f1407d16f8d81c93dd2941960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="34c93-102">Метод ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="34c93-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="34c93-103">Устанавливает карту кода для указанной функции с помощью указанных записей карты Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="34c93-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34c93-104">В .NET Framework версии 2.0, вызов `SetILInstrumentedCodeMap` на `FunctionID` что представляет универсальный функционировать в определенного домена приложения влияет на все экземпляры функции в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="34c93-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c93-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34c93-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34c93-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="34c93-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="34c93-107">[in] Идентификатор функции, для которого требуется задать карту кода.</span><span class="sxs-lookup"><span data-stu-id="34c93-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="34c93-108">[in] Логическое значение, указывающее, является ли вызов `SetILInstrumentedCodeMap` метод является первым для какого-либо `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="34c93-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="34c93-109">Задать `fStartJit` для `true` в первом вызове `SetILInstrumentedCodeMap` для данного `FunctionID`, а в `false` соответственно.</span><span class="sxs-lookup"><span data-stu-id="34c93-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="34c93-110">[in] Число элементов в `cILMapEntries` массива.</span><span class="sxs-lookup"><span data-stu-id="34c93-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="34c93-111">[in] Массив структур COR_IL_MAP, каждый из которых определяет смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="34c93-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34c93-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="34c93-112">Remarks</span></span>  
 <span data-ttu-id="34c93-113">Профилировщик часто вставляет операторы в исходном коде метода, позволяющие инструментировать этот метод (например, уведомлять о достижении заданной строки исходного).</span><span class="sxs-lookup"><span data-stu-id="34c93-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="34c93-114">`SetILInstrumentedCodeMap`позволяет профилировщику сопоставление исходной инструкции MSIL в новые расположения.</span><span class="sxs-lookup"><span data-stu-id="34c93-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="34c93-115">Можно использовать профилировщик [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) исходное смещение MSIL для заданного смещения собственного метода.</span><span class="sxs-lookup"><span data-stu-id="34c93-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="34c93-116">Отладчик будет предполагать, что каждое старое смещение ссылается на смещение в пределах исходного, неизмененного MSIL-код, и что каждое новое смещение ссылается на смещение MSIL в новом инструментированном коде.</span><span class="sxs-lookup"><span data-stu-id="34c93-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="34c93-117">Карты должны быть отсортированы в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="34c93-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="34c93-118">Для правильной работы из пошаговой отладки, придерживайтесь следующих правил:</span><span class="sxs-lookup"><span data-stu-id="34c93-118">For stepping to work properly, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="34c93-119">Не меняйте порядок инструментированный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="34c93-119">Do not reorder instrumented MSIL code.</span></span>  
  
-   <span data-ttu-id="34c93-120">Не удаляйте исходный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="34c93-120">Do not remove the original MSIL code.</span></span>  
  
-   <span data-ttu-id="34c93-121">Включить записи для всех точек следования из файла базы данных (PDB) программы на карте.</span><span class="sxs-lookup"><span data-stu-id="34c93-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="34c93-122">Карты не выполнять интерполяцию, отсутствующие записи.</span><span class="sxs-lookup"><span data-stu-id="34c93-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="34c93-123">Таким образом будет получено следующее сопоставление:</span><span class="sxs-lookup"><span data-stu-id="34c93-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="34c93-124">(0 старое, 0 новое)</span><span class="sxs-lookup"><span data-stu-id="34c93-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="34c93-125">(5 старого, 10 новых)</span><span class="sxs-lookup"><span data-stu-id="34c93-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="34c93-126">(9 старого, 20 новой)</span><span class="sxs-lookup"><span data-stu-id="34c93-126">(9 old, 20 new)</span></span>  
  
    -   <span data-ttu-id="34c93-127">Старое смещение 0, 1, 2, 3 или 4 будет сопоставлено новому смещению 0.</span><span class="sxs-lookup"><span data-stu-id="34c93-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    -   <span data-ttu-id="34c93-128">Старое смещение 5, 6, 7 или 8 будет сопоставлено новому смещению 10.</span><span class="sxs-lookup"><span data-stu-id="34c93-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    -   <span data-ttu-id="34c93-129">Старое смещение 9 или более поздней версии будут сопоставлены новому смещению 20.</span><span class="sxs-lookup"><span data-stu-id="34c93-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    -   <span data-ttu-id="34c93-130">Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлено старому смещению 0.</span><span class="sxs-lookup"><span data-stu-id="34c93-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    -   <span data-ttu-id="34c93-131">Новый смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет сопоставлено старому смещению 5.</span><span class="sxs-lookup"><span data-stu-id="34c93-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    -   <span data-ttu-id="34c93-132">Новое смещение 20 или выше будет сопоставлено старому смещению 9.</span><span class="sxs-lookup"><span data-stu-id="34c93-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34c93-133">Требования</span><span class="sxs-lookup"><span data-stu-id="34c93-133">Requirements</span></span>  
 <span data-ttu-id="34c93-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34c93-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34c93-135">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34c93-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34c93-136">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34c93-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34c93-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34c93-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c93-138">См. также</span><span class="sxs-lookup"><span data-stu-id="34c93-138">See Also</span></span>  
 [<span data-ttu-id="34c93-139">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="34c93-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
