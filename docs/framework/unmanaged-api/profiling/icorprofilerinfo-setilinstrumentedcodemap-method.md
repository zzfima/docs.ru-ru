---
title: Метод ICorProfilerInfo::SetILInstrumentedCodeMap
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc13dc1348a6d397c86b03976c86c3595f749cf6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480069"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="6446d-102">Метод ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="6446d-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="6446d-103">Задает карту кода для заданной функции, используя указанные записи карты Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="6446d-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6446d-104">В .NET Framework версии 2.0, вызвав `SetILInstrumentedCodeMap` на `FunctionID` что представляет универсальный работать в конкретный домен приложения будет влиять на все экземпляры этой функции в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6446d-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6446d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6446d-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6446d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6446d-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="6446d-107">[in] Идентификатор функции, для которого требуется задать карты кода.</span><span class="sxs-lookup"><span data-stu-id="6446d-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="6446d-108">[in] Логическое значение, указывающее ли вызов `SetILInstrumentedCodeMap` метод является первым для какого-либо `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="6446d-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="6446d-109">Задайте `fStartJit` для `true` в первом вызове `SetILInstrumentedCodeMap` для заданного `FunctionID`, а в `false` соответственно.</span><span class="sxs-lookup"><span data-stu-id="6446d-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="6446d-110">[in] Число элементов в `cILMapEntries` массива.</span><span class="sxs-lookup"><span data-stu-id="6446d-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="6446d-111">[in] Массив структур COR_IL_MAP, каждый из которых задает смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="6446d-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6446d-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="6446d-112">Remarks</span></span>  
 <span data-ttu-id="6446d-113">Профилировщик часто вставляет операторы в исходный код метода, позволяющие инструментировать этот метод (например, для уведомления при достижении заданной строки исходного).</span><span class="sxs-lookup"><span data-stu-id="6446d-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="6446d-114">`SetILInstrumentedCodeMap` позволяет профилировщику для сопоставления исходного инструкций MSIL в новые расположения.</span><span class="sxs-lookup"><span data-stu-id="6446d-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="6446d-115">Можно использовать профилировщик [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) метод, чтобы получить исходное смещение MSIL для заданного смещения машинного кода.</span><span class="sxs-lookup"><span data-stu-id="6446d-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="6446d-116">Отладчик предположит, что каждое старое смещение ссылается на смещение в исходном, неизмененном MSIL-код, и что каждое новое смещение ссылается на смещение MSIL в новом коде инструментированной.</span><span class="sxs-lookup"><span data-stu-id="6446d-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="6446d-117">Карты должны быть отсортированы в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="6446d-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="6446d-118">Для начала работы должным образом, придерживайтесь следующих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="6446d-118">For stepping to work properly, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="6446d-119">Не переупорядочивают инструментированный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="6446d-119">Do not reorder instrumented MSIL code.</span></span>  
  
-   <span data-ttu-id="6446d-120">Не удаляйте исходный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="6446d-120">Do not remove the original MSIL code.</span></span>  
  
-   <span data-ttu-id="6446d-121">Включите записи для всех точек следования из файла базы данных (PDB) программы на карте.</span><span class="sxs-lookup"><span data-stu-id="6446d-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="6446d-122">Карты не интерполирует недостающие записи.</span><span class="sxs-lookup"><span data-stu-id="6446d-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="6446d-123">Таким образом Если на следующей карте:</span><span class="sxs-lookup"><span data-stu-id="6446d-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="6446d-124">(0 старое, 0 новое)</span><span class="sxs-lookup"><span data-stu-id="6446d-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="6446d-125">(5 старше 10 новых)</span><span class="sxs-lookup"><span data-stu-id="6446d-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="6446d-126">(9 старый, 20 новых)</span><span class="sxs-lookup"><span data-stu-id="6446d-126">(9 old, 20 new)</span></span>  
  
    -   <span data-ttu-id="6446d-127">Старое смещение 0, 1, 2, 3 или 4 будет сопоставляться новое смещение 0.</span><span class="sxs-lookup"><span data-stu-id="6446d-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    -   <span data-ttu-id="6446d-128">Старое смещение 5, 6, 7 или 8 будет сопоставляться новое смещение 10.</span><span class="sxs-lookup"><span data-stu-id="6446d-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    -   <span data-ttu-id="6446d-129">Старое смещение 9 или более поздней версии будет сопоставляться новое смещение 20.</span><span class="sxs-lookup"><span data-stu-id="6446d-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    -   <span data-ttu-id="6446d-130">Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлен старое смещение 0.</span><span class="sxs-lookup"><span data-stu-id="6446d-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    -   <span data-ttu-id="6446d-131">Новое смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет сопоставлен старое смещение 5.</span><span class="sxs-lookup"><span data-stu-id="6446d-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    -   <span data-ttu-id="6446d-132">Новое смещение 20 или более поздней версии будет сопоставлен старое смещение 9.</span><span class="sxs-lookup"><span data-stu-id="6446d-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6446d-133">Требования</span><span class="sxs-lookup"><span data-stu-id="6446d-133">Requirements</span></span>  
 <span data-ttu-id="6446d-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6446d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6446d-135">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6446d-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6446d-136">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6446d-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6446d-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6446d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6446d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="6446d-138">See also</span></span>
- [<span data-ttu-id="6446d-139">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6446d-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
