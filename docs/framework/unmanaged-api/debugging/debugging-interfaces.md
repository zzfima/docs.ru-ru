---
title: Интерфейсы отладки
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: c4b9cdc2bc90096ab7c3b041bd8aa2742b48c35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179166"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="1cef5-102">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1cef5-102">Debugging Interfaces</span></span>
<span data-ttu-id="1cef5-103">В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="1cef5-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1cef5-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="1cef5-104">In This Section</span></span>  
 <span data-ttu-id="1cef5-105">[Интерфейс ICLRDataEnumMemoryРегионы](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="1cef5-106">Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.</span><span class="sxs-lookup"><span data-stu-id="1cef5-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="1cef5-107">[Интерфейс ICLRDataEnumMemoryCallback](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="1cef5-108">Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="1cef5-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="1cef5-109">[Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="1cef5-110">Предоставляет методы для взаимодействия с целевым процессом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1cef5-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="1cef5-111">[Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-112">Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="1cef5-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="1cef5-113">[Интерфейс ICLRDataTarget3](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-114">Подкласс [ICLRDataTarget2,](iclrdatatarget2-interface.md) предоставляющий доступ к информации об исключениях.</span><span class="sxs-lookup"><span data-stu-id="1cef5-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="1cef5-115">[Интерфейс ICLRDebugging](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="1cef5-116">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="1cef5-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="1cef5-117">[Интерфейс ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="1cef5-118">Включает метод [ProvideLibrary Method,](iclrdebugginglibraryprovider-providelibrary-method.md) который получает интерфейс обратного вызова поставщика библиотек, который позволяет находить и загружать библиотеки отладки по требованию для общего времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="1cef5-119">[Интерфейс ICLRMetadataLocator](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="1cef5-120">Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="1cef5-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="1cef5-121">[Интерфейс ICorDebug](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="1cef5-122">Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="1cef5-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="1cef5-123">[Интерфейс ICorDebugAppDomain](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="1cef5-124">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="1cef5-125">[Интерфейс ICorDebugAppDomain2](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-126">Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef.</span><span class="sxs-lookup"><span data-stu-id="1cef5-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="1cef5-127">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="1cef5-128">[Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-129">Предоставляет методы работы с типами Runtime Windows в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="1cef5-130">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="1cef5-131">[Интерфейс ICorDebugAppDomain4](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="1cef5-132">Логически расширяет интерфейс [ICorDebugAppDomain,](icordebugappdomain-interface.md) чтобы получить управляемый объект из вызываемой обертки COM.</span><span class="sxs-lookup"><span data-stu-id="1cef5-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="1cef5-133">[Интерфейс ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-134">Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="1cef5-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="1cef5-135">[Интерфейс ICorDebugArrayValueValue](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-136">Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="1cef5-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="1cef5-137">[Интерфейс ICorDebugAssembly](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="1cef5-138">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="1cef5-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="1cef5-139">[Интерфейс ICorDebugAssembly2](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-140">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="1cef5-140">Represents an assembly.</span></span> <span data-ttu-id="1cef5-141">Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="1cef5-142">[Интерфейс ICorDebugAssembly3](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-143">Логически расширяет интерфейс [ICorDebugAssembly,](icordebugassembly-interface.md) чтобы обеспечить поддержку контейнерных сборок и содержащихся в них сборок.</span><span class="sxs-lookup"><span data-stu-id="1cef5-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="1cef5-144">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-145">[Интерфейс ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-146">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-147">[Интерфейс ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-148">Предоставляет список для списка структур [CorDebugBlockingObject.](cordebugblockingobject-structure.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="1cef5-149">[Интерфейс ICorDebugBoxValue](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-150">Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.</span><span class="sxs-lookup"><span data-stu-id="1cef5-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="1cef5-151">[Интерфейс ICorDebugBreakpoint](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1cef5-152">Представляет точку останова в функции или контрольную точку для значения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="1cef5-153">[Интерфейс ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-154">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-155">[Интерфейс ICorDebugChain](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="1cef5-156">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="1cef5-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="1cef5-157">[Интерфейс ICorDebugChainEnum](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-158">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-159">[Интерфейс ICorDebugClass](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="1cef5-160">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="1cef5-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="1cef5-161">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="1cef5-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="1cef5-162">[Интерфейс ICorDebugClass2](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-163">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="1cef5-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="1cef5-164">Этот интерфейс расширяет интерфейс `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="1cef5-165">[Интерфейс ICorDebugCode](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="1cef5-166">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="1cef5-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="1cef5-167">[Интерфейс ICorDebugCode2](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-168">Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="1cef5-169">[Интерфейс ICorDebugCode3](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-170">Предоставляет метод, который расширяет [ICorDebugCode](icordebugcode-interface1.md) и [ICorDebugCode2](icordebugcode2-interface.md) для предоставления информации о управляемой стоимости возврата.</span><span class="sxs-lookup"><span data-stu-id="1cef5-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="1cef5-171">[Интерфейс ICorDebugCode4](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="1cef5-172">Предоставляет метод, позволяющий отладчику перечислять локальные переменные и аргументы в функции.</span><span class="sxs-lookup"><span data-stu-id="1cef5-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="1cef5-173">[Интерфейс ICorDebugCodeEnum](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-174">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-175">[Интерфейс ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-176">Предоставляет методы для получения кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1cef5-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="1cef5-177">[Интерфейс ICorDebugContext](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="1cef5-178">Представляет объект контекста.</span><span class="sxs-lookup"><span data-stu-id="1cef5-178">Represents a context object.</span></span> <span data-ttu-id="1cef5-179">Этот интерфейс еще не реализован.</span><span class="sxs-lookup"><span data-stu-id="1cef5-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="1cef5-180">[Интерфейс ICorDebugController](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="1cef5-181">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="1cef5-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="1cef5-182">[Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="1cef5-183">Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="1cef5-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="1cef5-184">[Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-185">Логически расширяет интерфейс [ICorDebugDataTarget.](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="1cef5-186">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-187">[Интерфейс ICorDebugDataTarget3](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-188">Логически расширяет интерфейс [ICorDebugDataTarget,](icordebugdatatarget-interface.md) чтобы предоставить информацию о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="1cef5-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="1cef5-189">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-190">[Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="1cef5-191">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="1cef5-192">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-193">[ICorDebugEditAndcontinueerrorinfo Интерфейс](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="1cef5-194">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="1cef5-194">Obsolete.</span></span> <span data-ttu-id="1cef5-195">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1cef5-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="1cef5-196">[Интерфейс ICorDebugEditAndcontinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="1cef5-197">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="1cef5-197">Obsolete.</span></span> <span data-ttu-id="1cef5-198">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1cef5-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="1cef5-199">[Интерфейс ICorDebugEnum](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="1cef5-200">Служит абстрактным базовым интерфейсом для перечислителей отладки.</span><span class="sxs-lookup"><span data-stu-id="1cef5-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="1cef5-201">[Интерфейс ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-202">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="1cef5-202">Obsolete.</span></span> <span data-ttu-id="1cef5-203">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1cef5-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="1cef5-204">[Интерфейс ICorDebugEval](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="1cef5-205">Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="1cef5-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="1cef5-206">[Интерфейс ICorDebugEval2](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-207">Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="1cef5-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="1cef5-208">[ICorDebugИзедебугВент Интерфейс](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="1cef5-209">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключений.</span><span class="sxs-lookup"><span data-stu-id="1cef5-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="1cef5-210">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-211">[Интерфейс ICorDebugExceptionObjectstackStackEnum интерфейс](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-212">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="1cef5-213">[Интерфейс ICorDebugExceptionValueValueValue](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-214">Расширяет интерфейс [ICorDebugObjectValue,](icordebugobjectvalue-interface.md) чтобы предоставить информацию о стеках из управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="1cef5-215">[Интерфейс ICorDebugFrame](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="1cef5-216">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="1cef5-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="1cef5-217">[Интерфейс ICorDebugFrameEnum](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-218">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-219">[Интерфейс ICorDebugFunction](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="1cef5-220">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="1cef5-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="1cef5-221">[Интерфейс ICorDebugFunction2](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-222">Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="1cef5-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="1cef5-223">[Интерфейс ICorDebugFunction3](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-224">Логически расширяет интерфейс [ICorDebugFunction,](icordebugfunction-interface1.md) чтобы обеспечить доступ к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="1cef5-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="1cef5-225">[Интерфейс ICorDebugФункцияBreakpoint](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1cef5-226">Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="1cef5-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="1cef5-227">[Интерфейс ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-228">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="1cef5-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="1cef5-229">[Интерфейс ICorDebugGenericValue](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-230">Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="1cef5-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="1cef5-231">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="1cef5-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="1cef5-232">[Интерфейс ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-233">Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="1cef5-234">[Интерфейс ICorDebugHandleValue](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-235">Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1cef5-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="1cef5-236">[Интерфейс ICorDebugHeapEnum](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-237">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="1cef5-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="1cef5-238">[Интерфейс ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-239">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="1cef5-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="1cef5-240">[Интерфейс ICorDebugHeapValue](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-241">Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1cef5-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="1cef5-242">[Интерфейс ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="1cef5-243">Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="1cef5-244">[Интерфейс ICorDebugHeapValue3](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-245">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="1cef5-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="1cef5-246">[Интерфейс ICorDebugILCode](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="1cef5-247">Представляет сегмент кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="1cef5-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="1cef5-248">[Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-249">Логически расширяет интерфейс [ICorDebugILCode,](icordebugilcode-interface.md) чтобы обеспечить методы, которые возвращают токен для локальной переменной подписи функции, и что карта инструментальный промежуточный язык профайлера (IL) компенсируется оригинальным методом IL смещения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="1cef5-250">[Интерфейс ICorDebugILFrame](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="1cef5-251">Предоставляет кадр стека кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="1cef5-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="1cef5-252">[Интерфейс ICorDebugILFrame2](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-253">Логическое расширение интерфейса `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="1cef5-254">[Интерфейс ICorDebugILFrame3](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-255">Предоставляет метод, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="1cef5-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="1cef5-256">[Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="1cef5-257">Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="1cef5-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="1cef5-258">Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="1cef5-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="1cef5-259">[Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="1cef5-260">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1cef5-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="1cef5-261">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-262">[Интерфейс ICorDebugInternalFrame](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="1cef5-263">Задает типы кадров для отладчика.</span><span class="sxs-lookup"><span data-stu-id="1cef5-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="1cef5-264">[Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-265">Предоставляет информацию о внутренних кадрах, включая адрес стека и положение по отношению к объектам [ICorDebugFrame.](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="1cef5-266">[ICorDebugLoadedModule Интерфейс](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="1cef5-267">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="1cef5-267">Provides information about a loaded module.</span></span> <span data-ttu-id="1cef5-268">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-269">[ICorDebugManagedCallback Интерфейс](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="1cef5-270">Предоставляет методы для обработки обратных вызовов отладчика.</span><span class="sxs-lookup"><span data-stu-id="1cef5-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="1cef5-271">[ICorDebugManagedCallback2 Интерфейс](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-272">Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="1cef5-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="1cef5-273">Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="1cef5-274">[ICorDebugManagedCallback3 Интерфейс](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-275">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="1cef5-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="1cef5-276">[Интерфейс ICorDebugMDA](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="1cef5-277">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="1cef5-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="1cef5-278">[Интерфейс ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="1cef5-279">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="1cef5-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="1cef5-280">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-281">[ICorDebugMergedAssemblyЗапись интерфейса](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="1cef5-282">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="1cef5-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="1cef5-283">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-284">[Интерфейс ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="1cef5-285">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="1cef5-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="1cef5-286">[Интерфейс ICorDebugМодуль](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="1cef5-287">Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="1cef5-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="1cef5-288">[Интерфейс ICorDebugModule2](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-289">Служит логическим расширением интерфейса `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="1cef5-290">[Интерфейс ICorDebugModule3](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-291">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="1cef5-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="1cef5-292">[Интерфейс ICorDebugModule](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1cef5-293">Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.</span><span class="sxs-lookup"><span data-stu-id="1cef5-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="1cef5-294">[ICorDebugModuleDebugEvent Интерфейс](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="1cef5-295">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="1cef5-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="1cef5-296">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-297">[Интерфейс ICorDebugModuleEnum](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-298">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-299">[ICorDebugMutableDataTarget Интерфейс](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="1cef5-300">Расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) для поддержки немых целей данных.</span><span class="sxs-lookup"><span data-stu-id="1cef5-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="1cef5-301">[Интерфейс ICorDebugNativeFrame](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="1cef5-302">Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.</span><span class="sxs-lookup"><span data-stu-id="1cef5-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="1cef5-303">[Интерфейс ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-304">Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".</span><span class="sxs-lookup"><span data-stu-id="1cef5-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="1cef5-305">[Интерфейс ICorDebugObjectEnum](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-306">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="1cef5-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="1cef5-307">[Интерфейс ICorDebugObjectValue](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-308">Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.</span><span class="sxs-lookup"><span data-stu-id="1cef5-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="1cef5-309">[Интерфейс ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-310">Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.</span><span class="sxs-lookup"><span data-stu-id="1cef5-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="1cef5-311">[Интерфейс ICorDebugProcess](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="1cef5-312">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="1cef5-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="1cef5-313">[Интерфейс ICorDebugProcess2](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="1cef5-314">Логическое расширение интерфейса `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="1cef5-315">[Интерфейс ICorDebugProcess3](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-316">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="1cef5-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="1cef5-317">[Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="1cef5-318">Обеспечивает поддержку вне контроля выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="1cef5-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="1cef5-319">[Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="1cef5-320">Расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) для поддержки доступа к управляемой куче, предоставления информации о сборе мусора управляемых объектов и определения того, загружает ли отладчик изображения из локального кэша изображений приложения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="1cef5-321">[Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="1cef5-322">Логически расширяет интерфейс [ICorDebugProcess,](icordebugprocess-interface.md) чтобы включить такие функции, как декодирование управляемых событий отладки, которые закодированы в событиях отладки родных исключений и расставании виртуального модуля.</span><span class="sxs-lookup"><span data-stu-id="1cef5-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="1cef5-323">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-324">[Интерфейс ICorDebugProcess7](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="1cef5-325">Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="1cef5-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="1cef5-326">[Интерфейс ICorDebugProcess8](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="1cef5-327">Логически расширяет интерфейс [ICorDebugProcess,](icordebugprocess-interface.md) чтобы включить или отключить определенные типы обратных вызовов [iCorDebugManagedCallback2.](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="1cef5-328">[Интерфейс ICorDebugProcessEnum](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-329">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-330">[ICorDebugСправкаИнтерфейс](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-331">Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="1cef5-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="1cef5-332">[Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="1cef5-333">Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="1cef5-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="1cef5-334">[Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-335">Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.</span><span class="sxs-lookup"><span data-stu-id="1cef5-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="1cef5-336">[ICorDebugУдаленный интерфейс](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="1cef5-337">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="1cef5-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="1cef5-338">[Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="1cef5-339">Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="1cef5-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="1cef5-340">[Интерфейс ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="1cef5-341">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="1cef5-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="1cef5-342">[Интерфейс ICorDebugStackWalk](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="1cef5-343">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="1cef5-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="1cef5-344">[Интерфейс ICorDebugStaticfieldSymbol](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="1cef5-345">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="1cef5-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="1cef5-346">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-347">[Интерфейс ICorDebugStepper](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="1cef5-348">Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.</span><span class="sxs-lookup"><span data-stu-id="1cef5-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="1cef5-349">[Интерфейс ICorDebugStepper2](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="1cef5-350">Предоставляет поддержку отладки "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="1cef5-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="1cef5-351">[Интерфейс ICorDebugStepperEnum](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-352">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-353">[Интерфейс ICorDebugStringValue](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-354">Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.</span><span class="sxs-lookup"><span data-stu-id="1cef5-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="1cef5-355">[Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="1cef5-356">Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="1cef5-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="1cef5-357">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-358">[Интерфейс ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-359">Логически расширяет интерфейс [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) для получения дополнительной информации о символе отладки.</span><span class="sxs-lookup"><span data-stu-id="1cef5-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="1cef5-360">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-361">[Интерфейс ICorDebugThread](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="1cef5-362">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="1cef5-362">Represents a thread in a process.</span></span> <span data-ttu-id="1cef5-363">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="1cef5-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="1cef5-364">[Интерфейс ICorDebugThread2](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-365">Служит логическим расширением интерфейса `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="1cef5-366">[Интерфейс ICorDebugThread3](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-367">Обеспечивает точку входа в [ICorDebugStackWalk](icordebugstackwalk-interface.md) и соответствующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="1cef5-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="1cef5-368">[Интерфейс ICorDebugThread4](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="1cef5-369">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="1cef5-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="1cef5-370">[Интерфейс ICorDebugThreadEnum](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="1cef5-371">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-372">[Интерфейс ICorDebugType](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="1cef5-373">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="1cef5-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="1cef5-374">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="1cef5-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="1cef5-375">[Интерфейс ICorDebugType2](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-376">Расширяет интерфейс [ICorDebugType](icordebugtype-interface.md) для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.</span><span class="sxs-lookup"><span data-stu-id="1cef5-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="1cef5-377">[Интерфейс ICorDebugTypeEnum](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-378">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-379">[ICorDebugUnmanagedCallback Интерфейс](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="1cef5-380">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1cef5-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="1cef5-381">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="1cef5-382">Представляет значение для записи или чтения в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="1cef5-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="1cef5-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="1cef5-384">Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="1cef5-385">[Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="1cef5-386">Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, превышают 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="1cef5-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="1cef5-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1cef5-388">Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="1cef5-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="1cef5-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-390">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="1cef5-391">[ICorDebug ПеременныйДомашний Интерфейс](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="1cef5-392">Представляет локальную переменную или аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="1cef5-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="1cef5-393">[Интерфейс ICorDebug VariableHomeEnum](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-394">Обеспечивает перечисление локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="1cef5-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="1cef5-395">[Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="1cef5-396">Извлекает сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="1cef5-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="1cef5-397">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-398">[Интерфейс ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="1cef5-399">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="1cef5-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="1cef5-400">**Доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="1cef5-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1cef5-401">[Интерфейс ICorPublish](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="1cef5-402">Служит универсальным интерфейсом для процессов публикации.</span><span class="sxs-lookup"><span data-stu-id="1cef5-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="1cef5-403">[Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="1cef5-404">Представляет и предоставляет информацию о домене приложения.</span><span class="sxs-lookup"><span data-stu-id="1cef5-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="1cef5-405">[Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-406">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.</span><span class="sxs-lookup"><span data-stu-id="1cef5-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="1cef5-407">[Интерфейс ICorPublishEnum](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-408">Служит абстрактной базой для перечислителей публикации.</span><span class="sxs-lookup"><span data-stu-id="1cef5-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="1cef5-409">[Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="1cef5-410">Предоставляет методы, позволяющие получить доступ к сведениям о процессе.</span><span class="sxs-lookup"><span data-stu-id="1cef5-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="1cef5-411">[Интерфейс ICorPublishProcessEnum](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="1cef5-412">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="1cef5-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="1cef5-413">[Интерфейс ISOSDacИнтерфейс](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="1cef5-414">Предоставляет вспомогательные методы `SOS`для доступа к данным из .</span><span class="sxs-lookup"><span data-stu-id="1cef5-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="1cef5-415">[Интерфейс IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="1cef5-416">Предоставляет методы запроса информации об определении метода.</span><span class="sxs-lookup"><span data-stu-id="1cef5-416">Provides methods for querying information about a method definition.</span></span>

 <span data-ttu-id="1cef5-417">[Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="1cef5-418">Предоставляет методы запроса информации о экземпляре метода.</span><span class="sxs-lookup"><span data-stu-id="1cef5-418">Provides methods for querying information about a method instance.</span></span>

 <span data-ttu-id="1cef5-419">[Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="1cef5-420">Предоставляет методы запроса информации о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="1cef5-420">Provides methods for querying information about a loaded module.</span></span>

 <span data-ttu-id="1cef5-421">[Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="1cef5-422">Предоставляет методы запроса информации о процессе.</span><span class="sxs-lookup"><span data-stu-id="1cef5-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="1cef5-423">См. также</span><span class="sxs-lookup"><span data-stu-id="1cef5-423">Related Sections</span></span>  
 <span data-ttu-id="1cef5-424">[Дебагинг coclasses](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="1cef5-425">[Отладка глобальных статических функций](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="1cef5-426">[Отладка цифр](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="1cef5-427">[Структуры отладки](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="1cef5-427">[Debugging Structures](debugging-structures.md)</span></span>\
