---
title: Структуры отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50db519410b9513725c3dc10637421ba8bb37ec
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965232"
---
# <a name="debugging-structures"></a><span data-ttu-id="b9775-102">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="b9775-102">Debugging Structures</span></span>

<span data-ttu-id="b9775-103">В этом разделе описаны неуправляемые структуры, которые использует API отладки.</span><span class="sxs-lookup"><span data-stu-id="b9775-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b9775-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b9775-104">In This Section</span></span>
 <span data-ttu-id="b9775-105">[Структура CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) определяет диапазон адресов.</span><span class="sxs-lookup"><span data-stu-id="b9775-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="b9775-106">[Структура CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) определяет инструкцию IL для сопоставления адресов</span><span class="sxs-lookup"><span data-stu-id="b9775-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="b9775-107">[Структура CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) определяет версию среды выполнения (CLR) для целей отладки.</span><span class="sxs-lookup"><span data-stu-id="b9775-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="b9775-108">[Структура CodeChunkInfo](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="b9775-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="b9775-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) содержит сведения о функциях, которые в настоящее время активны в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="b9775-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="b9775-110">[Структура COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) предоставляет сведения о расположении объекта массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="b9775-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="b9775-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) содержит смещения, которые используются для сопоставления промежуточного языка Майкрософт (MSIL) кода в машинный код.</span><span class="sxs-lookup"><span data-stu-id="b9775-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="b9775-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="b9775-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="b9775-113">[Структура COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) предоставляет сведения о поле в объекте.</span><span class="sxs-lookup"><span data-stu-id="b9775-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="b9775-114">[Структура COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) содержит сведения об объекте, который должен быть сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="b9775-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="b9775-115">[Структура COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) содержит общие сведения о куче для сборки мусора, включая ли он является перечислимым.</span><span class="sxs-lookup"><span data-stu-id="b9775-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="b9775-116">[Структура COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) предоставляет сведения об объекте в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="b9775-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="b9775-117">[COR_IL_MAP](cor-il-map-structure.md) определяет изменения в относительном смещении функции.</span><span class="sxs-lookup"><span data-stu-id="b9775-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="b9775-118">[Структура COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) содержит сведения об области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="b9775-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="b9775-119">[Структура COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="b9775-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="b9775-120">[Структура COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) предоставляет сведения о расположении объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="b9775-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="b9775-121">[COR_VERSION](cor-version-structure.md) хранит номер версии standard из четырех частей среда CLR.</span><span class="sxs-lookup"><span data-stu-id="b9775-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="b9775-122">[Структура CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) определяет объект, который блокирует поток и причину, почему поток блокируется.</span><span class="sxs-lookup"><span data-stu-id="b9775-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="b9775-123">[Структура CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) представляет предложение обработки (EH) исключения для данной части промежуточный язык (IL).</span><span class="sxs-lookup"><span data-stu-id="b9775-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="b9775-124">[Структура CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) представляет сведения о кадре от объекта исключения стека.</span><span class="sxs-lookup"><span data-stu-id="b9775-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="b9775-125">[Структура CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Соответствующим [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="b9775-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="b9775-126">[Структура DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) определяет контейнер для запроса адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="b9775-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="b9775-127">[Структура DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) определяет буфер транспорта сведения среды выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="b9775-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="b9775-128">[Структура DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) определяет буфер транспорта для модуля сведения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b9775-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="b9775-129">[Структура DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) , определяющего основную информацию о данный метод инструментированного профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="b9775-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="b9775-130">[Структура StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) обеспечивает простой контекст, который может использоваться вместо полной `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="b9775-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b9775-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b9775-131">Related Sections</span></span>

 [<span data-ttu-id="b9775-132">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="b9775-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="b9775-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b9775-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="b9775-134">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="b9775-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="b9775-135">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b9775-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="b9775-136">Отладка</span><span class="sxs-lookup"><span data-stu-id="b9775-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
