---
title: Интерфейс ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: c287b630aee58c6795ef405cc1801149e220fd51
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868425"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="a5195-102">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="a5195-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="a5195-103">Предоставляет методы, используемые профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий и сведениями о запросах.</span><span class="sxs-lookup"><span data-stu-id="a5195-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="a5195-104">.</span><span class="sxs-lookup"><span data-stu-id="a5195-104">.</span></span> <span data-ttu-id="a5195-105">Интерфейс `ICorProfilerInfo4` является расширением других интерфейсов `ICorProfilerInfo`.</span><span class="sxs-lookup"><span data-stu-id="a5195-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="a5195-106">Он предоставляет новые методы для поддержки повторной компиляции JIT, добавленной в .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="a5195-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5195-107">Методы</span><span class="sxs-lookup"><span data-stu-id="a5195-107">Methods</span></span>  
  
|<span data-ttu-id="a5195-108">Метод</span><span class="sxs-lookup"><span data-stu-id="a5195-108">Method</span></span>|<span data-ttu-id="a5195-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a5195-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5195-110">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="a5195-110">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="a5195-111">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы.</span><span class="sxs-lookup"><span data-stu-id="a5195-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="a5195-112">Метод EnumThreads</span><span class="sxs-lookup"><span data-stu-id="a5195-112">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="a5195-113">Возвращает перечислитель, предоставляющий методы для последовательного прохода по коллекции всех управляемых потоков в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="a5195-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="a5195-114">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="a5195-114">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="a5195-115">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="a5195-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="a5195-116">Метод GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="a5195-116">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="a5195-117">Сопоставляет указатель инструкции управляемого кода с JIT-повторно скомпилированной версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="a5195-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="a5195-118">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="a5195-118">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="a5195-119">Возвращает карту из смещений MSIL к собственным смещениям для кода, содержащегося в JIT-повторно скомпилированной версии указанной функции.</span><span class="sxs-lookup"><span data-stu-id="a5195-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="a5195-120">Метод GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="a5195-120">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="a5195-121">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="a5195-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="a5195-122">Метод GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="a5195-122">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="a5195-123">Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены.</span><span class="sxs-lookup"><span data-stu-id="a5195-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="a5195-124">Метод InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="a5195-124">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="a5195-125">Инициализирует текущий поток перед последовательными вызовами API профилировщика в том же потоке, что позволяет избежать взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="a5195-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="a5195-126">Метод RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="a5195-126">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="a5195-127">Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="a5195-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="a5195-128">Метод RequestRevert</span><span class="sxs-lookup"><span data-stu-id="a5195-128">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="a5195-129">Восстанавливает исходные версии всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="a5195-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5195-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="a5195-130">Remarks</span></span>  
 <span data-ttu-id="a5195-131">Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков.</span><span class="sxs-lookup"><span data-stu-id="a5195-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="a5195-132">Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="a5195-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="a5195-133">Список возможных кодов возврата см. в файле CorError.h.</span><span class="sxs-lookup"><span data-stu-id="a5195-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5195-134">Требования</span><span class="sxs-lookup"><span data-stu-id="a5195-134">Requirements</span></span>  
 <span data-ttu-id="a5195-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5195-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5195-136">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5195-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5195-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5195-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5195-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5195-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5195-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5195-139">See also</span></span>

- [<span data-ttu-id="a5195-140">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="a5195-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a5195-141">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a5195-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
