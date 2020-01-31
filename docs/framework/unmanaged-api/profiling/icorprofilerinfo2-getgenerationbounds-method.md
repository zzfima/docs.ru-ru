---
title: Метод ICorProfilerInfo2::GetGenerationBounds
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
ms.openlocfilehash: 3cdc185408576f5679daacef4dde438d66e490ff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862754"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="0b41c-102">Метод ICorProfilerInfo2::GetGenerationBounds</span><span class="sxs-lookup"><span data-stu-id="0b41c-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="0b41c-103">Получает области памяти, которые являются сегментами кучи, составляющими разные поколения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0b41c-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b41c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b41c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b41c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b41c-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="0b41c-106">[in] Количество элементов, выделенных вызывающим объектом для массива `ranges`.</span><span class="sxs-lookup"><span data-stu-id="0b41c-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="0b41c-107">[out] Указатель на целое число, задающее общее число диапазонов, некоторые или все из которых будут возвращены в массиве `ranges`.</span><span class="sxs-lookup"><span data-stu-id="0b41c-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="0b41c-108">заполняет Массив структур [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , каждый из которых описывает диапазон (т. е. блок) памяти в поколении, который является сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="0b41c-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b41c-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="0b41c-109">Remarks</span></span>  
 <span data-ttu-id="0b41c-110">Метод `GetGenerationBounds` может быть вызван из любого обратного вызова профилировщика при условии, что в этот момент не выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="0b41c-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="0b41c-111">Большинство смещений поколений происходит во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0b41c-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="0b41c-112">Поколения могут увеличиваться между сборками мусора, но обычно не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="0b41c-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="0b41c-113">Таким образом, наиболее интересные места вызова метода `GetGenerationBounds` — `ICorProfilerCallback2::GarbageCollectionStarted` и `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="0b41c-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="0b41c-114">При запуске программы некоторые объекты выделяются самой средой (CLR), обычно в поколениях 3 и 0.</span><span class="sxs-lookup"><span data-stu-id="0b41c-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="0b41c-115">Таким образом, к моменту начала выполнения управляемого кода эти поколения уже будут содержать объекты.</span><span class="sxs-lookup"><span data-stu-id="0b41c-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="0b41c-116">Поколения 1 и 2 обычно оказываются пустыми, разве что кроме фиктивных объектов, созданных сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="0b41c-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="0b41c-117">(Размер фиктивных объектов составляет 12 байт в 32-разрядных реализациях CLR; размер больше в 64-разрядных реализациях.) Вы также можете увидеть диапазоны поколения 2, которые находятся внутри модулей, созданных генератором образов в машинном кодах (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="0b41c-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="0b41c-118">В этом случае объекты в поколении 2 являются *замороженными объектами*, которые выделяются при запуске Ngen. exe, а не сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="0b41c-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="0b41c-119">Эта функция использует буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="0b41c-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b41c-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0b41c-120">Requirements</span></span>  
 <span data-ttu-id="0b41c-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b41c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b41c-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b41c-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b41c-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b41c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b41c-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b41c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b41c-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b41c-125">See also</span></span>

- [<span data-ttu-id="0b41c-126">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0b41c-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="0b41c-127">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="0b41c-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="0b41c-128">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="0b41c-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0b41c-129">Профилирование</span><span class="sxs-lookup"><span data-stu-id="0b41c-129">Profiling</span></span>](index.md)
