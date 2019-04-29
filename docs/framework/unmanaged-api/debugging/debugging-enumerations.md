---
title: Перечисления отладки
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5edd6dfb3dac05ce4614c43949f2ec4c19b5f742
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698516"
---
# <a name="debugging-enumerations"></a><span data-ttu-id="8b75c-102">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="8b75c-102">Debugging Enumerations</span></span>
<span data-ttu-id="8b75c-103">В этом разделе описываются неуправляемые перечисления, которые использует API отладки.</span><span class="sxs-lookup"><span data-stu-id="8b75c-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b75c-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8b75c-104">In This Section</span></span>  
 [<span data-ttu-id="8b75c-105">Перечисление CLR_DEBUGGING_PROCESS_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8b75c-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="8b75c-106">Предоставляет значения, используемые [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8b75c-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="8b75c-107">Перечисление CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="8b75c-107">CLRDataEnumMemoryFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="8b75c-108">Указывает области памяти вызов [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) должен включать метод.</span><span class="sxs-lookup"><span data-stu-id="8b75c-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="8b75c-109">Перечисление COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="8b75c-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="8b75c-110">Идентифицирует тип процесса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8b75c-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="8b75c-111">Перечисление CorDebugBlockingReason</span><span class="sxs-lookup"><span data-stu-id="8b75c-111">CorDebugBlockingReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="8b75c-112">Указывает возможные причины блокировки потока на данном объекте.</span><span class="sxs-lookup"><span data-stu-id="8b75c-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="8b75c-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="8b75c-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="8b75c-114">Указывает причину или причины запуска цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8b75c-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="8b75c-115">Перечисление CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="8b75c-115">CorDebugCodeInvokeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="8b75c-116">Описывает, каким образом экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="8b75c-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="8b75c-117">Перечисление CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="8b75c-117">CorDebugCodeInvokePurpose Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="8b75c-118">Описывает, почему экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="8b75c-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="8b75c-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="8b75c-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="8b75c-120">Предоставляет дополнительные параметры отладки, которые могут использоваться в вызове [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8b75c-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="8b75c-121">Перечисление CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="8b75c-121">CorDebugDebugEventKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="8b75c-122">Указывает тип события, сведения о котором декодируется [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8b75c-122">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="8b75c-123">Перечисление CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="8b75c-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="8b75c-124">Предоставляет дополнительную информацию о событиях отладки на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="8b75c-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="8b75c-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="8b75c-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="8b75c-126">Указывает тип обратного вызова, состоящее из [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) событий.</span><span class="sxs-lookup"><span data-stu-id="8b75c-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="8b75c-127">Перечисление CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="8b75c-127">CorDebugExceptionFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="8b75c-128">Предоставляет дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="8b75c-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="8b75c-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="8b75c-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="8b75c-130">Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="8b75c-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="8b75c-131">Перечисление CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="8b75c-131">CorDebugGCType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 <span data-ttu-id="8b75c-132">Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.</span><span class="sxs-lookup"><span data-stu-id="8b75c-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="8b75c-133">Перечисление CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="8b75c-133">CorDebugGenerationTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="8b75c-134">Указывает на создание области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="8b75c-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="8b75c-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="8b75c-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="8b75c-136">Указывает тип обработки.</span><span class="sxs-lookup"><span data-stu-id="8b75c-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="8b75c-137">Перечисление CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="8b75c-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="8b75c-138">Указывает, соответствует ли определенный диапазон машинных инструкций специальной области кода.</span><span class="sxs-lookup"><span data-stu-id="8b75c-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="8b75c-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="8b75c-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="8b75c-140">Указывает типы кода, который может быть пошагово выполнен.</span><span class="sxs-lookup"><span data-stu-id="8b75c-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="8b75c-141">Перечисление CorDebugInterfaceVersion</span><span class="sxs-lookup"><span data-stu-id="8b75c-141">CorDebugInterfaceVersion Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="8b75c-142">Указывает либо версию платформы .NET Framework, либо версию платформы .NET Framework, в которой был представлен интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8b75c-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="8b75c-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="8b75c-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="8b75c-144">Указывает тип кадра стека.</span><span class="sxs-lookup"><span data-stu-id="8b75c-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="8b75c-145">Перечисление CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="8b75c-145">CorDebugJITCompilerFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="8b75c-146">Содержит значения, которые влияют на поведение управляемого JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="8b75c-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="8b75c-147">Перечисление CorDebugJITCompilerFlagsDeprecated</span><span class="sxs-lookup"><span data-stu-id="8b75c-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="8b75c-148">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="8b75c-148">Obsolete.</span></span> <span data-ttu-id="8b75c-149">Используйте `CORDEBUG_JIT_DEFAULT` членом [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисления вместо этого.</span><span class="sxs-lookup"><span data-stu-id="8b75c-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="8b75c-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="8b75c-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="8b75c-151">Предоставляет сведения о том, как было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="8b75c-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="8b75c-152">Перечисление CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="8b75c-152">CorDebugMDAFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="8b75c-153">Указывает состояние потока, по которому был вызван помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8b75c-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="8b75c-154">Перечисление CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="8b75c-154">CorDebugNGenPolicy Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="8b75c-155">Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="8b75c-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="8b75c-156">Перечисление CorDebugPlatform</span><span class="sxs-lookup"><span data-stu-id="8b75c-156">CorDebugPlatform Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 <span data-ttu-id="8b75c-157">Предоставляет значения целевой платформы, используемые [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8b75c-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="8b75c-158">Перечисление CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="8b75c-158">CorDebugRecordFormat Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="8b75c-159">Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.</span><span class="sxs-lookup"><span data-stu-id="8b75c-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="8b75c-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="8b75c-160">CorDebugRegister</span></span>  
 <span data-ttu-id="8b75c-161">Указывает регистры, связанные с данной архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="8b75c-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="8b75c-162">Перечисление CorDebugSetContextFlag</span><span class="sxs-lookup"><span data-stu-id="8b75c-162">CorDebugSetContextFlag Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="8b75c-163">Указывает происхождение контекста: взят из активного (или листового) кадра в стеке или был вычислен в результате освобождения другого кадра.</span><span class="sxs-lookup"><span data-stu-id="8b75c-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="8b75c-164">Перечисление CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="8b75c-164">CorDebugStateChange Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 <span data-ttu-id="8b75c-165">Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.</span><span class="sxs-lookup"><span data-stu-id="8b75c-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="8b75c-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="8b75c-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="8b75c-167">Указывает результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="8b75c-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="8b75c-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="8b75c-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="8b75c-169">Указывает состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="8b75c-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="8b75c-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="8b75c-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="8b75c-171">Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.</span><span class="sxs-lookup"><span data-stu-id="8b75c-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="8b75c-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="8b75c-172">CorDebugUserState</span></span>  
 <span data-ttu-id="8b75c-173">Указывает состояние пользователя потока.</span><span class="sxs-lookup"><span data-stu-id="8b75c-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="8b75c-174">Перечисление CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="8b75c-174">CorGCReferenceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 <span data-ttu-id="8b75c-175">Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="8b75c-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="8b75c-176">Перечисление ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="8b75c-176">ILCodeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 <span data-ttu-id="8b75c-177">Предоставляет значения, которые указывают, может ли отладчик получить доступ к локальным переменным или коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8b75c-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="8b75c-178">Перечисление LoggingLevelEnum</span><span class="sxs-lookup"><span data-stu-id="8b75c-178">LoggingLevelEnum Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 <span data-ttu-id="8b75c-179">Указывает уровень важности описательного сообщения, записанного в журнале событий при регистрации события управляемым потоком.</span><span class="sxs-lookup"><span data-stu-id="8b75c-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="8b75c-180">Перечисление LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="8b75c-180">LogSwitchCallReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 <span data-ttu-id="8b75c-181">Указывает операцию, выполненную на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="8b75c-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="8b75c-182">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="8b75c-182">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 <span data-ttu-id="8b75c-183">Указывает тип собственного расположение переменной.</span><span class="sxs-lookup"><span data-stu-id="8b75c-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="8b75c-184">Перечисление WriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="8b75c-184">WriteableMetadataUpdateMode Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="8b75c-185">Предоставляет значения, указывающие, будут ли видны в отладчике обновления копии метаданных в памяти.</span><span class="sxs-lookup"><span data-stu-id="8b75c-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span> 

 <span data-ttu-id="8b75c-186">[Перечисление ClrDataSourceType](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) предоставляет значения, которые используются в структуре CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="8b75c-186">[ClrDataSourceType Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8b75c-187">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8b75c-187">Related Sections</span></span>  
 [<span data-ttu-id="8b75c-188">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="8b75c-188">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="8b75c-189">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8b75c-189">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="8b75c-190">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="8b75c-190">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="8b75c-191">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="8b75c-191">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
