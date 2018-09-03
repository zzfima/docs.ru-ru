---
title: Миграция приложения для магазина Windows в машинный код .NET
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3909855db109938794fad3e0afc99d492009b81c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43461791"
---
# <a name="migrating-your-windows-store-app-to-net-native"></a><span data-ttu-id="a9e6b-102">Миграция приложения для магазина Windows в машинный код .NET</span><span class="sxs-lookup"><span data-stu-id="a9e6b-102">Migrating Your Windows Store App to .NET Native</span></span>
<span data-ttu-id="a9e6b-103">.NET native обеспечивает статическую компиляцию приложений в Windows Store или на компьютере разработчика.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-103">.NET Native provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="a9e6b-104">В отличие от динамической компиляции, выполняемой JIT-компилятором для приложений магазина Windows или [Генератором машинных образов (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="a9e6b-105">Несмотря на различия, .NET Native пытается поддерживать совместимость с [.NET для Windows Store apps](https://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-105">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](https://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span></span> <span data-ttu-id="a9e6b-106">В большинстве случаев вещи, которые работают в приложениях .NET для Windows Store также работать с .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-106">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="a9e6b-107">Тем не менее в некоторых случаях могут произойти изменения поведения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="a9e6b-108">В этом документе рассматриваются различия между стандартных приложениях .NET для Windows Store и .NET Native в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-108">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>  
  
-   [<span data-ttu-id="a9e6b-109">Общие различия среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a9e6b-109">General runtime differences</span></span>](#Runtime)  
  
-   [<span data-ttu-id="a9e6b-110">Различия динамического программирования</span><span class="sxs-lookup"><span data-stu-id="a9e6b-110">Dynamic programming differences</span></span>](#Dynamic)  
  
-   [<span data-ttu-id="a9e6b-111">Другие различия, связанным с отражением</span><span class="sxs-lookup"><span data-stu-id="a9e6b-111">Other reflection-related differences</span></span>](#Reflection)  
  
-   [<span data-ttu-id="a9e6b-112">Неподдерживаемые сценарии и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a9e6b-112">Unsupported scenarios and APIs</span></span>](#Unsupported)  
  
-   [<span data-ttu-id="a9e6b-113">Различия в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a9e6b-113">Visual Studio differences</span></span>](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a><span data-ttu-id="a9e6b-114">Общие различия среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a9e6b-114">General runtime differences</span></span>  
  
-   <span data-ttu-id="a9e6b-115">Исключения, такие как <xref:System.TypeLoadException>, создаваемых компилятором JIT, при запуске приложения в общеязыковой среды выполнения (CLR) обычно привести к ошибкам во время компиляции при обработке машинного кода .NET.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>  
  
-   <span data-ttu-id="a9e6b-116">Не вызывайте метод <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> из потока пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="a9e6b-117">Это может привести к взаимоблокировке в среде .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-117">This can result in a deadlock on .NET Native.</span></span>  
  
-   <span data-ttu-id="a9e6b-118">Не полагайтесь на порядок вызова конструктора статического класса.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="a9e6b-119">В .NET Native порядок вызова отличается от порядка в стандартной среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-119">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="a9e6b-120">(Даже со стандартной средой выполнения, не следует рассчитывать на порядок выполнения конструкторов статических классов.)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>  
  
-   <span data-ttu-id="a9e6b-121">Бесконечный цикл без вызовов (например, `while(true);`) на любом потоке может привести к остановке приложения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="a9e6b-122">Аналогичным образом, большие или бесконечные ожидания могут также привести приложение к остановке.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>  
  
-   <span data-ttu-id="a9e6b-123">Некоторые циклы универсальной инициализации не создают исключения в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-123">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="a9e6b-124">Например, следующий код создает исключение <xref:System.TypeLoadException> исключений в стандартной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="a9e6b-125">В .NET Native нет.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-125">In .NET Native, it doesn't.</span></span>  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   <span data-ttu-id="a9e6b-126">В некоторых случаях .NET Native предоставляет различные реализации библиотеки классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-126">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="a9e6b-127">Объект, возвращенный из метода, всегда будет реализовать члены возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="a9e6b-128">Тем не менее, поскольку его резервная реализация отличается, может оказаться невозможным привести его к тому же набору типов, как это можно было бы сделать на платформах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="a9e6b-129">Например, в некоторых случаях может оказаться невозможным привести объект интерфейса <xref:System.Collections.Generic.IEnumerable%601>, возвращенный такими методами как <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> или <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType>, к `T[]`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>  
  
-   <span data-ttu-id="a9e6b-130">Кэш WinInet не включен по умолчанию в приложениях .NET для Windows Store, но это в среде .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="a9e6b-131">Это повышает производительность, но сказывается на рабочем наборе.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="a9e6b-132">Не требуется никаких действий разработчика.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-132">No developer action is necessary.</span></span>  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a><span data-ttu-id="a9e6b-133">Различия динамического программирования</span><span class="sxs-lookup"><span data-stu-id="a9e6b-133">Dynamic programming differences</span></span>  
 <span data-ttu-id="a9e6b-134">.NET native статически связывает код из платформы .NET Framework, чтобы сделать код локальным для достижения максимальной производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-134">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="a9e6b-135">Тем не менее, двоичные размеры должны оставаться небольшими, поэтому не удается подключить всю платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="a9e6b-136">.NET Native компилятор разрешает это ограничение с помощью редуктора зависимостей, который удаляет ссылки на неиспользуемый код.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-136">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="a9e6b-137">Тем не менее .NET Native не может поддерживать или создавать некоторые сведения о типе и код, когда эти сведения не могут быть определены статически во время компиляции, но вместо этого извлекаются динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-137">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>  
  
 <span data-ttu-id="a9e6b-138">.NET native включает отражение и динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-138">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="a9e6b-139">При этом, не все типы могут быть помечены для отражения, так как это сделает размер созданного кода слишком большим (особенно потому, что поддерживается отражение на общедоступных API в платформе .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="a9e6b-140">.NET Native компилятор делает интеллектуальный Выбор о том, какие типы должны поддерживать отражение, и он сохраняет метаданные и создает код только для этих типов.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-140">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>  
  
 <span data-ttu-id="a9e6b-141">Например, привязка данных требует, чтобы приложение обеспечивало сопоставление имен свойств с функциями.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="a9e6b-142">В приложениях .NET для магазина Windows среда CLR автоматически использует отражение для обеспечения этой возможности для управляемых и общедоступных собственных типов.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="a9e6b-143">В .NET Native компилятор автоматически включает метаданные для типов, к которым осуществляется привязка данных.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-143">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>  
  
 <span data-ttu-id="a9e6b-144">.NET Native, компилятор может также обрабатывать часто используемые универсальные типы, такие <xref:System.Collections.Generic.List%601> и <xref:System.Collections.Generic.Dictionary%602>, которые работают, не требуя подсказок или директив.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-144">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="a9e6b-145">Ключевое слово [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) также поддерживается в заданных пределах.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-145">The [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) keyword is also supported within certain limits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9e6b-146">Следует тщательно протестировать все пути динамического кода, при переносе приложения в машинный код .NET.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-146">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>  
  
 <span data-ttu-id="a9e6b-147">Конфигурация по умолчанию для машинного кода .NET достаточно для большинства разработчиков, но некоторым разработчикам может потребоваться точная настройка своих конфигураций с помощью директив среды выполнения (. rd.xml) файла.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-147">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="a9e6b-148">Кроме того в некоторых случаях компилятор .NET Native не удается определить, какие метаданные должны быть доступны для отражения и опирается на подсказки, особенно в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-148">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>  
  
-   <span data-ttu-id="a9e6b-149">Некоторые конструкции, такие как <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> и <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> не удается определить статически.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>  
  
-   <span data-ttu-id="a9e6b-150">Поскольку компилятор не может определить экземпляры, универсальный тип, который требуется отразить на нем должен быть указан директивами среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="a9e6b-151">Это необходимо не только потому, что весь код должен быть включен, но так же и вследствие того, что отражение на универсальных типах могут образовывать бесконечный цикл (например, при вызове универсального метода для универсального типа).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9e6b-152">Директивы среды выполнения определяются в файле директив среды выполнения (. rd.xml).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="a9e6b-153">Общие сведения об использовании этого файла см. в разделе [Приступая к работе](../../../docs/framework/net-native/getting-started-with-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-153">For general information about using this file, see [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md).</span></span> <span data-ttu-id="a9e6b-154">Сведения о директивах среды выполнения см. в разделе [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
 <span data-ttu-id="a9e6b-155">.NET native также включает средства профилирования, помогающие определить, какие типы, не входящие в набор по умолчанию, должны поддерживать отражения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-155">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a><span data-ttu-id="a9e6b-156">Другие различия, связанным с отражением</span><span class="sxs-lookup"><span data-stu-id="a9e6b-156">Other reflection-related differences</span></span>  
 <span data-ttu-id="a9e6b-157">Существует ряд других отдельных связанным с отражением различий в поведении между приложениями .NET для Windows Store и .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>  
  
 <span data-ttu-id="a9e6b-158">В машинный код .NET:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-158">In .NET Native:</span></span>  
  
-   <span data-ttu-id="a9e6b-159">Отражение закрытых типов и членов в библиотеке классов платформы .NET Framework не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="a9e6b-160">Тем не менее, можно выполнить отражение на собственных закрытых типах и членах, а также типах и членах библиотек сторонних поставщиков.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>  
  
-   <span data-ttu-id="a9e6b-161">Свойство <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> корректно возвращает `false` для объекта <xref:System.Reflection.ParameterInfo>, который представляет возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="a9e6b-162">В приложениях .NET для магазина Windows, будет возвращено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="a9e6b-163">Промежуточный язык (IL) не поддерживает это непосредственно, и интерпретация выполняется языком.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>  
  
-   <span data-ttu-id="a9e6b-164">Открытые члены на структурах <xref:System.RuntimeFieldHandle> и <xref:System.RuntimeMethodHandle> не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="a9e6b-165">Эти типы поддерживаются только для LINQ, деревьев выражений и инициализации статического массива.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>  
  
-   <span data-ttu-id="a9e6b-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType>и <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> включают скрытые члены в базовых классах и поэтому могут переопределяться без явного переопределения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="a9e6b-167">Это также справедливо для других [RuntimeReflectionExtensions.GetRuntime\*](https://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) методы.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](https://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) methods.</span></span>  
  
-   <span data-ttu-id="a9e6b-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>и <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> не дают сбой при попытке создать определенные комбинации (например, массив byrefs).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of byrefs).</span></span>  
  
-   <span data-ttu-id="a9e6b-169">Нельзя использовать отражение для вызова членов, которые содержат параметры указателя.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-169">You can't use reflection to invoke members that have pointer parameters.</span></span>  
  
-   <span data-ttu-id="a9e6b-170">Чтобы получить или задать поле указателя, нельзя использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-170">You can't use reflection to get or set a pointer field.</span></span>  
  
-   <span data-ttu-id="a9e6b-171">Если неверное количество аргументов и тип одного из аргументов неверен, .NET Native вызывает <xref:System.ArgumentException> вместо <xref:System.Reflection.TargetParameterCountException>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-171">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>  
  
-   <span data-ttu-id="a9e6b-172">Обычно двоичная сериализация исключений не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="a9e6b-173">В результате несериализуемые объекты могут быть добавлены к словарю <xref:System.Exception.Data%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="a9e6b-174">Неподдерживаемые сценарии и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a9e6b-174">Unsupported scenarios and APIs</span></span>  
 <span data-ttu-id="a9e6b-175">В следующих разделах перечислены неподдерживаемые сценарии и интерфейсы API для общей разработки, взаимодействия и таких технологий, как HTTPClient и Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="a9e6b-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>  
  
-   [<span data-ttu-id="a9e6b-176">Общая разработка</span><span class="sxs-lookup"><span data-stu-id="a9e6b-176">General development</span></span>](#General)  
  
-   [<span data-ttu-id="a9e6b-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="a9e6b-177">HttpClient</span></span>](#HttpClient)  
  
-   [<span data-ttu-id="a9e6b-178">Interop</span><span class="sxs-lookup"><span data-stu-id="a9e6b-178">Interop</span></span>](#Interop)  
  
-   [<span data-ttu-id="a9e6b-179">Неподдерживаемые API</span><span class="sxs-lookup"><span data-stu-id="a9e6b-179">Unsupported APIs</span></span>](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a><span data-ttu-id="a9e6b-180">Различия общей разработки</span><span class="sxs-lookup"><span data-stu-id="a9e6b-180">General development differences</span></span>  
 <span data-ttu-id="a9e6b-181">**Типы значений**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-181">**Value types**</span></span>  
  
-   <span data-ttu-id="a9e6b-182">При переопределении методов <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> и <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> для типа значения не вызывайте реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="a9e6b-183">В приложениях .NET для магазина Windows эти методы основаны на отражении.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="a9e6b-184">Во время компиляции .NET Native создает реализацию, которая не зависит от отражения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-184">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="a9e6b-185">Это означает, что если не переопределить эти два метода, они будут работать как и ожидалось, так как .NET Native создает реализацию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-185">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="a9e6b-186">Однако, переопределение этих методов с помощью вызова реализации базового класса приводит к возникновению исключения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>  
  
-   <span data-ttu-id="a9e6b-187">Типы значений больше одного мегабайта не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-187">Value types larger than one megabyte aren't supported.</span></span>  
  
-   <span data-ttu-id="a9e6b-188">Типы значений не может иметь конструктор по умолчанию в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-188">Value types can't have a default constructor in .NET Native.</span></span> <span data-ttu-id="a9e6b-189">(C# и Visual Basic запрещают конструкторы по умолчанию для типов значений.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-189">(C# and Visual Basic prohibit default constructors on value types.</span></span> <span data-ttu-id="a9e6b-190">Тем не менее их можно создать в IL.)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-190">However, these can be created in IL.)</span></span>  
  
 <span data-ttu-id="a9e6b-191">**Массивы**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-191">**Arrays**</span></span>  
  
-   <span data-ttu-id="a9e6b-192">Массивы с нижней границей, отличной от нуля, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="a9e6b-193">Как правило, эти массивы создаются путем вызова перегрузки <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
-   <span data-ttu-id="a9e6b-194">Динамическое создание многомерных массивов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="a9e6b-195">Такие массивы обычно создаются путем вызова перегрузки метода <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType>, который включает в себя параметр `lengths`, или же путем вызова метода <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="a9e6b-196">Многомерные массивы, имеющие четыре или более измерений не поддерживаются; т.е. их значение свойства <xref:System.Array.Rank%2A?displayProperty=nameWithType> равно или больше четырех.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="a9e6b-197">Вместо этого используйте [ступенчатые массивы](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (массива массивов).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-197">Use [jagged arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="a9e6b-198">Например `array[x,y,z]` является недопустимым, но `array[x][y][z]` нет.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>  
  
-   <span data-ttu-id="a9e6b-199">Вариативность для многомерных массивов не поддерживается и вызывает исключение <xref:System.InvalidCastException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>  
  
 <span data-ttu-id="a9e6b-200">**Универсальные шаблоны**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-200">**Generics**</span></span>  
  
-   <span data-ttu-id="a9e6b-201">Расширения бесконечного универсального типа приводят к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="a9e6b-202">Например, этот код вызывает ошибку при компиляции:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-202">For example, this code fails to compile:</span></span>  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 <span data-ttu-id="a9e6b-203">**Pointers**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-203">**Pointers**</span></span>  
  
-   <span data-ttu-id="a9e6b-204">Массивы указателей не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-204">Arrays of pointers aren't supported.</span></span>  
  
-   <span data-ttu-id="a9e6b-205">Чтобы получить или задать поле указателя, нельзя использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-205">You can't use reflection to get or set a pointer field.</span></span>  
  
 <span data-ttu-id="a9e6b-206">**Сериализация**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-206">**Serialization**</span></span>  
  
 <span data-ttu-id="a9e6b-207">Атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="a9e6b-208">Вместо этого используйте атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .</span><span class="sxs-lookup"><span data-stu-id="a9e6b-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>  
  
 <span data-ttu-id="a9e6b-209">**Ресурсы**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-209">**Resources**</span></span>  
  
 <span data-ttu-id="a9e6b-210">Использование локализованных ресурсов с классом <xref:System.Diagnostics.Tracing.EventSource> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="a9e6b-211">Свойство <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> не определяет локализованные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>  
  
 <span data-ttu-id="a9e6b-212">**Делегаты**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-212">**Delegates**</span></span>  
  
 <span data-ttu-id="a9e6b-213">`Delegate.BeginInvoke` и `Delegate.EndInvoke` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>  
  
 <span data-ttu-id="a9e6b-214">**Различные API**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-214">**Miscellaneous APIs**</span></span>  
  
-   <span data-ttu-id="a9e6b-215">Свойство <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> вызывает исключение <xref:System.PlatformNotSupportedException>, если атрибут <xref:System.Runtime.InteropServices.GuidAttribute> не применяется к типу.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-215">The <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="a9e6b-216">Идентификатор GUID используется в основном для поддержки модели COM.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-216">The GUID is used primarily for COM support.</span></span>  
  
-   <span data-ttu-id="a9e6b-217"><xref:System.DateTime.Parse%2A?displayProperty=nameWithType> Метод правильно выполняет синтаксический анализ строк, содержащих даты в коротком формате в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-217">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="a9e6b-218">Тем не менее, он не поддерживает совместимость с изменениями в дате и времени синтаксического анализа описанным в статьях базы знаний Microsoft Knowledge Base [KB2803771](https://support.microsoft.com/kb/2803771) и [KB2803755](https://support.microsoft.com/kb/2803755).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-218">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](https://support.microsoft.com/kb/2803771) and [KB2803755](https://support.microsoft.com/kb/2803755).</span></span>  
  
-   <span data-ttu-id="a9e6b-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` правильно округляется в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="a9e6b-220">В некоторых версиях среды CLR, результирующая строка усекается вместо округления.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-220">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a><span data-ttu-id="a9e6b-221">Различия HttpClient</span><span class="sxs-lookup"><span data-stu-id="a9e6b-221">HttpClient differences</span></span>  
 <span data-ttu-id="a9e6b-222">В .NET Native <xref:System.Net.Http.HttpClientHandler> класс внутренним образом использует WinINet (через [HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) класс) вместо <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> классы, используемые в стандартных приложениях .NET для Windows Store.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-222">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the [HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="a9e6b-223">WinINet не поддерживает все параметры конфигурации, которые поддерживает класс <xref:System.Net.Http.HttpClientHandler> .</span><span class="sxs-lookup"><span data-stu-id="a9e6b-223">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="a9e6b-224">Это приводит к следующим результатам.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-224">As a result:</span></span>  
  
-   <span data-ttu-id="a9e6b-225">Некоторые свойства возможности на <xref:System.Net.Http.HttpClientHandler> возвращают `false` машинного кода .NET, в то время как они возвращают `true` в стандартных приложениях .NET для Windows Store.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-225">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>  
  
-   <span data-ttu-id="a9e6b-226">Некоторые свойства конфигурации `get` методы доступа всегда возвращают фиксированное значение в среде .NET Native, отличный от значение по умолчанию можно настроить в приложениях .NET для Windows Store.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-226">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="a9e6b-227">В следующих подразделах описаны некоторые дополнительные различия в поведении.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-227">Some additional behavior differences are covered in the following subsections.</span></span>  
  
 <span data-ttu-id="a9e6b-228">**Прокси-сервер**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-228">**Proxy**</span></span>  
  
 <span data-ttu-id="a9e6b-229">[HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) класс не поддерживает настройку или переопределение прокси для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-229">The [HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="a9e6b-230">Это означает, что все запросы на .NET Native использовать системные настройки прокси-сервера или прокси-сервер, в зависимости от значения <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-230">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="a9e6b-231">В приложениях .NET для магазина Windows, прокси-сервер определяется свойством <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-231">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="a9e6b-232">В среде .NET Native, установка <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> на значение, отличное от `null` вызывает <xref:System.PlatformNotSupportedException> исключение.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-232">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="a9e6b-233"><xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> Возвращает `false` машинного кода .NET, в то время как он возвращает `true` в стандартных приложениях .NET Framework для Windows Store.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-233">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>  
  
 <span data-ttu-id="a9e6b-234">**Автоматическое перенаправление**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-234">**Automatic redirection**</span></span>  
  
 <span data-ttu-id="a9e6b-235">[HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) не допускает максимальное число автоматических перенаправлений к конфигурированию.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-235">The [HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="a9e6b-236">Значение свойства <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> равно 50 по умолчанию в стандартных приложениях .NET для магазина Windows и может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-236">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="a9e6b-237">На .NET Native, значение этого свойства равно 10 и попытка его изменить вызывает <xref:System.PlatformNotSupportedException> исключение.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-237">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="a9e6b-238"><xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> Возвращает `false` машинного кода .NET, в то время как он возвращает `true` в приложениях .NET для Windows Store.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-238">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="a9e6b-239">**Автоматическая распаковка**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-239">**Automatic decompression**</span></span>  
  
 <span data-ttu-id="a9e6b-240">Приложения .NET для магазина Windows позволяют задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> на <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip> или <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-240">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="a9e6b-241">.NET native поддерживает только <xref:System.Net.DecompressionMethods.Deflate> вместе с <xref:System.Net.DecompressionMethods.GZip>, или <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-241">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="a9e6b-242">При попытке задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> только на <xref:System.Net.DecompressionMethods.Deflate> или <xref:System.Net.DecompressionMethods.GZip> происходит его автоматическое задание на оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-242">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>  
  
 <span data-ttu-id="a9e6b-243">**Файлы cookie**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-243">**Cookies**</span></span>  
  
 <span data-ttu-id="a9e6b-244">Обработка файлов cookie выполняется одновременно с <xref:System.Net.Http.HttpClient> и WinINet.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-244">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="a9e6b-245">Файлы cookie из <xref:System.Net.CookieContainer> объединяются вместе файла cookie в кэше WinINet cookie.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-245">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="a9e6b-246">Удаление файла cookie из <xref:System.Net.CookieContainer> запрещает <xref:System.Net.Http.HttpClient> отправлять файл cookie, но если файл cookie уже был просмотрен WinINet и файлы "cookie" не были удалены пользователем, WinINet отправляет его.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-246">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="a9e6b-247">Не существует средств программного удаления файла cookie из WinINet с использованием API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>или <xref:System.Net.CookieContainer> .</span><span class="sxs-lookup"><span data-stu-id="a9e6b-247">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="a9e6b-248">Задание свойства <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> на `false` вызывает только <xref:System.Net.Http.HttpClient>, чтобы остановить отправку файлов "cookie"; WinINet может по-прежнему включить свои файлы cookie в запрос.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-248">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>  
  
 <span data-ttu-id="a9e6b-249">**Учетные данные**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-249">**Credentials**</span></span>  
  
 <span data-ttu-id="a9e6b-250">В приложениях .NET для магазина Windows свойства <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> и <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType>работают независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-250">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="a9e6b-251">Кроме того, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> принимает любой объект, реализующий интерфейс <xref:System.Net.ICredentials> .</span><span class="sxs-lookup"><span data-stu-id="a9e6b-251">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="a9e6b-252">В .NET Native, установка <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> свойства `true` вызывает <xref:System.Net.Http.HttpClientHandler.Credentials%2A> свойство станет `null`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-252">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="a9e6b-253">Кроме этого, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> может быть задано только в `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>или объект типа <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-253">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="a9e6b-254">Назначение любого другого объекта <xref:System.Net.ICredentials> , наиболее популярный из которых <xref:System.Net.CredentialCache>, свойству <xref:System.Net.Http.HttpClientHandler.Credentials%2A> вызывает исключение <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-254">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>  
  
 <span data-ttu-id="a9e6b-255">**Другие неподдерживаемые и ненастраиваемые функции**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-255">**Other unsupported or unconfigurable features**</span></span>  
  
 <span data-ttu-id="a9e6b-256">В машинный код .NET:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-256">In .NET Native:</span></span>  
  
-   <span data-ttu-id="a9e6b-257">Значение свойства <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> всегда <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-257">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="a9e6b-258">В приложения .NET для магазина Windows, по умолчанию используется <xref:System.Net.Http.ClientCertificateOption.Manual>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-258">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>  
  
-   <span data-ttu-id="a9e6b-259">Свойство <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> не настраивается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-259">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>  
  
-   <span data-ttu-id="a9e6b-260">Свойство <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> всегда имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-260">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="a9e6b-261">В приложения .NET для магазина Windows, по умолчанию используется `false`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-261">In .NET for Windows Store apps, the default is `false`.</span></span>  
  
-   <span data-ttu-id="a9e6b-262">Заголовок `SetCookie2` в ответах игнорируется как устаревший.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-262">The `SetCookie2` header in responses is ignored as obsolete.</span></span>  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a><span data-ttu-id="a9e6b-263">Различия взаимодействия</span><span class="sxs-lookup"><span data-stu-id="a9e6b-263">Interop differences</span></span>  
 <span data-ttu-id="a9e6b-264">**Устаревшие интерфейсы API**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-264">**Deprecated APIs**</span></span>  
  
 <span data-ttu-id="a9e6b-265">Не рекомендуется использовать несколько редко применяемых API-интерфейсов для взаимодействия с управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-265">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="a9e6b-266">При использовании с .NET Native, могут вызывать эти API-интерфейсы <xref:System.NotImplementedException> или <xref:System.PlatformNotSupportedException> исключение или приводят к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-266">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="a9e6b-267">В приложениях .NET для магазина Windows эти API-интерфейсы отмечены как устаревшие, хотя их вызов создает предупреждение компилятора, а не ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-267">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>  
  
 <span data-ttu-id="a9e6b-268">Устаревшие API-интерфейсы для маршалинга `VARIANT` :</span><span class="sxs-lookup"><span data-stu-id="a9e6b-268">Deprecated APIs for `VARIANT` marshaling:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a9e6b-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> поддерживается, но выдает исключение в некоторых сценариях, например при использовании с [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) или ByRef.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) or byref variants.</span></span>  
  
 <span data-ttu-id="a9e6b-270">Устаревшие интерфейсы API для [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) поддержки:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-270">Deprecated APIs for [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) support:</span></span>  
  
|<span data-ttu-id="a9e6b-271">Тип</span><span class="sxs-lookup"><span data-stu-id="a9e6b-271">Type</span></span>|<span data-ttu-id="a9e6b-272">Член</span><span class="sxs-lookup"><span data-stu-id="a9e6b-272">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>|<span data-ttu-id="a9e6b-273">Атрибут не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a9e6b-273">Attribute isn't supported</span></span>|  
  
 <span data-ttu-id="a9e6b-274">Устаревшие интерфейсы API для классических COM-событий:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-274">Deprecated APIs for classic COM events:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 <span data-ttu-id="a9e6b-275">Устаревшие интерфейсы API в <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> интерфейс, который не поддерживается в .NET Native:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-275">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native:</span></span>  
  
|<span data-ttu-id="a9e6b-276">Тип</span><span class="sxs-lookup"><span data-stu-id="a9e6b-276">Type</span></span>|<span data-ttu-id="a9e6b-277">Член</span><span class="sxs-lookup"><span data-stu-id="a9e6b-277">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>|<span data-ttu-id="a9e6b-278">Все члены.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-278">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>|<span data-ttu-id="a9e6b-279">Все члены.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-279">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>|<span data-ttu-id="a9e6b-280">Все члены.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-280">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a9e6b-281">Другие неподдерживаемые функции взаимодействия:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-281">Other unsupported interop features:</span></span>  
  
|<span data-ttu-id="a9e6b-282">Тип</span><span class="sxs-lookup"><span data-stu-id="a9e6b-282">Type</span></span>|<span data-ttu-id="a9e6b-283">Член</span><span class="sxs-lookup"><span data-stu-id="a9e6b-283">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>|<span data-ttu-id="a9e6b-284">Все члены.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-284">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>|<span data-ttu-id="a9e6b-285">Все члены.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-285">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 <span data-ttu-id="a9e6b-286">Редко используемые интерфейсы API маршалинга:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-286">Rarely used marshalling APIs:</span></span>  
  
|<span data-ttu-id="a9e6b-287">Тип</span><span class="sxs-lookup"><span data-stu-id="a9e6b-287">Type</span></span>|<span data-ttu-id="a9e6b-288">Член</span><span class="sxs-lookup"><span data-stu-id="a9e6b-288">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29>|  
  
 <span data-ttu-id="a9e6b-289">**Вызов неуправляемого кода и совместимость взаимодействия COM**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-289">**Platform invoke and COM interop compatibility**</span></span>  
  
 <span data-ttu-id="a9e6b-290">Большинство вызовов неуправляемого и сценариях COM-взаимодействия по-прежнему поддерживаются в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-290">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="a9e6b-291">В частности, поддерживаются все взаимодействия с API среды выполнения Windows (WinRT) и весь необходимый маршалинг для среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-291">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="a9e6b-292">Это включает поддержку маршалинга:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-292">This includes marshaling support for:</span></span>  
  
-   <span data-ttu-id="a9e6b-293">Массивы (включая <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-293">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>  
  
-   `BStr`  
  
-   <span data-ttu-id="a9e6b-294">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a9e6b-294">Delegates</span></span>  
  
-   <span data-ttu-id="a9e6b-295">Строки (Юникод, Ansi и HSTRING)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-295">Strings (Unicode, Ansi, and HSTRING)</span></span>  
  
-   <span data-ttu-id="a9e6b-296">Структуры (`byref` и `byval`)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-296">Structs (`byref` and `byval`)</span></span>  
  
-   <span data-ttu-id="a9e6b-297">Объединения</span><span class="sxs-lookup"><span data-stu-id="a9e6b-297">Unions</span></span>  
  
-   <span data-ttu-id="a9e6b-298">Дескрипторы Win32</span><span class="sxs-lookup"><span data-stu-id="a9e6b-298">Win32 handles</span></span>  
  
-   <span data-ttu-id="a9e6b-299">Все конструкции WinRT</span><span class="sxs-lookup"><span data-stu-id="a9e6b-299">All WinRT constructs</span></span>  
  
-   <span data-ttu-id="a9e6b-300">Частичная поддержка маршалинга типов variant.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-300">Partial support for marshaling variant types.</span></span> <span data-ttu-id="a9e6b-301">Поддерживаются следующие функции:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-301">The following are supported:</span></span>  
  
    -   <xref:System.Boolean>  
  
    -   <xref:System.Byte>  
  
    -   <xref:System.Decimal>  
  
    -   <xref:System.Double>  
  
    -   <xref:System.Int16>  
  
    -   <xref:System.Int32>  
  
    -   <xref:System.Int64>  
  
    -   <xref:System.SByte>  
  
    -   <xref:System.Single>  
  
    -   <xref:System.UInt16>  
  
    -   <xref:System.UInt32>  
  
    -   <xref:System.UInt64>  
  
    -   `BStr`  
  
    -   [<span data-ttu-id="a9e6b-302">IUnknown</span><span class="sxs-lookup"><span data-stu-id="a9e6b-302">IUnknown</span></span>](/windows/desktop/api/unknwn/nn-unknwn-iunknown)  
  
 <span data-ttu-id="a9e6b-303">Тем не менее .NET Native не поддерживает следующее:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-303">However, .NET Native doesn't support the following:</span></span>  
  
-   <span data-ttu-id="a9e6b-304">использование классических COM-событий</span><span class="sxs-lookup"><span data-stu-id="a9e6b-304">Using classic COM events</span></span>  
  
-   <span data-ttu-id="a9e6b-305">Реализация интерфейса <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> на управляемом типе</span><span class="sxs-lookup"><span data-stu-id="a9e6b-305">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>  
  
-   <span data-ttu-id="a9e6b-306">Реализация [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) интерфейса на управляемом типе через <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> атрибута.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-306">Implementing the [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="a9e6b-307">Однако, обратите внимание, что нельзя вызывать COM-объекты через `IDispatch`, а управляемый объект не может реализовать `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-307">However, note that you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>  
  
 <span data-ttu-id="a9e6b-308">Использование отражения для вызова метода неуправляемого кода не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-308">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="a9e6b-309">Это ограничение можно обойти путем заключения вызова метода в другой метод, вместо этого используя вызов оболочки.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-309">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="a9e6b-310">Другие отличия от API-интерфейсов приложений .NET для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="a9e6b-310">Other differences from .NET APIs for Windows Store apps</span></span>  
 <span data-ttu-id="a9e6b-311">В этом разделе перечислены остальные интерфейсы API, которые не поддерживаются в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-311">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="a9e6b-312">Самый большой набор неподдерживаемых интерфейсов API — это API-интерфейсы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-312">The largest set of the unsupported APIs are Windows Communication Foundation (WCF) APIs.</span></span>  
  
 <span data-ttu-id="a9e6b-313">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-313">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>  
  
 <span data-ttu-id="a9e6b-314">Типы в <xref:System.ComponentModel.DataAnnotations> и <xref:System.ComponentModel.DataAnnotations.Schema> пространства имен не поддерживаются в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-314">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="a9e6b-315">К ним относятся следующие типы, которые присутствуют в приложениях .NET для магазина Windows для Windows 8:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-315">These include the following types that are present in the .NET for Windows Store apps for Windows 8:</span></span>  
  
||  
|-|  
|<xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EditableAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a9e6b-316">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-316">**Visual Basic**</span></span>  
  
 <span data-ttu-id="a9e6b-317">Visual Basic сейчас не поддерживается в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-317">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="a9e6b-318">Следующие типы в <xref:Microsoft.VisualBasic> и <xref:Microsoft.VisualBasic.CompilerServices> пространства имен недоступны в .NET Native:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-318">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>  
  
||  
|-|  
|<xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a9e6b-319">**Контекст отражения (пространство имен System.Reflection.Context)**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-319">**Reflection Context (System.Reflection.Context namespace)**</span></span>  
  
 <span data-ttu-id="a9e6b-320"><xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> Класс не поддерживается в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-320">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>  
  
 <span data-ttu-id="a9e6b-321">**Часы реального времени (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-321">**RTC (System.Net.Http.Rtc)**</span></span>  
  
 <span data-ttu-id="a9e6b-322"><xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> Класс не поддерживается в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-322">The <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>  
  
 <span data-ttu-id="a9e6b-323">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-323">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>  
  
 <span data-ttu-id="a9e6b-324">Типы в [пространствах имен System.ServiceModel.\*](https://msdn.microsoft.com/library/gg145010.aspx) не поддерживаются в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-324">The types in the [System.ServiceModel.\* namespaces](https://msdn.microsoft.com/library/gg145010.aspx) aren't supported in .NET Native.</span></span> <span data-ttu-id="a9e6b-325">В число этих типов входят следующие:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-325">These includes the following types:</span></span>  
  
||  
|-|  
|<xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>|  
  
### <a name="differences-in-serializers"></a><span data-ttu-id="a9e6b-326">Различия в сериализаторах</span><span class="sxs-lookup"><span data-stu-id="a9e6b-326">Differences in serializers</span></span>  
 <span data-ttu-id="a9e6b-327">Существуют следующие различия, касающиеся сериализации и десериализации с классами <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>и <xref:System.Xml.Serialization.XmlSerializer> :</span><span class="sxs-lookup"><span data-stu-id="a9e6b-327">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>  
  
-   <span data-ttu-id="a9e6b-328">В .NET Native <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> не удается сериализовать или десериализовать производный класс, имеющий член базового класса, тип которого не является корневым тип сериализации.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-328">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="a9e6b-329">Например, в следующем коде при сериализации или десериализации `Y` возникает ошибка:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-329">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     <span data-ttu-id="a9e6b-330">Тип `InnerType` не известен сериализатору, так как члены базового класса не передаются во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-330">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>  
  
-   <span data-ttu-id="a9e6b-331"><xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> не удается сериализовать класс или структуру, которая реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="a9e6b-331"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="a9e6b-332">Например, не удается сериализовать или десериализовать следующие типы:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-332">For example, the following types fail to serialize or deserialize:</span></span>  
  
  
  
-   <span data-ttu-id="a9e6b-333"><xref:System.Xml.Serialization.XmlSerializer> не удается сериализовать следующие значения объекта, так как он не знает точный тип объекта для сериализации:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-333"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>  
  
  
  
-   <span data-ttu-id="a9e6b-334"><xref:System.Xml.Serialization.XmlSerializer> не удается сериализация или десериализация, если тип сериализованного объекта <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-334"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>  
  
-   <span data-ttu-id="a9e6b-335">Все сериализаторам (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и <xref:System.Xml.Serialization.XmlSerializer>) не удается создать код сериализации для типа <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> или типа, содержащего <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-335">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="a9e6b-336">Вместо этого они отображают ошибки во время построения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-336">They display build-time errors instead.</span></span>  
  
-   <span data-ttu-id="a9e6b-337">Следующие конструкторы типов сериализации не обязательно работают, как должны:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-337">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>  
  
-   <span data-ttu-id="a9e6b-338"><xref:System.Xml.Serialization.XmlSerializer> не удается создать код для типа, который содержит методы, определенные любым из следующих атрибутов:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-338"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <span data-ttu-id="a9e6b-339"><xref:System.Xml.Serialization.XmlSerializer> не поддерживает настраиваемый интерфейс сериализации <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="a9e6b-339"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="a9e6b-340">Если имеется класс, реализующий этот интерфейс, <xref:System.Xml.Serialization.XmlSerializer> рассматривает тип, как тип объекта (POCO) простой старой среды CLR и сериализует только его открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-340">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>  
  
-   <span data-ttu-id="a9e6b-341">Сериализация простого объекта <xref:System.Exception> , как указано ниже, плохо работает с <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-341">Serializing a plain <xref:System.Exception> object, such as the following, doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a><span data-ttu-id="a9e6b-342">Различия в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a9e6b-342">Visual Studio differences</span></span>  
 <span data-ttu-id="a9e6b-343">**Исключения и отладка**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-343">**Exceptions and debugging**</span></span>  
  
 <span data-ttu-id="a9e6b-344">При запуске приложений, скомпилированных с помощью .NET Native в отладчике исключения первого шанса включены для следующих типов исключений:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-344">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 <span data-ttu-id="a9e6b-345">**Создание приложений**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-345">**Building apps**</span></span>  
  
 <span data-ttu-id="a9e6b-346">Используйте средства построения x 86, которые используются по умолчанию в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-346">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="a9e6b-347">Не рекомендуется использование средств AMD64 MSBuild, которые находятся в C:\Program Files (x86)\MSBuild\12.0\bin\amd64; Это может создать проблемы построения.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-347">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>  
  
 <span data-ttu-id="a9e6b-348">**Профилировщики**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-348">**Profilers**</span></span>  
  
-   <span data-ttu-id="a9e6b-349">Профилировщик ЦП в Visual Studio и профилировщик памяти XAML неправильно отображают «только мой код».</span><span class="sxs-lookup"><span data-stu-id="a9e6b-349">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>  
  
-   <span data-ttu-id="a9e6b-350">Профилировщик памяти XAML неточно отображает данные управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-350">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>  
  
-   <span data-ttu-id="a9e6b-351">Профилировщик ЦП неправильно идентифицирует модули и отображает имена функций с префиксами.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-351">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>  
  
 <span data-ttu-id="a9e6b-352">**Проекты модульных тестов библиотеки**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-352">**Unit Test Library projects**</span></span>  
  
 <span data-ttu-id="a9e6b-353">Включение машинного кода .NET на библиотека модульных тестов для проекта приложения Windows Store не поддерживается и приводит к сбою построения проекта.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-353">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e6b-354">См. также</span><span class="sxs-lookup"><span data-stu-id="a9e6b-354">See Also</span></span>  
 [<span data-ttu-id="a9e6b-355">Начало работы</span><span class="sxs-lookup"><span data-stu-id="a9e6b-355">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="a9e6b-356">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-356">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="a9e6b-357">Обзор приложений .NET для Windows Store</span><span class="sxs-lookup"><span data-stu-id="a9e6b-357">.NET For Windows Store apps overview</span></span>](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [<span data-ttu-id="a9e6b-358">Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="a9e6b-358">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
