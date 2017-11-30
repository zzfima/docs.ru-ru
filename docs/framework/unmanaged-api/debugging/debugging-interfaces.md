---
title: "Интерфейсы отладки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de2469d15eef40b9ef283d67aeca429d9d96a7ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-interfaces"></a><span data-ttu-id="b3993-102">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b3993-102">Debugging Interfaces</span></span>
<span data-ttu-id="b3993-103">В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="b3993-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3993-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="b3993-104">In This Section</span></span>  
 [<span data-ttu-id="b3993-105">Интерфейс ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="b3993-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="b3993-106">Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.</span><span class="sxs-lookup"><span data-stu-id="b3993-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="b3993-107">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="b3993-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="b3993-108">Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="b3993-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="b3993-109">ICLRDataTarget-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="b3993-110">Предоставляет методы для взаимодействия с целевым процессом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b3993-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="b3993-111">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="b3993-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="b3993-112">Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="b3993-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="b3993-113">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="b3993-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="b3993-114">Подкласс [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , предоставляющий доступ к информации об исключении.</span><span class="sxs-lookup"><span data-stu-id="b3993-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="b3993-115">Интерфейс ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="b3993-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="b3993-116">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="b3993-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="b3993-117">Интерфейс ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="b3993-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="b3993-118">Включает в себя [метод ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) метод, получающий интерфейс обратного вызова, который позволяет среды выполнения от версии библиотеки отладки находить и загружать по требованию библиотеки поставщика.</span><span class="sxs-lookup"><span data-stu-id="b3993-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="b3993-119">Iclrmetadatalocator-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="b3993-120">Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="b3993-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="b3993-121">ICorDebug-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="b3993-122">Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="b3993-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="b3993-123">ICorDebugAppDomain интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="b3993-124">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="b3993-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="b3993-125">Интерфейс1 ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="b3993-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="b3993-126">Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef.</span><span class="sxs-lookup"><span data-stu-id="b3993-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="b3993-127">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="b3993-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="b3993-128">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="b3993-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="b3993-129">Предоставляет методы для работы с типами [!INCLUDE[wrt](../../../../includes/wrt-md.md)] в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="b3993-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="b3993-130">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="b3993-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="b3993-131">Интерфейс ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="b3993-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="b3993-132">Логически расширяет [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) интерфейс для получения управляемого объекта из вызываемой оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="b3993-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="b3993-133">ICorDebugAppDomainEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="b3993-134">Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="b3993-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="b3993-135">ICorDebugArrayValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="b3993-136">Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="b3993-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="b3993-137">ICorDebugAssembly интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="b3993-138">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="b3993-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="b3993-139">Интерфейс1 ICorDebugAssembly2</span><span class="sxs-lookup"><span data-stu-id="b3993-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="b3993-140">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="b3993-140">Represents an assembly.</span></span> <span data-ttu-id="b3993-141">Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="b3993-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="b3993-142">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="b3993-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="b3993-143">Логически расширяет [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) интерфейс для обеспечения поддержки контейнерных сборок и их вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="b3993-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="b3993-144">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-145">ICorDebugAssemblyEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="b3993-146">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="b3993-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-147">Icordebugblockingobjectenum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="b3993-148">Предоставляет перечислитель для списка [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="b3993-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="b3993-149">ICorDebugBoxValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="b3993-150">Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.</span><span class="sxs-lookup"><span data-stu-id="b3993-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="b3993-151">ICorDebugBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="b3993-152">Представляет точку останова в функции или контрольную точку для значения.</span><span class="sxs-lookup"><span data-stu-id="b3993-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="b3993-153">ICorDebugBreakpointEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="b3993-154">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="b3993-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-155">ICorDebugChain интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="b3993-156">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="b3993-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="b3993-157">ICorDebugChainEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="b3993-158">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="b3993-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-159">ICorDebugClass интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="b3993-160">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="b3993-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="b3993-161">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="b3993-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="b3993-162">ICorDebugClass2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="b3993-163">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="b3993-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="b3993-164">Этот интерфейс расширяет интерфейс `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="b3993-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="b3993-165">ICorDebugCode интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="b3993-166">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="b3993-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="b3993-167">Интерфейс1 ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="b3993-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="b3993-168">Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="b3993-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="b3993-169">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="b3993-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="b3993-170">Предоставляет метод, который расширяет [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) и [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="b3993-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="b3993-171">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="b3993-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="b3993-172">Предоставляет метод, который позволяет отладчику выполнить перечисление локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="b3993-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="b3993-173">Интерфейс1 ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="b3993-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="b3993-174">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="b3993-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-175">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="b3993-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="b3993-176">Предоставляет методы для получения кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b3993-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="b3993-177">Интерфейс1 ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="b3993-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="b3993-178">Представляет объект контекста.</span><span class="sxs-lookup"><span data-stu-id="b3993-178">Represents a context object.</span></span> <span data-ttu-id="b3993-179">Этот интерфейс еще не реализован.</span><span class="sxs-lookup"><span data-stu-id="b3993-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="b3993-180">ICorDebugController интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="b3993-181">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="b3993-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="b3993-182">ICorDebugDataTarget-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="b3993-183">Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="b3993-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="b3993-184">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="b3993-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="b3993-185">Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b3993-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="b3993-186">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-187">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="b3993-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="b3993-188">Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для предоставления сведений о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="b3993-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="b3993-189">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-190">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="b3993-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="b3993-191">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="b3993-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="b3993-192">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-193">Icordebugeditandcontinueerrorinfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="b3993-194">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b3993-194">Obsolete.</span></span> <span data-ttu-id="b3993-195">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b3993-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="b3993-196">Интерфейс1 ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="b3993-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="b3993-197">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b3993-197">Obsolete.</span></span> <span data-ttu-id="b3993-198">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b3993-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="b3993-199">ICorDebugEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="b3993-200">Служит абстрактным базовым интерфейсом для перечислителей отладки.</span><span class="sxs-lookup"><span data-stu-id="b3993-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="b3993-201">ICorDebugErrorInfoEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="b3993-202">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b3993-202">Obsolete.</span></span> <span data-ttu-id="b3993-203">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b3993-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="b3993-204">ICorDebugEval интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="b3993-205">Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="b3993-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="b3993-206">ICorDebugEval2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="b3993-207">Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="b3993-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="b3993-208">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="b3993-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="b3993-209">Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий исключения.</span><span class="sxs-lookup"><span data-stu-id="b3993-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="b3993-210">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-211">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="b3993-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="b3993-212">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="b3993-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="b3993-213">Интерфейс ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="b3993-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="b3993-214">Расширяет [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) интерфейс для предоставления сведений трассировки стека из управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="b3993-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="b3993-215">ICorDebugFrame интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="b3993-216">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="b3993-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="b3993-217">ICorDebugFrameEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="b3993-218">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="b3993-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-219">ICorDebugFunction интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="b3993-220">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="b3993-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="b3993-221">ICorDebugFunction2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="b3993-222">Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="b3993-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="b3993-223">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="b3993-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="b3993-224">Логически расширяет [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) интерфейс для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="b3993-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="b3993-225">ICorDebugFunctionBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="b3993-226">Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="b3993-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="b3993-227">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b3993-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="b3993-228">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="b3993-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="b3993-229">ICorDebugGenericValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="b3993-230">Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="b3993-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="b3993-231">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="b3993-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="b3993-232">Интерфейс ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="b3993-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="b3993-233">Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b3993-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="b3993-234">ICorDebugHandleValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="b3993-235">Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b3993-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="b3993-236">Интерфейс ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="b3993-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="b3993-237">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="b3993-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="b3993-238">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="b3993-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="b3993-239">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="b3993-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="b3993-240">ICorDebugHeapValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="b3993-241">Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b3993-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="b3993-242">Интерфейс1 ICorDebugHeapValue2</span><span class="sxs-lookup"><span data-stu-id="b3993-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="b3993-243">Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b3993-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="b3993-244">Интерфейс ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="b3993-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="b3993-245">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="b3993-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="b3993-246">Интерфейс ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="b3993-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="b3993-247">Представляет сегмент кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="b3993-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="b3993-248">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="b3993-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="b3993-249">Логически расширяет [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) смещений интерфейс предоставлять методы, возвращающие маркер для подписи локальной переменной функции и инструментированного профилировщиком промежуточного языка (IL), которые отображаются в исходный метод IL смещения.</span><span class="sxs-lookup"><span data-stu-id="b3993-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="b3993-250">ICorDebugILFrame интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="b3993-251">Предоставляет кадр стека кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="b3993-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="b3993-252">ICorDebugILFrame2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="b3993-253">Логическое расширение интерфейса `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="b3993-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="b3993-254">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="b3993-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="b3993-255">Предоставляет метод, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="b3993-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="b3993-256">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="b3993-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="b3993-257">Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="b3993-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="b3993-258">Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="b3993-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="b3993-259">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b3993-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="b3993-260">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b3993-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="b3993-261">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-262">ICorDebugInternalFrame интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="b3993-263">Задает типы кадров для отладчика.</span><span class="sxs-lookup"><span data-stu-id="b3993-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="b3993-264">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="b3993-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="b3993-265">Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="b3993-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="b3993-266">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="b3993-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="b3993-267">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="b3993-267">Provides information about a loaded module.</span></span> <span data-ttu-id="b3993-268">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-269">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="b3993-270">Предоставляет методы для обработки обратных вызовов отладчика.</span><span class="sxs-lookup"><span data-stu-id="b3993-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="b3993-271">ICorDebugManagedCallback2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="b3993-272">Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="b3993-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="b3993-273">Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="b3993-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="b3993-274">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="b3993-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="b3993-275">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="b3993-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="b3993-276">ICorDebugMDA-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="b3993-277">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="b3993-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="b3993-278">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="b3993-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="b3993-279">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="b3993-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="b3993-280">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-281">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="b3993-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="b3993-282">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="b3993-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="b3993-283">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-284">Icordebugmetadatalocator-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="b3993-285">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="b3993-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="b3993-286">ICorDebugModule интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="b3993-287">Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="b3993-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="b3993-288">ICorDebugModule2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="b3993-289">Служит логическим расширением интерфейса `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="b3993-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="b3993-290">Интерфейс ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="b3993-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="b3993-291">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="b3993-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="b3993-292">ICorDebugModuleBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="b3993-293">Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.</span><span class="sxs-lookup"><span data-stu-id="b3993-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="b3993-294">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="b3993-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="b3993-295">Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="b3993-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="b3993-296">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-297">ICorDebugModuleEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="b3993-298">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="b3993-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-299">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="b3993-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="b3993-300">Расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для поддержки целевых объектов изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="b3993-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="b3993-301">ICorDebugNativeFrame интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="b3993-302">Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.</span><span class="sxs-lookup"><span data-stu-id="b3993-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="b3993-303">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="b3993-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="b3993-304">Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".</span><span class="sxs-lookup"><span data-stu-id="b3993-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="b3993-305">ICorDebugObjectEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="b3993-306">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="b3993-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="b3993-307">ICorDebugObjectValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="b3993-308">Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.</span><span class="sxs-lookup"><span data-stu-id="b3993-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="b3993-309">Интерфейс1 ICorDebugObjectValue2</span><span class="sxs-lookup"><span data-stu-id="b3993-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="b3993-310">Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.</span><span class="sxs-lookup"><span data-stu-id="b3993-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="b3993-311">ICorDebugProcess интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="b3993-312">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="b3993-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="b3993-313">ICorDebugProcess2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="b3993-314">Логическое расширение интерфейса `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="b3993-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="b3993-315">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="b3993-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="b3993-316">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="b3993-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="b3993-317">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="b3993-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="b3993-318">Расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) локальный интерфейс для поддержки доступа к управляемой куче, для предоставления сведений о сборке мусора управляемых объектов и для определения, является ли отладчику загружать образы из приложения кэш образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="b3993-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="b3993-319">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="b3993-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="b3993-320">Логически расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) интерфейс, чтобы включить такие возможности как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей.</span><span class="sxs-lookup"><span data-stu-id="b3993-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="b3993-321">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-322">Интерфейс ICorDebugProcess7</span><span class="sxs-lookup"><span data-stu-id="b3993-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="b3993-323">Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="b3993-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="b3993-324">Интерфейс ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="b3993-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="b3993-325">Логически расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) интерфейс для включения или отключения определенных типов [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) обратных вызовов исключения.</span><span class="sxs-lookup"><span data-stu-id="b3993-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="b3993-326">ICorDebugProcessEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="b3993-327">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="b3993-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-328">ICorDebugReferenceValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="b3993-329">Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="b3993-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="b3993-330">ICorDebugRegisterSet-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="b3993-331">Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="b3993-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="b3993-332">ICorDebugRegisterSet2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="b3993-333">Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.</span><span class="sxs-lookup"><span data-stu-id="b3993-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="b3993-334">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="b3993-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="b3993-335">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="b3993-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="b3993-336">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="b3993-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="b3993-337">Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="b3993-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="b3993-338">Интерфейс ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="b3993-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="b3993-339">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="b3993-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="b3993-340">ICorDebugStackWalk-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="b3993-341">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="b3993-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="b3993-342">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b3993-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="b3993-343">Представляет сведения отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="b3993-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="b3993-344">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-345">ICorDebugStepper интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="b3993-346">Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.</span><span class="sxs-lookup"><span data-stu-id="b3993-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="b3993-347">Интерфейс1 ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="b3993-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="b3993-348">Предоставляет поддержку отладки "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="b3993-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="b3993-349">ICorDebugStepperEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="b3993-350">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="b3993-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-351">ICorDebugStringValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="b3993-352">Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.</span><span class="sxs-lookup"><span data-stu-id="b3993-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="b3993-353">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="b3993-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="b3993-354">Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="b3993-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="b3993-355">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-356">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="b3993-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="b3993-357">Логически расширяет [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) интерфейс для получения дополнительных символов отладки.</span><span class="sxs-lookup"><span data-stu-id="b3993-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="b3993-358">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-359">ICorDebugThread интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="b3993-360">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="b3993-360">Represents a thread in a process.</span></span> <span data-ttu-id="b3993-361">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="b3993-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="b3993-362">ICorDebugThread2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="b3993-363">Служит логическим расширением интерфейса `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b3993-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="b3993-364">Интерфейс ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="b3993-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="b3993-365">Предоставляет точку входа для [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) и соответствующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="b3993-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="b3993-366">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="b3993-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="b3993-367">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="b3993-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="b3993-368">ICorDebugThreadEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="b3993-369">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b3993-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-370">ICorDebugType интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="b3993-371">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="b3993-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="b3993-372">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="b3993-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="b3993-373">Интерфейс ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="b3993-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="b3993-374">Расширяет [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) интерфейс для извлечения идентификатора типа для базового типа или сложного типа (определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="b3993-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="b3993-375">ICorDebugTypeEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b3993-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="b3993-376">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b3993-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-377">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="b3993-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="b3993-378">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b3993-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="b3993-379">«ICorDebugValue»</span><span class="sxs-lookup"><span data-stu-id="b3993-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="b3993-380">Представляет значение для записи или чтения в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="b3993-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="b3993-381">«ICorDebugValue2»</span><span class="sxs-lookup"><span data-stu-id="b3993-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="b3993-382">Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b3993-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="b3993-383">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="b3993-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="b3993-384">Расширяет интерфейсы «ICorDebugValue» и «ICorDebugValue2» для обеспечения поддержки массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="b3993-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="b3993-385">«ICorDebugValueBreakpoint»</span><span class="sxs-lookup"><span data-stu-id="b3993-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="b3993-386">Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="b3993-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="b3993-387">«ICorDebugValueEnum»</span><span class="sxs-lookup"><span data-stu-id="b3993-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="b3993-388">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="b3993-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="b3993-389">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="b3993-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="b3993-390">Представляет локальную переменную или аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="b3993-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="b3993-391">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="b3993-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="b3993-392">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="b3993-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="b3993-393">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="b3993-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="b3993-394">Извлекает сведения отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="b3993-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="b3993-395">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-396">Интерфейс ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="b3993-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="b3993-397">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="b3993-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="b3993-398">**Этот параметр доступен только в .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="b3993-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="b3993-399">ICorPublish-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="b3993-400">Служит универсальным интерфейсом для процессов публикации.</span><span class="sxs-lookup"><span data-stu-id="b3993-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="b3993-401">ICorPublishAppDomain-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="b3993-402">Представляет и предоставляет информацию о домене приложения.</span><span class="sxs-lookup"><span data-stu-id="b3993-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="b3993-403">ICorPublishAppDomainEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="b3993-404">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b3993-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="b3993-405">ICorPublishEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="b3993-406">Служит абстрактной базой для перечислителей публикации.</span><span class="sxs-lookup"><span data-stu-id="b3993-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="b3993-407">ICorPublishProcess-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="b3993-408">Предоставляет методы, позволяющие получить доступ к сведениям о процессе.</span><span class="sxs-lookup"><span data-stu-id="b3993-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="b3993-409">ICorPublishProcessEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3993-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="b3993-410">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="b3993-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b3993-411">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b3993-411">Related Sections</span></span>  
 [<span data-ttu-id="b3993-412">Компонентные классы отладки</span><span class="sxs-lookup"><span data-stu-id="b3993-412">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="b3993-413">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="b3993-413">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="b3993-414">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b3993-414">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="b3993-415">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="b3993-415">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
