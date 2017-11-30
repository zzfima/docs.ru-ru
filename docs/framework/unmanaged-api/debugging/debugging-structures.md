---
title: "Структуры отладки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0293a20f5f735dd38b1d167ebc5057f645fa011a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-structures"></a><span data-ttu-id="1d495-102">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="1d495-102">Debugging Structures</span></span>
<span data-ttu-id="1d495-103">В этом разделе описаны неуправляемые структуры, которые использует API отладки.</span><span class="sxs-lookup"><span data-stu-id="1d495-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d495-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="1d495-104">In This Section</span></span>  
 [<span data-ttu-id="1d495-105">Clr_debugging_version-структура</span><span class="sxs-lookup"><span data-stu-id="1d495-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="1d495-106">Определяет версию продукта среды CLR, предназначенную для отладки.</span><span class="sxs-lookup"><span data-stu-id="1d495-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="1d495-107">CodeChunkInfo Structure1</span><span class="sxs-lookup"><span data-stu-id="1d495-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="1d495-108">Представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="1d495-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="1d495-109">Структура CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="1d495-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="1d495-110">Определяет объект, блокирующий поток, и причину блокировки потока.</span><span class="sxs-lookup"><span data-stu-id="1d495-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="1d495-111">Структура CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="1d495-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="1d495-112">Представляет предложение обработки исключений для данного фрагмента кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="1d495-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="1d495-113">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="1d495-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="1d495-114">Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="1d495-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="1d495-115">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="1d495-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="1d495-116">Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] с соответствующим [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="1d495-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="1d495-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="1d495-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="1d495-118">Содержит сведения о функциях, которые в данный момент активны в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="1d495-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="1d495-119">Структура COR_ARRAY_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="1d495-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="1d495-120">Предоставляет сведения о расположении объекта массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="1d495-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="1d495-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="1d495-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="1d495-122">Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="1d495-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="1d495-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="1d495-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="1d495-124">Содержит сведения о смещении для диапазона кода.</span><span class="sxs-lookup"><span data-stu-id="1d495-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="1d495-125">Структура COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="1d495-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="1d495-126">Предоставляет сведения о поле в объекте.</span><span class="sxs-lookup"><span data-stu-id="1d495-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="1d495-127">Структура COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="1d495-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="1d495-128">Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="1d495-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="1d495-129">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="1d495-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="1d495-130">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="1d495-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="1d495-131">Структура COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="1d495-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="1d495-132">Предоставляет сведения об объекте, находящемся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="1d495-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="1d495-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="1d495-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="1d495-134">Указывает изменения в относительном смещении функции.</span><span class="sxs-lookup"><span data-stu-id="1d495-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="1d495-135">Структура COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="1d495-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="1d495-136">Содержит сведения об области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="1d495-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="1d495-137">Структура COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="1d495-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="1d495-138">Содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="1d495-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="1d495-139">Структура COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="1d495-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="1d495-140">Предоставляет сведения о расположении объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="1d495-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="1d495-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="1d495-141">COR_VERSION</span></span>  
 <span data-ttu-id="1d495-142">Содержит стандартный номер версии среды CLR, состоящий из четырех частей.</span><span class="sxs-lookup"><span data-stu-id="1d495-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="1d495-143">Stacktrace_simplecontext-структура</span><span class="sxs-lookup"><span data-stu-id="1d495-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="1d495-144">Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="1d495-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1d495-145">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="1d495-145">Related Sections</span></span>  
 [<span data-ttu-id="1d495-146">Компонентные классы отладки</span><span class="sxs-lookup"><span data-stu-id="1d495-146">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="1d495-147">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1d495-147">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="1d495-148">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="1d495-148">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="1d495-149">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="1d495-149">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="1d495-150">Отладка</span><span class="sxs-lookup"><span data-stu-id="1d495-150">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
