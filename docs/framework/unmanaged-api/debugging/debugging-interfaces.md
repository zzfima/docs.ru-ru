---
title: Интерфейсы отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b6d00d17615769a5d03d58e0eda5af62ca58368
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415966"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="a239a-102">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a239a-102">Debugging Interfaces</span></span>
<span data-ttu-id="a239a-103">В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="a239a-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a239a-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a239a-104">In This Section</span></span>  
 [<span data-ttu-id="a239a-105">Интерфейс ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="a239a-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="a239a-106">Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.</span><span class="sxs-lookup"><span data-stu-id="a239a-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="a239a-107">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="a239a-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="a239a-108">Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="a239a-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="a239a-109">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="a239a-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="a239a-110">Предоставляет методы для взаимодействия с целевым процессом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a239a-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="a239a-111">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="a239a-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="a239a-112">Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="a239a-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="a239a-113">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="a239a-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="a239a-114">Подкласс [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , обеспечивающий доступ к сведениям об исключении.</span><span class="sxs-lookup"><span data-stu-id="a239a-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="a239a-115">Интерфейс ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="a239a-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="a239a-116">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="a239a-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="a239a-117">Интерфейс ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="a239a-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="a239a-118">Включает в себя [метод ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) метод, получающий интерфейс обратного вызова, который позволяет библиотеки отладки конкретной версии среды выполнения, находить и загружать по мере необходимости поставщика библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a239a-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="a239a-119">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="a239a-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="a239a-120">Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="a239a-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="a239a-121">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a239a-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="a239a-122">Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="a239a-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="a239a-123">Интерфейс1 ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="a239a-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="a239a-124">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="a239a-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="a239a-125">Интерфейс1 ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="a239a-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="a239a-126">Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef.</span><span class="sxs-lookup"><span data-stu-id="a239a-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="a239a-127">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="a239a-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="a239a-128">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="a239a-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="a239a-129">Предоставляет методы для работы с типами [!INCLUDE[wrt](../../../../includes/wrt-md.md)] в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="a239a-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="a239a-130">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="a239a-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="a239a-131">Интерфейс ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="a239a-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="a239a-132">Логически расширяет [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) интерфейса для получения управляемого объекта из вызываемой оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="a239a-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="a239a-133">Интерфейс1 ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="a239a-134">Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="a239a-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="a239a-135">Интерфейс1 ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="a239a-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="a239a-136">Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="a239a-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="a239a-137">Интерфейс1 ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="a239a-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="a239a-138">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="a239a-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="a239a-139">Интерфейс1 ICorDebugAssembly2</span><span class="sxs-lookup"><span data-stu-id="a239a-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="a239a-140">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="a239a-140">Represents an assembly.</span></span> <span data-ttu-id="a239a-141">Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="a239a-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="a239a-142">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="a239a-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="a239a-143">Логически расширяет [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) интерфейса для обеспечения поддержки контейнерных сборок и их вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="a239a-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="a239a-144">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-145">Интерфейс1 ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="a239a-146">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="a239a-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-147">Интерфейс ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="a239a-148">Предоставляет перечислитель для списка [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="a239a-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="a239a-149">Интерфейс1 ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="a239a-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="a239a-150">Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.</span><span class="sxs-lookup"><span data-stu-id="a239a-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="a239a-151">Интерфейс1 ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a239a-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="a239a-152">Представляет точку останова в функции или контрольную точку для значения.</span><span class="sxs-lookup"><span data-stu-id="a239a-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="a239a-153">Интерфейс1 ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="a239a-154">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="a239a-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-155">Интерфейс1 ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="a239a-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="a239a-156">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="a239a-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="a239a-157">Интерфейс1 ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="a239a-158">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="a239a-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-159">Интерфейс1 ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="a239a-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="a239a-160">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="a239a-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="a239a-161">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="a239a-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="a239a-162">Интерфейс1 ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="a239a-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="a239a-163">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="a239a-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="a239a-164">Этот интерфейс расширяет интерфейс `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="a239a-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="a239a-165">Интерфейс1 ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="a239a-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="a239a-166">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="a239a-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="a239a-167">Интерфейс1 ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="a239a-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="a239a-168">Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="a239a-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="a239a-169">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="a239a-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="a239a-170">Предоставляет метод, который расширяет [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) и [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="a239a-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="a239a-171">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="a239a-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="a239a-172">Предоставляет метод, который позволяет отладчику выполнить перечисление локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="a239a-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="a239a-173">Интерфейс1 ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="a239a-174">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="a239a-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-175">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="a239a-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="a239a-176">Предоставляет методы для получения кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a239a-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="a239a-177">Интерфейс1 ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="a239a-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="a239a-178">Представляет объект контекста.</span><span class="sxs-lookup"><span data-stu-id="a239a-178">Represents a context object.</span></span> <span data-ttu-id="a239a-179">Этот интерфейс еще не реализован.</span><span class="sxs-lookup"><span data-stu-id="a239a-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="a239a-180">Интерфейс1 ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="a239a-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="a239a-181">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="a239a-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="a239a-182">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="a239a-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="a239a-183">Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="a239a-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="a239a-184">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="a239a-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="a239a-185">Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a239a-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="a239a-186">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-187">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="a239a-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="a239a-188">Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для предоставления сведений о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="a239a-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="a239a-189">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-190">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a239a-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="a239a-191">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="a239a-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="a239a-192">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-193">Интерфейс ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="a239a-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="a239a-194">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="a239a-194">Obsolete.</span></span> <span data-ttu-id="a239a-195">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a239a-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="a239a-196">Интерфейс1 ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="a239a-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="a239a-197">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="a239a-197">Obsolete.</span></span> <span data-ttu-id="a239a-198">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a239a-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="a239a-199">Интерфейс1 ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="a239a-200">Служит абстрактным базовым интерфейсом для перечислителей отладки.</span><span class="sxs-lookup"><span data-stu-id="a239a-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="a239a-201">Интерфейс1 ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="a239a-202">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="a239a-202">Obsolete.</span></span> <span data-ttu-id="a239a-203">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a239a-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="a239a-204">Интерфейс1 ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="a239a-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="a239a-205">Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="a239a-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="a239a-206">Интерфейс1 ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="a239a-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="a239a-207">Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="a239a-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="a239a-208">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a239a-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="a239a-209">Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий исключения.</span><span class="sxs-lookup"><span data-stu-id="a239a-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="a239a-210">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-211">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="a239a-212">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="a239a-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="a239a-213">Интерфейс ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="a239a-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="a239a-214">Расширяет [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) интерфейс, чтобы предоставить сведения о трассировке стека из управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="a239a-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="a239a-215">Интерфейс1ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="a239a-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="a239a-216">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="a239a-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="a239a-217">Интерфейс1 ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="a239a-218">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="a239a-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-219">Интерфейс1 ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="a239a-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="a239a-220">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="a239a-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="a239a-221">Интерфейс1 ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="a239a-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="a239a-222">Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="a239a-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="a239a-223">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="a239a-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="a239a-224">Логически расширяет [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) интерфейс для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="a239a-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="a239a-225">Интерфейс1 ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a239a-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="a239a-226">Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="a239a-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="a239a-227">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="a239a-228">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="a239a-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="a239a-229">Интерфейс1 ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="a239a-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="a239a-230">Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="a239a-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="a239a-231">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="a239a-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="a239a-232">Интерфейс ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="a239a-233">Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="a239a-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="a239a-234">Интерфейс1 ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="a239a-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="a239a-235">Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a239a-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="a239a-236">Интерфейс ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="a239a-237">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="a239a-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="a239a-238">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="a239a-239">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="a239a-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="a239a-240">Интерфейс1 ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="a239a-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="a239a-241">Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a239a-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="a239a-242">Интерфейс1 ICorDebugHeapValue2</span><span class="sxs-lookup"><span data-stu-id="a239a-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="a239a-243">Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a239a-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="a239a-244">Интерфейс ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="a239a-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="a239a-245">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="a239a-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="a239a-246">Интерфейс ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="a239a-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="a239a-247">Представляет сегмент кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="a239a-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="a239a-248">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="a239a-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="a239a-249">Логически расширяет [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) интерфейс, чтобы предоставить методы, возвращающие маркер для подписи локальной переменной функции и сопоставлены инструментированного профилировщиком промежуточного языка (IL) смещений в исходный метод IL смещения.</span><span class="sxs-lookup"><span data-stu-id="a239a-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="a239a-250">Интерфейс1 ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="a239a-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="a239a-251">Предоставляет кадр стека кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="a239a-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="a239a-252">Интерфейс1 ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="a239a-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="a239a-253">Логическое расширение интерфейса `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="a239a-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="a239a-254">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="a239a-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="a239a-255">Предоставляет метод, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="a239a-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="a239a-256">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="a239a-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="a239a-257">Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="a239a-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="a239a-258">Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="a239a-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="a239a-259">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a239a-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="a239a-260">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a239a-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="a239a-261">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-262">Интерфейс1 ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="a239a-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="a239a-263">Задает типы кадров для отладчика.</span><span class="sxs-lookup"><span data-stu-id="a239a-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="a239a-264">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="a239a-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="a239a-265">Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="a239a-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="a239a-266">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="a239a-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="a239a-267">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="a239a-267">Provides information about a loaded module.</span></span> <span data-ttu-id="a239a-268">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-269">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="a239a-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="a239a-270">Предоставляет методы для обработки обратных вызовов отладчика.</span><span class="sxs-lookup"><span data-stu-id="a239a-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="a239a-271">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="a239a-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="a239a-272">Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="a239a-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="a239a-273">Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="a239a-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="a239a-274">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="a239a-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="a239a-275">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="a239a-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="a239a-276">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="a239a-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="a239a-277">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="a239a-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="a239a-278">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="a239a-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="a239a-279">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="a239a-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="a239a-280">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-281">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="a239a-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="a239a-282">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="a239a-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="a239a-283">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-284">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="a239a-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="a239a-285">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="a239a-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="a239a-286">Интерфейс1 ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="a239a-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="a239a-287">Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="a239a-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="a239a-288">Интерфейс1 ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="a239a-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="a239a-289">Служит логическим расширением интерфейса `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="a239a-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="a239a-290">Интерфейс ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="a239a-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="a239a-291">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="a239a-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="a239a-292">Интерфейс1 ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a239a-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="a239a-293">Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.</span><span class="sxs-lookup"><span data-stu-id="a239a-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="a239a-294">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a239a-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="a239a-295">Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="a239a-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="a239a-296">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-297">Интерфейс1 ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="a239a-298">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="a239a-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-299">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="a239a-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="a239a-300">Расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для поддержки целевых объектов изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="a239a-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="a239a-301">Интерфейс1 ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="a239a-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="a239a-302">Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.</span><span class="sxs-lookup"><span data-stu-id="a239a-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="a239a-303">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="a239a-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="a239a-304">Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".</span><span class="sxs-lookup"><span data-stu-id="a239a-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="a239a-305">Интерфейс1 ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="a239a-306">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="a239a-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="a239a-307">Интерфейс1 ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="a239a-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="a239a-308">Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.</span><span class="sxs-lookup"><span data-stu-id="a239a-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="a239a-309">Интерфейс1 ICorDebugObjectValue2</span><span class="sxs-lookup"><span data-stu-id="a239a-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="a239a-310">Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.</span><span class="sxs-lookup"><span data-stu-id="a239a-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="a239a-311">Интерфейс1 ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="a239a-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="a239a-312">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="a239a-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="a239a-313">Интерфейс1 ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="a239a-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="a239a-314">Логическое расширение интерфейса `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="a239a-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="a239a-315">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="a239a-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="a239a-316">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="a239a-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="a239a-317">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="a239a-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="a239a-318">Расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) локального интерфейса для поддержки доступа к управляемой куче, для предоставления сведений о сборке мусора управляемых объектов и для определения, загружает ли отладчик образы из приложения кэш образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="a239a-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="a239a-319">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="a239a-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="a239a-320">Логически расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) интерфейс для включения функции, такие как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей.</span><span class="sxs-lookup"><span data-stu-id="a239a-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="a239a-321">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-322">Интерфейс ICorDebugProcess7</span><span class="sxs-lookup"><span data-stu-id="a239a-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="a239a-323">Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="a239a-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="a239a-324">Интерфейс ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="a239a-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="a239a-325">Логически расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) интерфейс, чтобы включить или отключить определенные виды [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) обратных вызовов исключения.</span><span class="sxs-lookup"><span data-stu-id="a239a-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="a239a-326">Интерфейс1 ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="a239a-327">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="a239a-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-328">Интерфейс1 ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="a239a-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="a239a-329">Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="a239a-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="a239a-330">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="a239a-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="a239a-331">Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="a239a-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="a239a-332">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="a239a-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="a239a-333">Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.</span><span class="sxs-lookup"><span data-stu-id="a239a-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="a239a-334">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="a239a-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="a239a-335">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="a239a-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="a239a-336">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="a239a-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="a239a-337">Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="a239a-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="a239a-338">Интерфейс ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="a239a-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="a239a-339">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="a239a-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="a239a-340">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="a239a-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="a239a-341">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="a239a-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="a239a-342">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a239a-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="a239a-343">Представляет сведения отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="a239a-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="a239a-344">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-345">Интерфейс1 ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="a239a-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="a239a-346">Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.</span><span class="sxs-lookup"><span data-stu-id="a239a-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="a239a-347">Интерфейс1 ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="a239a-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="a239a-348">Предоставляет поддержку отладки "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="a239a-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="a239a-349">Интерфейс1 ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="a239a-350">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="a239a-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-351">Интерфейс1 ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="a239a-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="a239a-352">Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.</span><span class="sxs-lookup"><span data-stu-id="a239a-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="a239a-353">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a239a-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="a239a-354">Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="a239a-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="a239a-355">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-356">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="a239a-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="a239a-357">Логически расширяет [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) интерфейс для извлечения дополнительных символов отладки.</span><span class="sxs-lookup"><span data-stu-id="a239a-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="a239a-358">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-359">Интерфейс1 ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="a239a-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="a239a-360">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="a239a-360">Represents a thread in a process.</span></span> <span data-ttu-id="a239a-361">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="a239a-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="a239a-362">Интерфейс1 ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="a239a-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="a239a-363">Служит логическим расширением интерфейса `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="a239a-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="a239a-364">Интерфейс ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="a239a-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="a239a-365">Предоставляет точку входа для [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) и соответствующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="a239a-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="a239a-366">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="a239a-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="a239a-367">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="a239a-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="a239a-368">Интерфейс1 ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="a239a-369">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="a239a-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-370">Интерфейс1 ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="a239a-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="a239a-371">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="a239a-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="a239a-372">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="a239a-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="a239a-373">Интерфейс ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="a239a-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="a239a-374">Расширяет [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) интерфейс для извлечения идентификатора типа базового типа или сложного типа (определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="a239a-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="a239a-375">Интерфейс1 ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="a239a-376">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="a239a-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-377">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="a239a-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="a239a-378">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a239a-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="a239a-379">"ICorDebugValue"</span><span class="sxs-lookup"><span data-stu-id="a239a-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="a239a-380">Представляет значение для записи или чтения в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="a239a-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="a239a-381">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="a239a-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="a239a-382">Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="a239a-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="a239a-383">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="a239a-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="a239a-384">Расширяет интерфейс «ICorDebugValue» и «ICorDebugValue2» для обеспечения поддержки массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="a239a-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="a239a-385">"ICorDebugValueBreakpoint"</span><span class="sxs-lookup"><span data-stu-id="a239a-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="a239a-386">Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="a239a-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="a239a-387">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="a239a-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="a239a-388">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="a239a-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="a239a-389">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="a239a-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="a239a-390">Представляет локальную переменную или аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="a239a-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="a239a-391">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="a239a-392">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="a239a-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="a239a-393">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="a239a-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="a239a-394">Извлекает сведения отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="a239a-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="a239a-395">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-396">Интерфейс ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="a239a-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="a239a-397">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="a239a-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="a239a-398">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="a239a-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="a239a-399">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="a239a-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="a239a-400">Служит универсальным интерфейсом для процессов публикации.</span><span class="sxs-lookup"><span data-stu-id="a239a-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="a239a-401">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="a239a-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="a239a-402">Представляет и предоставляет информацию о домене приложения.</span><span class="sxs-lookup"><span data-stu-id="a239a-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="a239a-403">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="a239a-404">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a239a-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="a239a-405">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="a239a-406">Служит абстрактной базой для перечислителей публикации.</span><span class="sxs-lookup"><span data-stu-id="a239a-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="a239a-407">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="a239a-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="a239a-408">Предоставляет методы, позволяющие получить доступ к сведениям о процессе.</span><span class="sxs-lookup"><span data-stu-id="a239a-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="a239a-409">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="a239a-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="a239a-410">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="a239a-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="a239a-411">[Интерфейс ISOSDacInterface](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md) предоставляет вспомогательные методы для доступа к данным из `SOS`.</span><span class="sxs-lookup"><span data-stu-id="a239a-411">[ISOSDacInterface Interface](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md) Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="a239a-412">[Интерфейс IXCLRDataMethodDefinition](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md) предоставляет методы для запроса на получение сведений об определении метода.</span><span class="sxs-lookup"><span data-stu-id="a239a-412">[IXCLRDataMethodDefinition Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md) Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="a239a-413">[Интерфейс IXCLRDataMethodInstance](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md) предоставляет методы для запроса на получение сведений о экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="a239a-413">[IXCLRDataMethodInstance Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md) Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="a239a-414">[Интерфейс IXCLRDataModule](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md) предоставляет методы для запроса на получение сведений о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="a239a-414">[IXCLRDataModule Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md) Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="a239a-415">[Интерфейс IXCLRDataProcess](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md) предоставляет методы для запроса на получение сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="a239a-415">[IXCLRDataProcess Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md) Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="a239a-416">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a239a-416">Related Sections</span></span>  
 [<span data-ttu-id="a239a-417">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="a239a-417">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="a239a-418">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="a239a-418">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="a239a-419">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="a239a-419">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="a239a-420">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="a239a-420">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
