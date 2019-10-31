---
title: Структуры отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: 05a321d5025f03d6a0378b462178bf06c0291f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123031"
---
# <a name="debugging-structures"></a><span data-ttu-id="6fd32-102">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="6fd32-102">Debugging Structures</span></span>

<span data-ttu-id="6fd32-103">В этом разделе описаны неуправляемые структуры, которые использует API отладки.</span><span class="sxs-lookup"><span data-stu-id="6fd32-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6fd32-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="6fd32-104">In This Section</span></span>
 <span data-ttu-id="6fd32-105">[Структура CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Определяет диапазон адресов.</span><span class="sxs-lookup"><span data-stu-id="6fd32-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="6fd32-106">[Структура CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Определяет IL для сопоставления адресов</span><span class="sxs-lookup"><span data-stu-id="6fd32-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="6fd32-107">[Структура CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Определяет версию продукта среды CLR для целей отладки.</span><span class="sxs-lookup"><span data-stu-id="6fd32-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="6fd32-108">[Структура кодечункинфо](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Представляет отдельный фрагмент кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="6fd32-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="6fd32-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Содержит сведения о функциях, которые в данный момент активны в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="6fd32-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="6fd32-110">[Структура COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Предоставляет сведения о макете объекта массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="6fd32-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="6fd32-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Содержит смещения, используемые для преобразования кода MSIL в машинный код.</span><span class="sxs-lookup"><span data-stu-id="6fd32-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="6fd32-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="6fd32-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="6fd32-113">[Структура COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Предоставляет сведения о поле в объекте.</span><span class="sxs-lookup"><span data-stu-id="6fd32-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="6fd32-114">[Структура COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Содержит сведения об объекте, который должен быть собран в мусор.</span><span class="sxs-lookup"><span data-stu-id="6fd32-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="6fd32-115">[Структура COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Содержит общие сведения о куче сборки мусора, в том числе о том, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="6fd32-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="6fd32-116">[Структура COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Предоставляет сведения об объекте в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="6fd32-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="6fd32-117">[COR_IL_MAP](cor-il-map-structure.md) Задает изменения в относительном смещении функции.</span><span class="sxs-lookup"><span data-stu-id="6fd32-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="6fd32-118">[Структура COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Содержит сведения о области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="6fd32-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="6fd32-119">[Структура COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="6fd32-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="6fd32-120">[Структура COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Предоставляет сведения о макете объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="6fd32-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="6fd32-121">[COR_VERSION](cor-version-structure.md) Хранит Стандартный номер версии, сообщая из четырех частей, для общеязыковой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6fd32-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="6fd32-122">[Структура CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Определяет объект, который блокирует поток и причину блокировки потока.</span><span class="sxs-lookup"><span data-stu-id="6fd32-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="6fd32-123">[Структура кордебужехклаусе](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Представляет предложение обработки исключений (EH) для заданного фрагмента промежуточного языка (IL).</span><span class="sxs-lookup"><span data-stu-id="6fd32-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="6fd32-124">[Структура кордебужексцептионобжектстаккфраме](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="6fd32-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="6fd32-125">[Структура кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6fd32-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="6fd32-126">[Структура дакпжетмодулеаддресс](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Определяет контейнер для запроса адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="6fd32-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="6fd32-127">[Структура дакпмесоддескдата](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Определяет транспортный буфер для сведений о среде выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="6fd32-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="6fd32-128">[Структура дакпмодуледата](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Определяет транспортный буфер для сведений о среде выполнения модуля.</span><span class="sxs-lookup"><span data-stu-id="6fd32-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="6fd32-129">[Структура дакпрежитдата](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Определяет основные сведения о конкретном инструментированном методе профилирования.</span><span class="sxs-lookup"><span data-stu-id="6fd32-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="6fd32-130">[Структура StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Предоставляет простой контекст, который можно использовать вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="6fd32-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6fd32-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6fd32-131">Related Sections</span></span>

 [<span data-ttu-id="6fd32-132">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="6fd32-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="6fd32-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6fd32-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="6fd32-134">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="6fd32-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="6fd32-135">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="6fd32-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="6fd32-136">Отладка</span><span class="sxs-lookup"><span data-stu-id="6fd32-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
