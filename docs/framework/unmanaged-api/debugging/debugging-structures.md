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
ms.openlocfilehash: 23aa619d666f2e0b9eb67ab4cf8d4f92761865d3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415329"
---
# <a name="debugging-structures"></a><span data-ttu-id="bf321-102">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="bf321-102">Debugging Structures</span></span>
<span data-ttu-id="bf321-103">В этом разделе описаны неуправляемые структуры, которые использует API отладки.</span><span class="sxs-lookup"><span data-stu-id="bf321-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf321-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bf321-104">In This Section</span></span>  
 [<span data-ttu-id="bf321-105">Структура CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="bf321-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="bf321-106">Определяет версию продукта среды CLR, предназначенную для отладки.</span><span class="sxs-lookup"><span data-stu-id="bf321-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="bf321-107">Структура1 CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="bf321-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="bf321-108">Представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="bf321-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="bf321-109">Структура CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="bf321-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="bf321-110">Определяет объект, блокирующий поток, и причину блокировки потока.</span><span class="sxs-lookup"><span data-stu-id="bf321-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="bf321-111">Структура CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="bf321-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="bf321-112">Представляет предложение обработки исключений для данного фрагмента кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="bf321-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="bf321-113">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="bf321-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="bf321-114">Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="bf321-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="bf321-115">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="bf321-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="bf321-116">Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Соответствующим [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="bf321-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="bf321-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="bf321-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="bf321-118">Содержит сведения о функциях, которые в данный момент активны в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="bf321-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="bf321-119">Структура COR_ARRAY_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="bf321-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="bf321-120">Предоставляет сведения о расположении объекта массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="bf321-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="bf321-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="bf321-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="bf321-122">Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="bf321-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="bf321-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="bf321-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="bf321-124">Содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="bf321-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="bf321-125">Структура COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="bf321-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="bf321-126">Предоставляет сведения о поле в объекте.</span><span class="sxs-lookup"><span data-stu-id="bf321-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="bf321-127">Структура COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="bf321-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="bf321-128">Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="bf321-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="bf321-129">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="bf321-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="bf321-130">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="bf321-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="bf321-131">Структура COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="bf321-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="bf321-132">Предоставляет сведения об объекте, находящемся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="bf321-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="bf321-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="bf321-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="bf321-134">Указывает изменения в относительном смещении функции.</span><span class="sxs-lookup"><span data-stu-id="bf321-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="bf321-135">Структура COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="bf321-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="bf321-136">Содержит сведения об области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="bf321-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="bf321-137">Структура COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="bf321-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="bf321-138">Содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="bf321-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="bf321-139">Структура COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="bf321-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="bf321-140">Предоставляет сведения о расположении объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="bf321-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="bf321-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="bf321-141">COR_VERSION</span></span>  
 <span data-ttu-id="bf321-142">Содержит стандартный номер версии среды CLR, состоящий из четырех частей.</span><span class="sxs-lookup"><span data-stu-id="bf321-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="bf321-143">Структура StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="bf321-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="bf321-144">Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="bf321-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

 <span data-ttu-id="bf321-145">[Структура CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) определяет диапазон адресов.</span><span class="sxs-lookup"><span data-stu-id="bf321-145">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>
 
 <span data-ttu-id="bf321-146">[Структура CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) определяет инструкцию IL для сопоставления адресов</span><span class="sxs-lookup"><span data-stu-id="bf321-146">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>
 
 <span data-ttu-id="bf321-147">[Структура DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) определяет контейнер для запроса адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="bf321-147">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

  
## <a name="related-sections"></a><span data-ttu-id="bf321-148">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bf321-148">Related Sections</span></span>  
 [<span data-ttu-id="bf321-149">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="bf321-149">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="bf321-150">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bf321-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="bf321-151">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="bf321-151">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="bf321-152">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="bf321-152">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="bf321-153">Отладка</span><span class="sxs-lookup"><span data-stu-id="bf321-153">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
