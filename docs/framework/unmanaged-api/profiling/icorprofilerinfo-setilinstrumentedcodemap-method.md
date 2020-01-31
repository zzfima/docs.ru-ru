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
ms.openlocfilehash: 99e473268fd0d5bb8ce120b97576277949b86508
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869001"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="469f0-102">Метод ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="469f0-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>

<span data-ttu-id="469f0-103">Задает карту кода для указанной функции, используя указанные записи о сопоставлении языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="469f0-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>

> [!NOTE]
> <span data-ttu-id="469f0-104">В .NET Framework версии 2,0 вызов `SetILInstrumentedCodeMap` на `FunctionID`, который представляет универсальную функцию в определенном домене приложения, повлияет на все экземпляры этой функции в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="469f0-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>

## <a name="syntax"></a><span data-ttu-id="469f0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="469f0-105">Syntax</span></span>

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a><span data-ttu-id="469f0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="469f0-106">Parameters</span></span>

`functionId`\
<span data-ttu-id="469f0-107">окне Идентификатор функции, для которой необходимо задать карту кода.</span><span class="sxs-lookup"><span data-stu-id="469f0-107">[in] The ID of the function for which to set the code map.</span></span>

`fStartJit`\
<span data-ttu-id="469f0-108">окне Логическое значение, указывающее, является ли вызов метода `SetILInstrumentedCodeMap` первым для конкретного `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="469f0-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="469f0-109">Задайте для `fStartJit` значение `true` в первом вызове `SetILInstrumentedCodeMap` для заданного `FunctionID`, а затем — `false`.</span><span class="sxs-lookup"><span data-stu-id="469f0-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>

`cILMapEntries`\
<span data-ttu-id="469f0-110">окне Число элементов в массиве `cILMapEntries`.</span><span class="sxs-lookup"><span data-stu-id="469f0-110">[in] The number of elements in the `cILMapEntries` array.</span></span>

`rgILMapEntries`\
<span data-ttu-id="469f0-111">окне Массив структур COR_IL_MAP, каждый из которых задает смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="469f0-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>

## <a name="remarks"></a><span data-ttu-id="469f0-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="469f0-112">Remarks</span></span>

<span data-ttu-id="469f0-113">Профилировщик часто вставляет инструкции в исходном коде метода, чтобы инструментировать этот метод (например, уведомлять о достижении данной строки исходного кода).</span><span class="sxs-lookup"><span data-stu-id="469f0-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="469f0-114">`SetILInstrumentedCodeMap` позволяет профилировщику сопоставлять исходные инструкции MSIL с их новыми расположениями.</span><span class="sxs-lookup"><span data-stu-id="469f0-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="469f0-115">Профилировщик может использовать метод [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) , чтобы получить исходное смещение MSIL для заданного смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="469f0-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>

<span data-ttu-id="469f0-116">Отладчик предполагает, что каждое старое смещение ссылается на смещение MSIL в исходном, неизмененном коде MSIL и что каждое новое смещение ссылается на смещение MSIL в новом, инструментированном коде.</span><span class="sxs-lookup"><span data-stu-id="469f0-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="469f0-117">Карту следует сортировать в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="469f0-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="469f0-118">Чтобы пошаговое выполнение работало правильно, следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="469f0-118">For stepping to work properly, follow these guidelines:</span></span>

- <span data-ttu-id="469f0-119">Не Переупорядочивайте инструментированный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="469f0-119">Do not reorder instrumented MSIL code.</span></span>

- <span data-ttu-id="469f0-120">Не удаляйте исходный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="469f0-120">Do not remove the original MSIL code.</span></span>

- <span data-ttu-id="469f0-121">Включить записи для всех точек следования из файла базы данных программы (PDB) на карте.</span><span class="sxs-lookup"><span data-stu-id="469f0-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="469f0-122">На карте не выполняется интерполяция отсутствующих записей.</span><span class="sxs-lookup"><span data-stu-id="469f0-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="469f0-123">Итак, учитывая следующую карту:</span><span class="sxs-lookup"><span data-stu-id="469f0-123">So, given the following map:</span></span>

  <span data-ttu-id="469f0-124">(0 старых, 0 новых)</span><span class="sxs-lookup"><span data-stu-id="469f0-124">(0 old, 0 new)</span></span>

  <span data-ttu-id="469f0-125">(5 старых, 10 новых)</span><span class="sxs-lookup"><span data-stu-id="469f0-125">(5 old, 10 new)</span></span>

  <span data-ttu-id="469f0-126">(9 старых, 20 новых)</span><span class="sxs-lookup"><span data-stu-id="469f0-126">(9 old, 20 new)</span></span>

  - <span data-ttu-id="469f0-127">Старое смещение 0, 1, 2, 3 или 4 будет сопоставлено с новым смещением 0.</span><span class="sxs-lookup"><span data-stu-id="469f0-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>

  - <span data-ttu-id="469f0-128">Старое смещение 5, 6, 7 или 8 будет сопоставлено с новым смещением 10.</span><span class="sxs-lookup"><span data-stu-id="469f0-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>

  - <span data-ttu-id="469f0-129">Старое смещение 9 или выше будет сопоставлено с новым смещением 20.</span><span class="sxs-lookup"><span data-stu-id="469f0-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>

  - <span data-ttu-id="469f0-130">Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлено со старым смещением 0.</span><span class="sxs-lookup"><span data-stu-id="469f0-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>

  - <span data-ttu-id="469f0-131">Новое смещение, равное 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19, будет сопоставлено со старым смещением 5.</span><span class="sxs-lookup"><span data-stu-id="469f0-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>

  - <span data-ttu-id="469f0-132">Новое смещение, равное 20 или выше, будет сопоставлено старому смещению 9.</span><span class="sxs-lookup"><span data-stu-id="469f0-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>

<span data-ttu-id="469f0-133">В .NET Framework 3,5 и предыдущих версиях вы выделяете массив `rgILMapEntries`, вызывая метод [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) .</span><span class="sxs-lookup"><span data-stu-id="469f0-133">In the .NET Framework 3.5 and previous versions, you allocate the `rgILMapEntries` array by calling the [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) method.</span></span> <span data-ttu-id="469f0-134">Поскольку среда выполнения получает владение этой памятью, профилировщик не должен пытаться освободить его.</span><span class="sxs-lookup"><span data-stu-id="469f0-134">Because the runtime takes ownership of this memory, the profiler should not attempt to free it.</span></span>

## <a name="requirements"></a><span data-ttu-id="469f0-135">Требования</span><span class="sxs-lookup"><span data-stu-id="469f0-135">Requirements</span></span>

<span data-ttu-id="469f0-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="469f0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="469f0-137">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="469f0-137">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="469f0-138">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="469f0-138">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="469f0-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="469f0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="469f0-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="469f0-140">See also</span></span>

- [<span data-ttu-id="469f0-141">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="469f0-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
