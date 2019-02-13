---
title: Интерфейсы отладки
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afa4e6cd4e99540030d3a9e151da4bbe711d973a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219832"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="8995e-102">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8995e-102">Debugging Interfaces</span></span>
<span data-ttu-id="8995e-103">В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8995e-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8995e-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8995e-104">In This Section</span></span>  
 <span data-ttu-id="8995e-105">[Интерфейс ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)\\</span></span>
 <span data-ttu-id="8995e-106">Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.</span><span class="sxs-lookup"><span data-stu-id="8995e-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="8995e-107">[Интерфейс ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\\</span></span>
 <span data-ttu-id="8995e-108">Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="8995e-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="8995e-109">[Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="8995e-110">Предоставляет методы для взаимодействия с целевым процессом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8995e-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="8995e-111">[Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-112">Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="8995e-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="8995e-113">[Интерфейс ICLRDataTarget3](iclrdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-114">Подкласс [ICLRDataTarget2](iclrdatatarget2-interface.md) , обеспечивающий доступ к сведениям об исключении.</span><span class="sxs-lookup"><span data-stu-id="8995e-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="8995e-115">[Интерфейс ICLRDebugging](iclrdebugging-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-115">[ICLRDebugging Interface](iclrdebugging-interface.md)\\</span></span>
 <span data-ttu-id="8995e-116">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="8995e-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="8995e-117">[Интерфейс ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)\\</span></span>
 <span data-ttu-id="8995e-118">Включает в себя [метод ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) метод, получающий интерфейс обратного вызова, который позволяет библиотеки отладки конкретной версии среды выполнения, находить и загружать по мере необходимости поставщика библиотеки.</span><span class="sxs-lookup"><span data-stu-id="8995e-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="8995e-119">[Интерфейс ICLRMetadataLocator](iclrmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="8995e-120">Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="8995e-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="8995e-121">[Интерфейс ICorDebug](icordebug-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-121">[ICorDebug Interface](icordebug-interface.md)\\</span></span>
 <span data-ttu-id="8995e-122">Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8995e-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="8995e-123">[Интерфейс1 ICorDebugAppDomain](icordebugappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-123">[ICorDebugAppDomain Interface1](icordebugappdomain-interface.md)\\</span></span>
 <span data-ttu-id="8995e-124">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="8995e-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="8995e-125">[ICorDebugAppDomain2 Interface1](icordebugappdomain2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-125">[ICorDebugAppDomain2 Interface1](icordebugappdomain2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-126">Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef.</span><span class="sxs-lookup"><span data-stu-id="8995e-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="8995e-127">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="8995e-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="8995e-128">[Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-129">Предоставляет методы для работы с типами [!INCLUDE[wrt](../../../../includes/wrt-md.md)] в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="8995e-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="8995e-130">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="8995e-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="8995e-131">[Интерфейс ICorDebugAppDomain4](icordebugappdomain4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\\</span></span>
 <span data-ttu-id="8995e-132">Логически расширяет [ICorDebugAppDomain](icordebugappdomain-interface.md) интерфейса для получения управляемого объекта из вызываемой оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="8995e-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="8995e-133">[ICorDebugAppDomainEnum Interface1](icordebugappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-133">[ICorDebugAppDomainEnum Interface1](icordebugappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-134">Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="8995e-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="8995e-135">[ICorDebugArrayValue Interface1](icordebugarrayvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-135">[ICorDebugArrayValue Interface1](icordebugarrayvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-136">Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="8995e-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="8995e-137">[Интерфейс1 ICorDebugAssembly](icordebugassembly-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-137">[ICorDebugAssembly Interface1](icordebugassembly-interface.md)\\</span></span>
 <span data-ttu-id="8995e-138">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="8995e-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="8995e-139">[Интерфейс1 ICorDebugAssembly2](icordebugassembly2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-139">[ICorDebugAssembly2 Interface1](icordebugassembly2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-140">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="8995e-140">Represents an assembly.</span></span> <span data-ttu-id="8995e-141">Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="8995e-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="8995e-142">[Интерфейс ICorDebugAssembly3](icordebugassembly3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-143">Логически расширяет [ICorDebugAssembly](icordebugassembly-interface.md) интерфейса для обеспечения поддержки контейнерных сборок и их вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="8995e-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="8995e-144">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-145">[Интерфейс1 ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-145">[ICorDebugAssemblyEnum Interface1](icordebugassemblyenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-146">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="8995e-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="8995e-147">[Интерфейс ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-148">Предоставляет перечислитель для списка [CorDebugBlockingObject](cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="8995e-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="8995e-149">[ICorDebugBoxValue Interface1](icordebugboxvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-149">[ICorDebugBoxValue Interface1](icordebugboxvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-150">Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.</span><span class="sxs-lookup"><span data-stu-id="8995e-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="8995e-151">[Интерфейс1 ICorDebugBreakpoint](icordebugbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-151">[ICorDebugBreakpoint Interface1](icordebugbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="8995e-152">Представляет точку останова в функции или контрольную точку для значения.</span><span class="sxs-lookup"><span data-stu-id="8995e-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="8995e-153">[ICorDebugBreakpointEnum Interface1](icordebugbreakpointenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-153">[ICorDebugBreakpointEnum Interface1](icordebugbreakpointenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-154">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="8995e-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="8995e-155">[Интерфейс1 ICorDebugChain](icordebugchain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-155">[ICorDebugChain Interface1](icordebugchain-interface.md)\\</span></span>
 <span data-ttu-id="8995e-156">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="8995e-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="8995e-157">[ICorDebugChainEnum Interface1](icordebugchainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-157">[ICorDebugChainEnum Interface1](icordebugchainenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-158">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="8995e-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="8995e-159">[Интерфейс1 ICorDebugClass](icordebugclass-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-159">[ICorDebugClass Interface1](icordebugclass-interface.md)\\</span></span>
 <span data-ttu-id="8995e-160">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="8995e-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="8995e-161">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="8995e-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="8995e-162">[ICorDebugClass2 Interface1](icordebugclass2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-162">[ICorDebugClass2 Interface1](icordebugclass2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-163">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="8995e-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="8995e-164">Этот интерфейс расширяет интерфейс `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="8995e-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="8995e-165">[Интерфейс1 ICorDebugCode](icordebugcode-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-165">[ICorDebugCode Interface1](icordebugcode-interface1.md)\\</span></span>
 <span data-ttu-id="8995e-166">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="8995e-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="8995e-167">[Интерфейс1 ICorDebugCode2](icordebugcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-167">[ICorDebugCode2 Interface1](icordebugcode2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-168">Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="8995e-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="8995e-169">[Интерфейс ICorDebugCode3](icordebugcode3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-170">Предоставляет метод, который расширяет [ICorDebugCode](icordebugcode-interface1.md) и [ICorDebugCode2](icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="8995e-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="8995e-171">[Интерфейс ICorDebugCode4](icordebugcode4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)\\</span></span>
 <span data-ttu-id="8995e-172">Предоставляет метод, который позволяет отладчику выполнить перечисление локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="8995e-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="8995e-173">[ICorDebugCodeEnum Interface1](icordebugcodeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-173">[ICorDebugCodeEnum Interface1](icordebugcodeenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-174">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="8995e-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="8995e-175">[Интерфейс ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-176">Предоставляет методы для получения кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8995e-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="8995e-177">[Интерфейс1 ICorDebugContext](icordebugcontext-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-177">[ICorDebugContext Interface1](icordebugcontext-interface.md)\\</span></span>
 <span data-ttu-id="8995e-178">Представляет объект контекста.</span><span class="sxs-lookup"><span data-stu-id="8995e-178">Represents a context object.</span></span> <span data-ttu-id="8995e-179">Этот интерфейс еще не реализован.</span><span class="sxs-lookup"><span data-stu-id="8995e-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="8995e-180">[Интерфейс1 ICorDebugController](icordebugcontroller-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-180">[ICorDebugController Interface1](icordebugcontroller-interface.md)\\</span></span>
 <span data-ttu-id="8995e-181">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="8995e-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="8995e-182">[Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)\\</span></span>
 <span data-ttu-id="8995e-183">Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="8995e-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="8995e-184">[Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-185">Логически расширяет [ICorDebugDataTarget](icordebugdatatarget-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8995e-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="8995e-186">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-187">[Интерфейс ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-188">Логически расширяет [ICorDebugDataTarget](icordebugdatatarget-interface.md) интерфейс для предоставления сведений о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="8995e-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="8995e-189">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-190">[Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)\\</span></span>
 <span data-ttu-id="8995e-191">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="8995e-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="8995e-192">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-193">[Интерфейс ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\\</span></span>
 <span data-ttu-id="8995e-194">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="8995e-194">Obsolete.</span></span> <span data-ttu-id="8995e-195">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8995e-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="8995e-196">[Интерфейс1 ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-196">[ICorDebugEditAndContinueSnapshot Interface1](icordebugeditandcontinuesnapshot-interface.md)\\</span></span>
 <span data-ttu-id="8995e-197">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="8995e-197">Obsolete.</span></span> <span data-ttu-id="8995e-198">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8995e-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="8995e-199">[Интерфейс1 ICorDebugEnum](icordebugenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-199">[ICorDebugEnum Interface1](icordebugenum-interface1.md)\\</span></span>
 <span data-ttu-id="8995e-200">Служит абстрактным базовым интерфейсом для перечислителей отладки.</span><span class="sxs-lookup"><span data-stu-id="8995e-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="8995e-201">[Интерфейс1 ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-201">[ICorDebugErrorInfoEnum Interface1](icordebugerrorinfoenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-202">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="8995e-202">Obsolete.</span></span> <span data-ttu-id="8995e-203">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8995e-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="8995e-204">[Интерфейс1 ICorDebugEval](icordebugeval-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-204">[ICorDebugEval Interface1](icordebugeval-interface.md)\\</span></span>
 <span data-ttu-id="8995e-205">Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="8995e-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="8995e-206">[ICorDebugEval2 Interface1](icordebugeval2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-206">[ICorDebugEval2 Interface1](icordebugeval2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-207">Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="8995e-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="8995e-208">[Интерфейс ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)\\</span></span>
 <span data-ttu-id="8995e-209">Расширяет [ICorDebugDebugEvent](icordebugdebugevent-interface.md) интерфейс для поддержки событий исключения.</span><span class="sxs-lookup"><span data-stu-id="8995e-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="8995e-210">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-211">[Интерфейс ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-212">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="8995e-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="8995e-213">[Интерфейс ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-214">Расширяет [ICorDebugObjectValue](icordebugobjectvalue-interface.md) интерфейс, чтобы предоставить сведения о трассировке стека из управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="8995e-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="8995e-215">[Интерфейс1 ICorDebugFrame](icordebugframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-215">[ICorDebugFrame Interface1](icordebugframe-interface.md)\\</span></span>
 <span data-ttu-id="8995e-216">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="8995e-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="8995e-217">[Интерфейс1 ICorDebugFrameEnum](icordebugframeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-217">[ICorDebugFrameEnum Interface1](icordebugframeenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-218">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="8995e-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="8995e-219">[Интерфейс1 ICorDebugFunction](icordebugfunction-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-219">[ICorDebugFunction Interface1](icordebugfunction-interface1.md)\\</span></span>
 <span data-ttu-id="8995e-220">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="8995e-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="8995e-221">[Интерфейс1 ICorDebugFunction2](icordebugfunction2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-221">[ICorDebugFunction2 Interface1](icordebugfunction2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-222">Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="8995e-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="8995e-223">[Интерфейс ICorDebugFunction3](icordebugfunction3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-224">Логически расширяет [ICorDebugFunction](icordebugfunction-interface1.md) интерфейс для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="8995e-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="8995e-225">[Интерфейс1 ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-225">[ICorDebugFunctionBreakpoint Interface1](icordebugfunctionbreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="8995e-226">Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="8995e-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="8995e-227">[Интерфейс ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-228">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="8995e-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="8995e-229">[ICorDebugGenericValue Interface1](icordebuggenericvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-229">[ICorDebugGenericValue Interface1](icordebuggenericvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-230">Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="8995e-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="8995e-231">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="8995e-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="8995e-232">[Интерфейс ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-233">Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="8995e-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="8995e-234">[Интерфейс1 ICorDebugHandleValue](icordebughandlevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-234">[ICorDebugHandleValue Interface1](icordebughandlevalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-235">Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8995e-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="8995e-236">[Интерфейс ICorDebugHeapEnum](icordebugheapenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-237">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="8995e-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="8995e-238">[Интерфейс ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-239">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="8995e-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="8995e-240">[Интерфейс1 ICorDebugHeapValue](icordebugheapvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-240">[ICorDebugHeapValue Interface1](icordebugheapvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-241">Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8995e-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="8995e-242">[Интерфейс1 ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-242">[ICorDebugHeapValue2 Interface1](icordebugheapvalue2-interface1.md)\\</span></span>
 <span data-ttu-id="8995e-243">Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8995e-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="8995e-244">[Интерфейс ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-245">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="8995e-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="8995e-246">[Интерфейс ICorDebugILCode](icordebugilcode-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)\\</span></span>
 <span data-ttu-id="8995e-247">Представляет сегмент кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="8995e-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="8995e-248">[Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-249">Логически расширяет [ICorDebugILCode](icordebugilcode-interface.md) интерфейс, чтобы предоставить методы, возвращающие маркер для подписи локальной переменной функции и сопоставлены инструментированного профилировщиком промежуточного языка (IL) смещений в исходный метод IL смещения.</span><span class="sxs-lookup"><span data-stu-id="8995e-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="8995e-250">[Интерфейс1 ICorDebugILFrame](icordebugilframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-250">[ICorDebugILFrame Interface1](icordebugilframe-interface.md)\\</span></span>
 <span data-ttu-id="8995e-251">Предоставляет кадр стека кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="8995e-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="8995e-252">[Интерфейс1 ICorDebugILFrame2](icordebugilframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-252">[ICorDebugILFrame2 Interface1](icordebugilframe2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-253">Логическое расширение интерфейса `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="8995e-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="8995e-254">[Интерфейс ICorDebugILFrame3](icordebugilframe3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-255">Предоставляет метод, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="8995e-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="8995e-256">[Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)\\</span></span>
 <span data-ttu-id="8995e-257">Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="8995e-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="8995e-258">Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8995e-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="8995e-259">[Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="8995e-260">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8995e-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="8995e-261">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-262">[Интерфейс1 ICorDebugInternalFrame](icordebuginternalframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-262">[ICorDebugInternalFrame Interface1](icordebuginternalframe-interface.md)\\</span></span>
 <span data-ttu-id="8995e-263">Задает типы кадров для отладчика.</span><span class="sxs-lookup"><span data-stu-id="8995e-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="8995e-264">[Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-265">Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно [ICorDebugFrame](icordebugframe-interface.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="8995e-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="8995e-266">[Интерфейс ICorDebugLoadedModule](icordebugloadedmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)\\</span></span>
 <span data-ttu-id="8995e-267">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="8995e-267">Provides information about a loaded module.</span></span> <span data-ttu-id="8995e-268">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-269">[Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="8995e-270">Предоставляет методы для обработки обратных вызовов отладчика.</span><span class="sxs-lookup"><span data-stu-id="8995e-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="8995e-271">[Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-272">Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="8995e-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="8995e-273">Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="8995e-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="8995e-274">[Интерфейс ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-275">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="8995e-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="8995e-276">[Интерфейс ICorDebugMDA](icordebugmda-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-276">[ICorDebugMDA Interface](icordebugmda-interface.md)\\</span></span>
 <span data-ttu-id="8995e-277">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="8995e-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="8995e-278">[Интерфейс ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)\\</span></span>
 <span data-ttu-id="8995e-279">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="8995e-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="8995e-280">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-281">[Интерфейс ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)\\</span></span>
 <span data-ttu-id="8995e-282">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="8995e-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="8995e-283">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-284">[Интерфейс ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)\\</span></span>
 <span data-ttu-id="8995e-285">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="8995e-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="8995e-286">[Интерфейс1 ICorDebugModule](icordebugmodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-286">[ICorDebugModule Interface1](icordebugmodule-interface.md)\\</span></span>
 <span data-ttu-id="8995e-287">Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="8995e-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="8995e-288">[Интерфейс1 ICorDebugModule2](icordebugmodule2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-288">[ICorDebugModule2 Interface1](icordebugmodule2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-289">Служит логическим расширением интерфейса `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="8995e-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="8995e-290">[Интерфейс ICorDebugModule3](icordebugmodule3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-291">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="8995e-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="8995e-292">[Интерфейс1 ICorDebugModuleBreakpoint](icordebugmodulebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-292">[ICorDebugModuleBreakpoint Interface1](icordebugmodulebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="8995e-293">Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.</span><span class="sxs-lookup"><span data-stu-id="8995e-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="8995e-294">[Интерфейс ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)\\</span></span>
 <span data-ttu-id="8995e-295">Расширяет [ICorDebugDebugEvent](icordebugdebugevent-interface.md) интерфейс для поддержки событий на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="8995e-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="8995e-296">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-297">[Интерфейс1 ICorDebugModuleEnum](icordebugmoduleenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-297">[ICorDebugModuleEnum Interface1](icordebugmoduleenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-298">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="8995e-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="8995e-299">[Интерфейс ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)\\</span></span>
 <span data-ttu-id="8995e-300">Расширяет [ICorDebugDataTarget](icordebugdatatarget-interface.md) интерфейс для поддержки целевых объектов изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="8995e-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="8995e-301">[Интерфейс1 ICorDebugNativeFrame](icordebugnativeframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-301">[ICorDebugNativeFrame Interface1](icordebugnativeframe-interface.md)\\</span></span>
 <span data-ttu-id="8995e-302">Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.</span><span class="sxs-lookup"><span data-stu-id="8995e-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="8995e-303">[Интерфейс ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-304">Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".</span><span class="sxs-lookup"><span data-stu-id="8995e-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="8995e-305">[Интерфейс1 ICorDebugObjectEnum](icordebugobjectenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-305">[ICorDebugObjectEnum Interface1](icordebugobjectenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-306">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="8995e-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="8995e-307">[Интерфейс1 ICorDebugObjectValue](icordebugobjectvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-307">[ICorDebugObjectValue Interface1](icordebugobjectvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-308">Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.</span><span class="sxs-lookup"><span data-stu-id="8995e-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="8995e-309">[Интерфейс1 ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-309">[ICorDebugObjectValue2 Interface1](icordebugobjectvalue2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-310">Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.</span><span class="sxs-lookup"><span data-stu-id="8995e-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="8995e-311">[Интерфейс1 ICorDebugProcess](icordebugprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-311">[ICorDebugProcess Interface1](icordebugprocess-interface.md)\\</span></span>
 <span data-ttu-id="8995e-312">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="8995e-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="8995e-313">[Интерфейс1 ICorDebugProcess2](icordebugprocess2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-313">[ICorDebugProcess2 Interface1](icordebugprocess2-interface1.md)\\</span></span>
 <span data-ttu-id="8995e-314">Логическое расширение интерфейса `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="8995e-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="8995e-315">[Интерфейс ICorDebugProcess3](icordebugprocess3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-316">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="8995e-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="8995e-317">[Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)\\</span></span>
 <span data-ttu-id="8995e-318">Обеспечивает поддержку вне контроля выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="8995e-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="8995e-319">[Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)\\</span></span>
 <span data-ttu-id="8995e-320">Расширяет [ICorDebugProcess](icordebugprocess-interface.md) локального интерфейса для поддержки доступа к управляемой куче, для предоставления сведений о сборке мусора управляемых объектов и для определения, загружает ли отладчик образы из приложения кэш образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="8995e-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="8995e-321">[Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)\\</span></span>
 <span data-ttu-id="8995e-322">Логически расширяет [ICorDebugProcess](icordebugprocess-interface.md) интерфейс для включения функции, такие как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей.</span><span class="sxs-lookup"><span data-stu-id="8995e-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="8995e-323">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-324">[Интерфейс ICorDebugProcess7](icordebugprocess7-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)\\</span></span>
 <span data-ttu-id="8995e-325">Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="8995e-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="8995e-326">[Интерфейс ICorDebugProcess8](icordebugprocess8-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)\\</span></span>
 <span data-ttu-id="8995e-327">Логически расширяет [ICorDebugProcess](icordebugprocess-interface.md) интерфейс, чтобы включить или отключить определенные виды [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) обратных вызовов исключения.</span><span class="sxs-lookup"><span data-stu-id="8995e-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="8995e-328">[ICorDebugProcessEnum Interface1](icordebugprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-328">[ICorDebugProcessEnum Interface1](icordebugprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-329">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="8995e-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="8995e-330">[Интерфейс1 ICorDebugReferenceValue](icordebugreferencevalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-330">[ICorDebugReferenceValue Interface1](icordebugreferencevalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-331">Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="8995e-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="8995e-332">[Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)\\</span></span>
 <span data-ttu-id="8995e-333">Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="8995e-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="8995e-334">[Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-335">Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.</span><span class="sxs-lookup"><span data-stu-id="8995e-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="8995e-336">[Интерфейс ICorDebugRemote](icordebugremote-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-336">[ICorDebugRemote Interface](icordebugremote-interface.md)\\</span></span>
 <span data-ttu-id="8995e-337">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="8995e-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="8995e-338">[Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)\\</span></span>
 <span data-ttu-id="8995e-339">Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8995e-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="8995e-340">[Интерфейс ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)\\</span></span>
 <span data-ttu-id="8995e-341">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="8995e-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="8995e-342">[Интерфейс ICorDebugStackWalk](icordebugstackwalk-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)\\</span></span>
 <span data-ttu-id="8995e-343">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="8995e-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="8995e-344">[Интерфейс ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)\\</span></span>
 <span data-ttu-id="8995e-345">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="8995e-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="8995e-346">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-347">[Интерфейс1 ICorDebugStepper](icordebugstepper-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-347">[ICorDebugStepper Interface1](icordebugstepper-interface.md)\\</span></span>
 <span data-ttu-id="8995e-348">Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.</span><span class="sxs-lookup"><span data-stu-id="8995e-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="8995e-349">[Интерфейс1 ICorDebugStepper2](icordebugstepper2-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-349">[ICorDebugStepper2 Interface1](icordebugstepper2-interface1.md)\\</span></span>
 <span data-ttu-id="8995e-350">Предоставляет поддержку отладки "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="8995e-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="8995e-351">[Интерфейс1 ICorDebugStepperEnum](icordebugstepperenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-351">[ICorDebugStepperEnum Interface1](icordebugstepperenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-352">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="8995e-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="8995e-353">[Интерфейс1 ICorDebugStringValue](icordebugstringvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-353">[ICorDebugStringValue Interface1](icordebugstringvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-354">Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.</span><span class="sxs-lookup"><span data-stu-id="8995e-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="8995e-355">[Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)\\</span></span>
 <span data-ttu-id="8995e-356">Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="8995e-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="8995e-357">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-358">[Интерфейс ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-359">Логически расширяет [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) интерфейс для извлечения дополнительных символов отладки.</span><span class="sxs-lookup"><span data-stu-id="8995e-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="8995e-360">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-361">[Интерфейс1 ICorDebugThread](icordebugthread-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-361">[ICorDebugThread Interface1](icordebugthread-interface.md)\\</span></span>
 <span data-ttu-id="8995e-362">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="8995e-362">Represents a thread in a process.</span></span> <span data-ttu-id="8995e-363">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="8995e-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="8995e-364">[Интерфейс1 ICorDebugThread2](icordebugthread2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-364">[ICorDebugThread2 Interface1](icordebugthread2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-365">Служит логическим расширением интерфейса `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="8995e-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="8995e-366">[Интерфейс ICorDebugThread3](icordebugthread3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-367">Предоставляет точку входа для [ICorDebugStackWalk](icordebugstackwalk-interface.md) и соответствующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="8995e-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="8995e-368">[Интерфейс ICorDebugThread4](icordebugthread4-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)\\</span></span>
 <span data-ttu-id="8995e-369">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="8995e-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="8995e-370">[ICorDebugThreadEnum Interface1](icordebugthreadenum-interface1.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-370">[ICorDebugThreadEnum Interface1](icordebugthreadenum-interface1.md)\\</span></span>
 <span data-ttu-id="8995e-371">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="8995e-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="8995e-372">[Интерфейс1 ICorDebugType](icordebugtype-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-372">[ICorDebugType Interface1](icordebugtype-interface.md)\\</span></span>
 <span data-ttu-id="8995e-373">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="8995e-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="8995e-374">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="8995e-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="8995e-375">[Интерфейс ICorDebugType2](icordebugtype2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-376">Расширяет [ICorDebugType](icordebugtype-interface.md) интерфейс для извлечения идентификатора типа базового типа или сложного типа (определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="8995e-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="8995e-377">[ICorDebugTypeEnum Interface1](icordebugtypeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-377">[ICorDebugTypeEnum Interface1](icordebugtypeenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-378">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="8995e-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="8995e-379">[Интерфейс ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)\\</span></span>
 <span data-ttu-id="8995e-380">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="8995e-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="8995e-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-381">[ICorDebugValue](icordebugvalue-interface.md)\\</span></span>
 <span data-ttu-id="8995e-382">Представляет значение для записи или чтения в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="8995e-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="8995e-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-383">[ICorDebugValue2](icordebugvalue2-interface.md)\\</span></span>
 <span data-ttu-id="8995e-384">Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="8995e-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="8995e-385">[Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)\\</span></span>
 <span data-ttu-id="8995e-386">Расширяет интерфейс «ICorDebugValue» и «ICorDebugValue2» для обеспечения поддержки массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="8995e-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="8995e-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\\</span></span>
 <span data-ttu-id="8995e-388">Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="8995e-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="8995e-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-390">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="8995e-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="8995e-391">[Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)\\</span></span>
 <span data-ttu-id="8995e-392">Представляет локальную переменную или аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="8995e-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="8995e-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-394">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="8995e-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="8995e-395">[Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)\\</span></span>
 <span data-ttu-id="8995e-396">Извлекает сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="8995e-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="8995e-397">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-398">[Интерфейс ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)\\</span></span>
 <span data-ttu-id="8995e-399">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="8995e-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="8995e-400">**Доступно только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="8995e-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="8995e-401">[Интерфейс ICorPublish](icorpublish-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-401">[ICorPublish Interface](icorpublish-interface.md)\\</span></span>
 <span data-ttu-id="8995e-402">Служит универсальным интерфейсом для процессов публикации.</span><span class="sxs-lookup"><span data-stu-id="8995e-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="8995e-403">[Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)\\</span></span>
 <span data-ttu-id="8995e-404">Представляет и предоставляет информацию о домене приложения.</span><span class="sxs-lookup"><span data-stu-id="8995e-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="8995e-405">[Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-406">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.</span><span class="sxs-lookup"><span data-stu-id="8995e-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="8995e-407">[Интерфейс ICorPublishEnum](icorpublishenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-408">Служит абстрактной базой для перечислителей публикации.</span><span class="sxs-lookup"><span data-stu-id="8995e-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="8995e-409">[Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)\\</span></span>
 <span data-ttu-id="8995e-410">Предоставляет методы, позволяющие получить доступ к сведениям о процессе.</span><span class="sxs-lookup"><span data-stu-id="8995e-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="8995e-411">[Интерфейс ICorPublishProcessEnum](icorpublishprocessenum-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\\</span></span>
 <span data-ttu-id="8995e-412">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="8995e-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="8995e-413">[Интерфейс ISOSDacInterface](isosdacinterface-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)\\</span></span>
 <span data-ttu-id="8995e-414">Предоставляет вспомогательные методы для доступа к данным из `SOS`.</span><span class="sxs-lookup"><span data-stu-id="8995e-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="8995e-415">[Интерфейс IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)\\</span></span>
 <span data-ttu-id="8995e-416">Предоставляет методы для запроса на получение сведений об определении метода.</span><span class="sxs-lookup"><span data-stu-id="8995e-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="8995e-417">[Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)\\</span></span>
 <span data-ttu-id="8995e-418">Предоставляет методы для запроса на получение сведений о экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="8995e-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="8995e-419">[Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)\\</span></span>
 <span data-ttu-id="8995e-420">Предоставляет методы для запроса на получение сведений о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="8995e-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="8995e-421">[Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\\</span></span>
 <span data-ttu-id="8995e-422">Предоставляет методы для запроса на получение сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="8995e-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="8995e-423">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8995e-423">Related Sections</span></span>  
 <span data-ttu-id="8995e-424">[Коклассы отладки](debugging-coclasses.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-424">[Debugging Coclasses](debugging-coclasses.md)\\</span></span>
 <span data-ttu-id="8995e-425">[Глобальные статические функции отладки](debugging-global-static-functions.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-425">[Debugging Global Static Functions](debugging-global-static-functions.md)\\</span></span>
 <span data-ttu-id="8995e-426">[Перечисления отладки](debugging-enumerations.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-426">[Debugging Enumerations](debugging-enumerations.md)\\</span></span>
 <span data-ttu-id="8995e-427">[Структуры отладки](debugging-structures.md)\\</span><span class="sxs-lookup"><span data-stu-id="8995e-427">[Debugging Structures](debugging-structures.md)\\</span></span>
