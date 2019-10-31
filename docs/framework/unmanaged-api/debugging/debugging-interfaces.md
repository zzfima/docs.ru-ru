---
title: Интерфейсы отладки
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 07b39666637628102e9ffafd2c059ba0d4b51b92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097198"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="9f738-102">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9f738-102">Debugging Interfaces</span></span>
<span data-ttu-id="9f738-103">В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="9f738-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f738-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="9f738-104">In This Section</span></span>  
 <span data-ttu-id="9f738-105">\ [интерфейса иклрдатаенуммеморирегионс](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)\</span></span>
 <span data-ttu-id="9f738-106">Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.</span><span class="sxs-lookup"><span data-stu-id="9f738-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="9f738-107">\ [интерфейса иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\</span></span>
 <span data-ttu-id="9f738-108">Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="9f738-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="9f738-109">\ [интерфейса ICLRDataTarget](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)\</span></span>
 <span data-ttu-id="9f738-110">Предоставляет методы для взаимодействия с целевым процессом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f738-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="9f738-111">\ [интерфейса ICLRDataTarget2](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\</span></span>
 <span data-ttu-id="9f738-112">Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="9f738-113">\ [интерфейса метод iclrdatatarget3](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\</span></span>
 <span data-ttu-id="9f738-114">Подкласс [ICLRDataTarget2](iclrdatatarget2-interface.md) , предоставляющий доступ к сведениям об исключениях.</span><span class="sxs-lookup"><span data-stu-id="9f738-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="9f738-115">\ [интерфейса ICLRDebugging](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-115">[ICLRDebugging Interface](iclrdebugging-interface.md)\</span></span>
 <span data-ttu-id="9f738-116">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="9f738-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="9f738-117">\ [интерфейса иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)\</span></span>
 <span data-ttu-id="9f738-118">Включает метод [метода ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , который получает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки, относящиеся к конкретной версии среды CLR, по запросу.</span><span class="sxs-lookup"><span data-stu-id="9f738-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="9f738-119">\ [интерфейса иклрметадаталокатор](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)\</span></span>
 <span data-ttu-id="9f738-120">Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="9f738-121">[Интерфейс ICorDebug](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="9f738-122">Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="9f738-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="9f738-123">\ [интерфейса ICorDebugAppDomain](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)\</span></span>
 <span data-ttu-id="9f738-124">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="9f738-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="9f738-125">\ [интерфейса ICorDebugAppDomain2](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)\</span></span>
 <span data-ttu-id="9f738-126">Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef.</span><span class="sxs-lookup"><span data-stu-id="9f738-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="9f738-127">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="9f738-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="9f738-128">\ [интерфейса ICorDebugAppDomain3](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)\</span></span>
 <span data-ttu-id="9f738-129">Предоставляет методы для работы с типами среда выполнения Windows в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="9f738-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="9f738-130">Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="9f738-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="9f738-131">\ [интерфейса ICorDebugAppDomain4](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\</span></span>
 <span data-ttu-id="9f738-132">Логически расширяет интерфейс [ICorDebugAppDomain](icordebugappdomain-interface.md) для получения управляемого объекта из вызываемой оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="9f738-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="9f738-133">\ [интерфейса икордебугаппдомаиненум](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-134">Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="9f738-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="9f738-135">\ [интерфейса ICorDebugArrayValue](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-136">Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="9f738-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="9f738-137">\ [интерфейса ICorDebugAssembly](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)\</span></span>
 <span data-ttu-id="9f738-138">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="9f738-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="9f738-139">\ [интерфейса ICorDebugAssembly2](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)\</span></span>
 <span data-ttu-id="9f738-140">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="9f738-140">Represents an assembly.</span></span> <span data-ttu-id="9f738-141">Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="9f738-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="9f738-142">\ [интерфейса ICorDebugAssembly3](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)\</span></span>
 <span data-ttu-id="9f738-143">Логически расширяет интерфейс [ICorDebugAssembly](icordebugassembly-interface.md) , чтобы обеспечить поддержку для сборок контейнеров и содержащихся в них сборок.</span><span class="sxs-lookup"><span data-stu-id="9f738-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="9f738-144">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-145">\ [интерфейса ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-146">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="9f738-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="9f738-147">\ [интерфейса икордебугблоккингобжектенум](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-148">Предоставляет перечислитель для списка структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="9f738-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="9f738-149">\ [интерфейса икордебугбоксвалуе](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-150">Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.</span><span class="sxs-lookup"><span data-stu-id="9f738-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="9f738-151">\ [интерфейса икордебугбреакпоинт](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)\</span></span>
 <span data-ttu-id="9f738-152">Представляет точку останова в функции или контрольную точку для значения.</span><span class="sxs-lookup"><span data-stu-id="9f738-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="9f738-153">\ [интерфейса ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-154">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9f738-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="9f738-155">\ [интерфейса ICorDebugChain](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-155">[ICorDebugChain Interface](icordebugchain-interface.md)\</span></span>
 <span data-ttu-id="9f738-156">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="9f738-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="9f738-157">\ [интерфейса икордебугчаиненум](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-158">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="9f738-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="9f738-159">\ [интерфейса ICorDebugClass](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-159">[ICorDebugClass Interface](icordebugclass-interface.md)\</span></span>
 <span data-ttu-id="9f738-160">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="9f738-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="9f738-161">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="9f738-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="9f738-162">\ [интерфейса ICorDebugClass2](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)\</span></span>
 <span data-ttu-id="9f738-163">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="9f738-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="9f738-164">Этот интерфейс расширяет интерфейс `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="9f738-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="9f738-165">[Интерфейс ICorDebugCode](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="9f738-166">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="9f738-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="9f738-167">\ [интерфейса ICorDebugCode2](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)\</span></span>
 <span data-ttu-id="9f738-168">Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="9f738-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="9f738-169">\ [интерфейса ICorDebugCode3](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)\</span></span>
 <span data-ttu-id="9f738-170">Предоставляет метод, расширяющий интерфейс [ICorDebugCode](icordebugcode-interface1.md) и [ICorDebugCode2](icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="9f738-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="9f738-171">\ [интерфейса ICorDebugCode4](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)\</span></span>
 <span data-ttu-id="9f738-172">Предоставляет метод, позволяющий отладчику перечислить локальные переменные и аргументы в функции.</span><span class="sxs-lookup"><span data-stu-id="9f738-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="9f738-173">\ [интерфейса икордебугкодинум](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-174">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="9f738-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="9f738-175">\ [интерфейса икордебугкомобжектвалуе](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-176">Предоставляет методы для получения кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9f738-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="9f738-177">\ [интерфейса икордебугконтекст](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-177">[ICorDebugContext Interface](icordebugcontext-interface.md)\</span></span>
 <span data-ttu-id="9f738-178">Представляет объект контекста.</span><span class="sxs-lookup"><span data-stu-id="9f738-178">Represents a context object.</span></span> <span data-ttu-id="9f738-179">Этот интерфейс еще не реализован.</span><span class="sxs-lookup"><span data-stu-id="9f738-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="9f738-180">\ [интерфейса ICorDebugController](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-180">[ICorDebugController Interface](icordebugcontroller-interface.md)\</span></span>
 <span data-ttu-id="9f738-181">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="9f738-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="9f738-182">\ [интерфейса ICorDebugDataTarget](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)\</span></span>
 <span data-ttu-id="9f738-183">Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="9f738-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="9f738-184">\ [интерфейса метод icordebugdatatarget2](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)\</span></span>
 <span data-ttu-id="9f738-185">Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f738-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="9f738-186">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-187">\ [интерфейса ICorDebugDataTarget3](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)\</span></span>
 <span data-ttu-id="9f738-188">Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) , чтобы предоставить сведения о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="9f738-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="9f738-189">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-190">\ [интерфейса ICorDebugDebugEvent](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)\</span></span>
 <span data-ttu-id="9f738-191">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="9f738-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="9f738-192">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-193">\ [интерфейса икордебужедитандконтинуирроринфо](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\</span></span>
 <span data-ttu-id="9f738-194">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9f738-194">Obsolete.</span></span> <span data-ttu-id="9f738-195">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9f738-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="9f738-196">\ [интерфейса метод icordebugeditandcontinuesnapshot](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)\</span></span>
 <span data-ttu-id="9f738-197">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9f738-197">Obsolete.</span></span> <span data-ttu-id="9f738-198">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9f738-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="9f738-199">\ [интерфейса ICorDebugEnum](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)\</span></span>
 <span data-ttu-id="9f738-200">Служит абстрактным базовым интерфейсом для перечислителей отладки.</span><span class="sxs-lookup"><span data-stu-id="9f738-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="9f738-201">\ [интерфейса ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-202">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9f738-202">Obsolete.</span></span> <span data-ttu-id="9f738-203">Не следует использовать данный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9f738-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="9f738-204">\ [интерфейса ICorDebugEval](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-204">[ICorDebugEval Interface](icordebugeval-interface.md)\</span></span>
 <span data-ttu-id="9f738-205">Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="9f738-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="9f738-206">\ [интерфейса ICorDebugEval2](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)\</span></span>
 <span data-ttu-id="9f738-207">Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="9f738-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="9f738-208">\ [интерфейса икордебужексцептиондебужевент](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)\</span></span>
 <span data-ttu-id="9f738-209">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключения.</span><span class="sxs-lookup"><span data-stu-id="9f738-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="9f738-210">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-211">\ [интерфейса ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-212">Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="9f738-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="9f738-213">\ [интерфейса ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-214">Расширяет интерфейс [ICorDebugObjectValue](icordebugobjectvalue-interface.md) для предоставления сведений о трассировке стека из управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="9f738-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="9f738-215">[Интерфейс ICorDebugFrame](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="9f738-216">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="9f738-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="9f738-217">\ [интерфейса ICorDebugFrameEnum](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-218">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="9f738-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="9f738-219">[Интерфейс ICorDebugFunction](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="9f738-220">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="9f738-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="9f738-221">\ [интерфейса ICorDebugFunction2](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)\</span></span>
 <span data-ttu-id="9f738-222">Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="9f738-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="9f738-223">\ [интерфейса ICorDebugFunction3](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)\</span></span>
 <span data-ttu-id="9f738-224">Логически расширяет интерфейс [ICorDebugFunction](icordebugfunction-interface1.md) , чтобы предоставить доступ к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="9f738-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="9f738-225">\ [интерфейса ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)\</span></span>
 <span data-ttu-id="9f738-226">Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.</span><span class="sxs-lookup"><span data-stu-id="9f738-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="9f738-227">\ [интерфейса ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-228">Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="9f738-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="9f738-229">\ [интерфейса ICorDebugGenericValue](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-230">Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="9f738-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="9f738-231">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="9f738-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="9f738-232">\ [интерфейса ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-233">Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="9f738-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="9f738-234">\ [интерфейса ICorDebugHandleValue](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-235">Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="9f738-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="9f738-236">\ [интерфейса икордебугхеапенум](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-237">Предоставляет перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="9f738-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="9f738-238">\ [интерфейса икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-239">Предоставляет перечислитель для областей памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="9f738-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="9f738-240">\ [интерфейса ICorDebugHeapValue](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-241">Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f738-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="9f738-242">\ [интерфейса ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)\</span></span>
 <span data-ttu-id="9f738-243">Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9f738-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="9f738-244">\ [интерфейса ICorDebugHeapValue3](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)\</span></span>
 <span data-ttu-id="9f738-245">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="9f738-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="9f738-246">\ [интерфейса икордебугилкоде](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)\</span></span>
 <span data-ttu-id="9f738-247">Представляет сегмент кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="9f738-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="9f738-248">\ [интерфейса ICorDebugILCode2](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)\</span></span>
 <span data-ttu-id="9f738-249">Логически расширяет интерфейс [икордебугилкоде](icordebugilcode-interface.md) , чтобы предоставить методы, которые возвращают маркер для сигнатуры локальной переменной функции и сопоставляют смещенные промежуточные языки (IL) профилировщика с исходными смещениями Il метода.</span><span class="sxs-lookup"><span data-stu-id="9f738-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="9f738-250">\ [интерфейса ICorDebugILFrame](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)\</span></span>
 <span data-ttu-id="9f738-251">Предоставляет кадр стека кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="9f738-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="9f738-252">\ [интерфейса ICorDebugILFrame2](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)\</span></span>
 <span data-ttu-id="9f738-253">Логическое расширение интерфейса `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="9f738-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="9f738-254">\ [интерфейса ICorDebugILFrame3](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)\</span></span>
 <span data-ttu-id="9f738-255">Предоставляет метод, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="9f738-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="9f738-256">\ [интерфейса ICorDebugILFrame4](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)\</span></span>
 <span data-ttu-id="9f738-257">Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="9f738-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="9f738-258">Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="9f738-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="9f738-259">\ [интерфейса ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)\</span></span>
 <span data-ttu-id="9f738-260">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9f738-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="9f738-261">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-262">\ [интерфейса ICorDebugInternalFrame](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)\</span></span>
 <span data-ttu-id="9f738-263">Задает типы кадров для отладчика.</span><span class="sxs-lookup"><span data-stu-id="9f738-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="9f738-264">\ [интерфейса ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)\</span></span>
 <span data-ttu-id="9f738-265">Предоставляет сведения о внутренних кадрах, включая адрес стека и расположение по отношению к объектам [ICorDebugFrame](icordebugframe-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f738-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="9f738-266">\ [интерфейса икордебуглоадедмодуле](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)\</span></span>
 <span data-ttu-id="9f738-267">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="9f738-267">Provides information about a loaded module.</span></span> <span data-ttu-id="9f738-268">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-269">\ [интерфейса ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)\</span></span>
 <span data-ttu-id="9f738-270">Предоставляет методы для обработки обратных вызовов отладчика.</span><span class="sxs-lookup"><span data-stu-id="9f738-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="9f738-271">\ [интерфейса ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\</span></span>
 <span data-ttu-id="9f738-272">Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="9f738-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="9f738-273">Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="9f738-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="9f738-274">\ [интерфейса ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\</span></span>
 <span data-ttu-id="9f738-275">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="9f738-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="9f738-276">\ [интерфейса ICorDebugMDA](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-276">[ICorDebugMDA Interface](icordebugmda-interface.md)\</span></span>
 <span data-ttu-id="9f738-277">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="9f738-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="9f738-278">\ [интерфейса икордебугмеморибуффер](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)\</span></span>
 <span data-ttu-id="9f738-279">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="9f738-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="9f738-280">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-281">\ [интерфейса икордебугмержедассемблирекорд](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)\</span></span>
 <span data-ttu-id="9f738-282">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="9f738-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="9f738-283">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-284">\ [интерфейса икордебугметадаталокатор](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)\</span></span>
 <span data-ttu-id="9f738-285">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="9f738-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="9f738-286">\ [интерфейса ICorDebugModule](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-286">[ICorDebugModule Interface](icordebugmodule-interface.md)\</span></span>
 <span data-ttu-id="9f738-287">Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="9f738-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="9f738-288">\ [интерфейса ICorDebugModule2](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)\</span></span>
 <span data-ttu-id="9f738-289">Служит логическим расширением интерфейса `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="9f738-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="9f738-290">\ [интерфейса метод icordebugmodule3](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)\</span></span>
 <span data-ttu-id="9f738-291">Создает средство чтения символов для динамического модуля.</span><span class="sxs-lookup"><span data-stu-id="9f738-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="9f738-292">\ [интерфейса икордебугмодулебреакпоинт](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)\</span></span>
 <span data-ttu-id="9f738-293">Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.</span><span class="sxs-lookup"><span data-stu-id="9f738-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="9f738-294">\ [интерфейса икордебугмодуледебужевент](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)\</span></span>
 <span data-ttu-id="9f738-295">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="9f738-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="9f738-296">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-297">\ [интерфейса икордебугмодулинум](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-298">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="9f738-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="9f738-299">\ [интерфейса икордебугмутабледататаржет](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)\</span></span>
 <span data-ttu-id="9f738-300">Расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) для поддержки целевых объектов данных.</span><span class="sxs-lookup"><span data-stu-id="9f738-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="9f738-301">\ [интерфейса ICorDebugNativeFrame](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)\</span></span>
 <span data-ttu-id="9f738-302">Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.</span><span class="sxs-lookup"><span data-stu-id="9f738-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="9f738-303">\ [интерфейса ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)\</span></span>
 <span data-ttu-id="9f738-304">Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".</span><span class="sxs-lookup"><span data-stu-id="9f738-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="9f738-305">\ [интерфейса икордебугобжектенум](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-306">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="9f738-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="9f738-307">\ [интерфейса ICorDebugObjectValue](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-308">Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.</span><span class="sxs-lookup"><span data-stu-id="9f738-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="9f738-309">\ [интерфейса ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)\</span></span>
 <span data-ttu-id="9f738-310">Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.</span><span class="sxs-lookup"><span data-stu-id="9f738-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="9f738-311">\ [интерфейса ICorDebugProcess](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)\</span></span>
 <span data-ttu-id="9f738-312">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="9f738-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="9f738-313">\ [интерфейса ICorDebugProcess2](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)\</span></span>
 <span data-ttu-id="9f738-314">Логическое расширение интерфейса `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="9f738-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="9f738-315">\ [интерфейса ICorDebugProcess3](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)\</span></span>
 <span data-ttu-id="9f738-316">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="9f738-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="9f738-317">\ [интерфейса ICorDebugProcess4](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)\</span></span>
 <span data-ttu-id="9f738-318">Обеспечивает поддержку управления выполнением в процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="9f738-319">\ [интерфейса метод ICorDebugProcess5](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)\</span></span>
 <span data-ttu-id="9f738-320">Расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) для поддержки доступа к управляемой куче, предоставляет сведения о сборке мусора управляемых объектов и определяет, загружает ли отладчик изображения из локального кэша образов в машинном код.</span><span class="sxs-lookup"><span data-stu-id="9f738-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="9f738-321">\ [интерфейса ICorDebugProcess6](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)\</span></span>
 <span data-ttu-id="9f738-322">Логически расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) , позволяя выполнять такие функции, как декодирование управляемых событий отладки, которые кодируются в событиях отладки машинного кода и разбиении виртуального модуля.</span><span class="sxs-lookup"><span data-stu-id="9f738-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="9f738-323">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-324">\ [интерфейса ICorDebugProcess7](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)\</span></span>
 <span data-ttu-id="9f738-325">Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="9f738-326">\ [интерфейса ICorDebugProcess8](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)\</span></span>
 <span data-ttu-id="9f738-327">Логически расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) , чтобы включать или отключать определенные типы обратных вызовов исключений [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f738-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="9f738-328">\ [интерфейса икордебугпроцессенум](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-329">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="9f738-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="9f738-330">\ [интерфейса ICorDebugReferenceValue](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-331">Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="9f738-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="9f738-332">\ [интерфейса ICorDebugRegisterSet](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)\</span></span>
 <span data-ttu-id="9f738-333">Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="9f738-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="9f738-334">\ [интерфейса ICorDebugRegisterSet2](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)\</span></span>
 <span data-ttu-id="9f738-335">Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.</span><span class="sxs-lookup"><span data-stu-id="9f738-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="9f738-336">\ [интерфейса метод icordebugremote](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-336">[ICorDebugRemote Interface](icordebugremote-interface.md)\</span></span>
 <span data-ttu-id="9f738-337">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="9f738-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="9f738-338">\ [интерфейса ICorDebugRemoteTarget](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)\</span></span>
 <span data-ttu-id="9f738-339">Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="9f738-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="9f738-340">\ [интерфейса икордебугрунтимеунвиндаблефраме](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)\</span></span>
 <span data-ttu-id="9f738-341">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="9f738-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="9f738-342">\ [интерфейса икордебугстакквалк](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)\</span></span>
 <span data-ttu-id="9f738-343">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="9f738-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="9f738-344">\ [интерфейса икордебугстатикфиелдсимбол](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)\</span></span>
 <span data-ttu-id="9f738-345">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="9f738-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="9f738-346">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-347">[Интерфейс ICorDebugStepper](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="9f738-348">Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.</span><span class="sxs-lookup"><span data-stu-id="9f738-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="9f738-349">\ [интерфейса ICorDebugStepper2](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)\</span></span>
 <span data-ttu-id="9f738-350">Предоставляет поддержку отладки "Только мой код".</span><span class="sxs-lookup"><span data-stu-id="9f738-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="9f738-351">\ [интерфейса икордебугстепперенум](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-352">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="9f738-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="9f738-353">\ [интерфейса ICorDebugStringValue](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-354">Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.</span><span class="sxs-lookup"><span data-stu-id="9f738-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="9f738-355">\ [интерфейса метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)\</span></span>
 <span data-ttu-id="9f738-356">Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="9f738-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="9f738-357">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-358">\ [интерфейса ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)\</span></span>
 <span data-ttu-id="9f738-359">Логически расширяет интерфейс [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) для получения дополнительных сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="9f738-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="9f738-360">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-361">[Интерфейс ICorDebugThread](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="9f738-362">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-362">Represents a thread in a process.</span></span> <span data-ttu-id="9f738-363">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="9f738-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="9f738-364">\ [интерфейса ICorDebugThread2](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)\</span></span>
 <span data-ttu-id="9f738-365">Служит логическим расширением интерфейса `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="9f738-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="9f738-366">\ [интерфейса ICorDebugThread3](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)\</span></span>
 <span data-ttu-id="9f738-367">Предоставляет точку входа для [икордебугстакквалк](icordebugstackwalk-interface.md) и соответствующих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="9f738-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="9f738-368">\ [интерфейса ICorDebugThread4](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)\</span></span>
 <span data-ttu-id="9f738-369">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="9f738-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="9f738-370">\ [интерфейса икордебугсреаденум](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)\</span></span>
 <span data-ttu-id="9f738-371">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="9f738-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="9f738-372">\ [интерфейса ICorDebugType](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-372">[ICorDebugType Interface](icordebugtype-interface.md)\</span></span>
 <span data-ttu-id="9f738-373">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="9f738-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="9f738-374">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="9f738-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="9f738-375">\ [интерфейса ICorDebugType2](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)\</span></span>
 <span data-ttu-id="9f738-376">Расширяет интерфейс [ICorDebugType](icordebugtype-interface.md) для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.</span><span class="sxs-lookup"><span data-stu-id="9f738-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="9f738-377">\ [интерфейса ICorDebugTypeEnum](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-378">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="9f738-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="9f738-379">\ [интерфейса икордебугунманажедкаллбакк](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)\</span></span>
 <span data-ttu-id="9f738-380">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9f738-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="9f738-381">\ [ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-381">[ICorDebugValue](icordebugvalue-interface.md)\</span></span>
 <span data-ttu-id="9f738-382">Представляет значение для записи или чтения в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="9f738-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="9f738-384">Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="9f738-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="9f738-385">\ [интерфейса ICorDebugValue3](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)\</span></span>
 <span data-ttu-id="9f738-386">Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="9f738-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="9f738-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="9f738-388">Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="9f738-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="9f738-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="9f738-390">Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="9f738-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="9f738-391">\ [интерфейса ICorDebugVariableHome](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)\</span></span>
 <span data-ttu-id="9f738-392">Представляет локальную переменную или аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="9f738-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="9f738-393">\ [интерфейса ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-394">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="9f738-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="9f738-395">\ [интерфейса ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)\</span></span>
 <span data-ttu-id="9f738-396">Извлекает сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="9f738-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="9f738-397">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-398">\ [интерфейса ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)\</span></span>
 <span data-ttu-id="9f738-399">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="9f738-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="9f738-400">**Доступно только на .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="9f738-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="9f738-401">\ [интерфейса ICorPublish](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-401">[ICorPublish Interface](icorpublish-interface.md)\</span></span>
 <span data-ttu-id="9f738-402">Служит универсальным интерфейсом для процессов публикации.</span><span class="sxs-lookup"><span data-stu-id="9f738-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="9f738-403">\ [интерфейса ICorPublishAppDomain](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)\</span></span>
 <span data-ttu-id="9f738-404">Представляет и предоставляет информацию о домене приложения.</span><span class="sxs-lookup"><span data-stu-id="9f738-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="9f738-405">\ [интерфейса ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-406">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.</span><span class="sxs-lookup"><span data-stu-id="9f738-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="9f738-407">\ [интерфейса ICorPublishEnum](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-408">Служит абстрактной базой для перечислителей публикации.</span><span class="sxs-lookup"><span data-stu-id="9f738-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="9f738-409">\ [интерфейса ICorPublishProcess](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)\</span></span>
 <span data-ttu-id="9f738-410">Предоставляет методы, позволяющие получить доступ к сведениям о процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="9f738-411">\ [интерфейса ICorPublishProcessEnum](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\</span></span>
 <span data-ttu-id="9f738-412">Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="9f738-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="9f738-413">\ [интерфейса исосдаЦинтерфаце](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)\</span></span>
 <span data-ttu-id="9f738-414">Предоставляет вспомогательные методы для доступа к данным из `SOS`.</span><span class="sxs-lookup"><span data-stu-id="9f738-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="9f738-415">\ [интерфейса иксклрдатамесоддефинитион](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)\</span></span>
 <span data-ttu-id="9f738-416">Предоставляет методы для запроса сведений об определении метода.</span><span class="sxs-lookup"><span data-stu-id="9f738-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="9f738-417">\ [интерфейса иксклрдатамесодинстанце](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)\</span></span>
 <span data-ttu-id="9f738-418">Предоставляет методы для запроса сведений об экземпляре метода.</span><span class="sxs-lookup"><span data-stu-id="9f738-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="9f738-419">\ [интерфейса иксклрдатамодуле](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)\</span></span>
 <span data-ttu-id="9f738-420">Предоставляет методы для запроса сведений о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="9f738-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="9f738-421">\ [интерфейса иксклрдатапроцесс](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\</span></span>
 <span data-ttu-id="9f738-422">Предоставляет методы для запроса сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="9f738-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="9f738-423">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9f738-423">Related Sections</span></span>  
 <span data-ttu-id="9f738-424">[Коклассы отладки](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="9f738-425">[Отладка глобальных статических функций](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="9f738-426">\ [перечисления отладки](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-426">[Debugging Enumerations](debugging-enumerations.md)\</span></span>
 <span data-ttu-id="9f738-427">[Отладка структур](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="9f738-427">[Debugging Structures](debugging-structures.md)</span></span>\
