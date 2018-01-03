---
title: "Миграция приложения для магазина Windows в машинный код .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
caps.latest.revision: "29"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce23d66f79f94af74250cff137499f6c8b1582ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-your-windows-store-app-to-net-native"></a><span data-ttu-id="57852-102">Миграция приложения для магазина Windows в машинный код .NET</span><span class="sxs-lookup"><span data-stu-id="57852-102">Migrating Your Windows Store App to .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="57852-103"> обеспечивает статическую компиляцию приложений в магазине Windows или на компьютере разработчика.</span><span class="sxs-lookup"><span data-stu-id="57852-103"> provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="57852-104">В отличие от динамической компиляции, выполняемой JIT-компилятором для приложений магазина Windows или [Генератором машинных образов (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) на устройстве.</span><span class="sxs-lookup"><span data-stu-id="57852-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="57852-105">Несмотря на эти различия [!INCLUDE[net_native](../../../includes/net-native-md.md)] пытается поддерживать совместимость с [приложениями .NET для магазина Windows](http://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span><span class="sxs-lookup"><span data-stu-id="57852-105">Despite the differences, [!INCLUDE[net_native](../../../includes/net-native-md.md)] tries to maintain compatibility with the [.NET for Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span></span> <span data-ttu-id="57852-106">В большинстве случаев все, что работает в приложении .NET для магазина Windows, также работает с [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-106">For the most part, things that work on the .NET for Windows Store apps also work with [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  <span data-ttu-id="57852-107">Тем не менее в некоторых случаях могут произойти изменения поведения.</span><span class="sxs-lookup"><span data-stu-id="57852-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="57852-108">В этом документе рассматриваются различия между стандартными приложениями .NET для магазина Windows и [!INCLUDE[net_native](../../../includes/net-native-md.md)] в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="57852-108">This document discusses these differences between the standard .NET for Windows Store apps and [!INCLUDE[net_native](../../../includes/net-native-md.md)] in the following areas:</span></span>  
  
-   [<span data-ttu-id="57852-109">Общие различия среды выполнения</span><span class="sxs-lookup"><span data-stu-id="57852-109">General runtime differences</span></span>](#Runtime)  
  
-   [<span data-ttu-id="57852-110">Различия динамического программирования</span><span class="sxs-lookup"><span data-stu-id="57852-110">Dynamic programming differences</span></span>](#Dynamic)  
  
-   [<span data-ttu-id="57852-111">Другие различия, связанным с отражением</span><span class="sxs-lookup"><span data-stu-id="57852-111">Other reflection-related differences</span></span>](#Reflection)  
  
-   [<span data-ttu-id="57852-112">Неподдерживаемые сценарии и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="57852-112">Unsupported scenarios and APIs</span></span>](#Unsupported)  
  
-   [<span data-ttu-id="57852-113">Различия в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="57852-113">Visual Studio differences</span></span>](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a><span data-ttu-id="57852-114">Общие различия среды выполнения</span><span class="sxs-lookup"><span data-stu-id="57852-114">General runtime differences</span></span>  
  
-   <span data-ttu-id="57852-115">Исключения, например, <xref:System.TypeLoadException>, которые вызываются с помощью JIT-компилятора при запуске приложения в общеязыковой среде выполнения (CLR), обычно приводят к ошибкам времени компиляции, когда обрабатываются средством [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
-   <span data-ttu-id="57852-116">Не вызывайте метод <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> из потока пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="57852-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="57852-117">Это может привести к взаимоблокировке в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-117">This can result in a deadlock on [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
-   <span data-ttu-id="57852-118">Не полагайтесь на порядок вызова конструктора статического класса.</span><span class="sxs-lookup"><span data-stu-id="57852-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="57852-119">В [!INCLUDE[net_native](../../../includes/net-native-md.md)], порядок вызова отличается от порядка в стандартной среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="57852-119">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="57852-120">(Даже со стандартной средой выполнения, не следует рассчитывать на порядок выполнения конструкторов статических классов.)</span><span class="sxs-lookup"><span data-stu-id="57852-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>  
  
-   <span data-ttu-id="57852-121">Бесконечный цикл без вызовов (например, `while(true);`) на любом потоке может привести к остановке приложения.</span><span class="sxs-lookup"><span data-stu-id="57852-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="57852-122">Аналогичным образом, большие или бесконечные ожидания могут также привести приложение к остановке.</span><span class="sxs-lookup"><span data-stu-id="57852-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>  
  
-   <span data-ttu-id="57852-123">Некоторые циклы универсальной инициализации не создают исключения в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-123">Certain generic initialization cycles don't throw exceptions in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-124">Например, следующий код создает исключение <xref:System.TypeLoadException> исключений в стандартной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="57852-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="57852-125">В [!INCLUDE[net_native](../../../includes/net-native-md.md)], это не так.</span><span class="sxs-lookup"><span data-stu-id="57852-125">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], it doesn't.</span></span>  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   <span data-ttu-id="57852-126">В некоторых случаях [!INCLUDE[net_native](../../../includes/net-native-md.md)] предоставляет различные реализации библиотеки классов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57852-126">In some cases, [!INCLUDE[net_native](../../../includes/net-native-md.md)] provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="57852-127">Объект, возвращенный из метода, всегда будет реализовать члены возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="57852-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="57852-128">Тем не менее, поскольку его резервная реализация отличается, может оказаться невозможным привести его к тому же набору типов, как это можно было бы сделать на платформах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57852-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="57852-129">Например, в некоторых случаях может оказаться невозможным привести объект интерфейса <xref:System.Collections.Generic.IEnumerable%601>, возвращенный такими методами как <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> или <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType>, к `T[]`.</span><span class="sxs-lookup"><span data-stu-id="57852-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>  
  
-   <span data-ttu-id="57852-130">Кэш WinInet не включен по умолчанию на платформе .NET для приложений магазина Windows, но он включен на [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-131">Это повышает производительность, но сказывается на рабочем наборе.</span><span class="sxs-lookup"><span data-stu-id="57852-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="57852-132">Не требуется никаких действий разработчика.</span><span class="sxs-lookup"><span data-stu-id="57852-132">No developer action is necessary.</span></span>  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a><span data-ttu-id="57852-133">Различия динамического программирования</span><span class="sxs-lookup"><span data-stu-id="57852-133">Dynamic programming differences</span></span>  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="57852-134"> статически связывает код из платформы .NET Framework, чтобы сделать код локальным для приложения с целью достижения максимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="57852-134"> statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="57852-135">Тем не менее, двоичные размеры должны оставаться небольшими, поэтому не удается подключить всю платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57852-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="57852-136">Компилятор [!INCLUDE[net_native](../../../includes/net-native-md.md)] разрешает это ограничение с помощью редуктора зависимостей, который удаляет ссылки на неиспользуемый код.</span><span class="sxs-lookup"><span data-stu-id="57852-136">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="57852-137">Однако, [!INCLUDE[net_native](../../../includes/net-native-md.md)] не может поддерживать или создавать некоторые сведения о типе и код, если эти сведения не могут быть определены статически во время компиляции, а вместо этого извлекаются динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="57852-137">However, [!INCLUDE[net_native](../../../includes/net-native-md.md)] might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="57852-138"> включает отражение и динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="57852-138"> does enable reflection and dynamic programming.</span></span> <span data-ttu-id="57852-139">При этом, не все типы могут быть помечены для отражения, так как это сделает размер созданного кода слишком большим (особенно потому, что поддерживается отражение на общедоступных API в платформе .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="57852-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="57852-140">Компилятор [!INCLUDE[net_native](../../../includes/net-native-md.md)] делает интеллектуальный выбор типов, которые должны поддерживать отражение, сохраняет метаданные и создает код только для этих типов.</span><span class="sxs-lookup"><span data-stu-id="57852-140">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>  
  
 <span data-ttu-id="57852-141">Например, привязка данных требует, чтобы приложение обеспечивало сопоставление имен свойств с функциями.</span><span class="sxs-lookup"><span data-stu-id="57852-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="57852-142">В приложениях .NET для магазина Windows среда CLR автоматически использует отражение для обеспечения этой возможности для управляемых и общедоступных собственных типов.</span><span class="sxs-lookup"><span data-stu-id="57852-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="57852-143">В [!INCLUDE[net_native](../../../includes/net-native-md.md)], компилятор автоматически включает метаданные для типов, к которым осуществляется привязка данных.</span><span class="sxs-lookup"><span data-stu-id="57852-143">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the compiler automatically includes metadata for types to which you bind data.</span></span>  
  
 <span data-ttu-id="57852-144">Компилятор [!INCLUDE[net_native](../../../includes/net-native-md.md)] может также обрабатывать часто используемые универсальные типы, такие как <xref:System.Collections.Generic.List%601> и <xref:System.Collections.Generic.Dictionary%602>, которые работают, не требуя подсказок или директив.</span><span class="sxs-lookup"><span data-stu-id="57852-144">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="57852-145">Ключевое слово [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) также поддерживается в заданных пределах.</span><span class="sxs-lookup"><span data-stu-id="57852-145">The [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) keyword is also supported within certain limits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57852-146">Следует тщательно протестировать все пути динамического кода при переносе приложения в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-146">You should test all dynamic code paths thoroughly when porting your app to [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="57852-147">Конфигурация по умолчанию для [!INCLUDE[net_native](../../../includes/net-native-md.md)] достаточна для большинства разработчиков, но некоторым разработчикам может потребоваться точная настройка своих конфигураций с помощью файла директив среды выполнения (. rd.xml) файла.</span><span class="sxs-lookup"><span data-stu-id="57852-147">The default configuration for [!INCLUDE[net_native](../../../includes/net-native-md.md)] is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="57852-148">Кроме того, в некоторых случаях компилятору [!INCLUDE[net_native](../../../includes/net-native-md.md)] не удается определить, какие метаданные должны быть доступны для отражения, и он опирается на подсказки, в особенности в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="57852-148">In addition, in some cases, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>  
  
-   <span data-ttu-id="57852-149">Некоторые конструкции, такие как <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> и <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> не удается определить статически.</span><span class="sxs-lookup"><span data-stu-id="57852-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>  
  
-   <span data-ttu-id="57852-150">Поскольку компилятор не может определить экземпляры, универсальный тип, который требуется отразить на нем должен быть указан директивами среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="57852-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="57852-151">Это необходимо не только потому, что весь код должен быть включен, но так же и вследствие того, что отражение на универсальных типах могут образовывать бесконечный цикл (например, при вызове универсального метода для универсального типа).</span><span class="sxs-lookup"><span data-stu-id="57852-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57852-152">Директивы среды выполнения определяются в файле директив среды выполнения (. rd.xml).</span><span class="sxs-lookup"><span data-stu-id="57852-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="57852-153">Общие сведения об использовании этого файла см. в разделе [Приступая к работе](../../../docs/framework/net-native/getting-started-with-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="57852-153">For general information about using this file, see [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md).</span></span> <span data-ttu-id="57852-154">Сведения о директивах среды выполнения см. в разделе [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="57852-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="57852-155"> также включает средства профилирования, помогающие определить, какие типы, не входящие в набор по умолчанию, должны поддерживать отражения.</span><span class="sxs-lookup"><span data-stu-id="57852-155"> also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a><span data-ttu-id="57852-156">Другие различия, связанным с отражением</span><span class="sxs-lookup"><span data-stu-id="57852-156">Other reflection-related differences</span></span>  
 <span data-ttu-id="57852-157">Существует ряд других отдельных, связанных с отражением различий в поведении приложения .NET для магазина Windows и [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="57852-158">В [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="57852-158">In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
-   <span data-ttu-id="57852-159">Отражение закрытых типов и членов в библиотеке классов платформы .NET Framework не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="57852-160">Тем не менее, можно выполнить отражение на собственных закрытых типах и членах, а также типах и членах библиотек сторонних поставщиков.</span><span class="sxs-lookup"><span data-stu-id="57852-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>  
  
-   <span data-ttu-id="57852-161">Свойство <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> корректно возвращает `false` для объекта <xref:System.Reflection.ParameterInfo>, который представляет возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="57852-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="57852-162">В приложениях .NET для магазина Windows, будет возвращено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="57852-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="57852-163">Промежуточный язык (IL) не поддерживает это непосредственно, и интерпретация выполняется языком.</span><span class="sxs-lookup"><span data-stu-id="57852-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>  
  
-   <span data-ttu-id="57852-164">Открытые члены на структурах <xref:System.RuntimeFieldHandle> и <xref:System.RuntimeMethodHandle> не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="57852-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="57852-165">Эти типы поддерживаются только для LINQ, деревьев выражений и инициализации статического массива.</span><span class="sxs-lookup"><span data-stu-id="57852-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>  
  
-   <span data-ttu-id="57852-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType>и <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> включают скрытые члены в базовых классах и поэтому могут переопределяться без явного переопределения.</span><span class="sxs-lookup"><span data-stu-id="57852-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="57852-167">Это также справедливо для других методов [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) .</span><span class="sxs-lookup"><span data-stu-id="57852-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) methods.</span></span>  
  
-   <span data-ttu-id="57852-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>и <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> не дают сбой при попытке создать определенные комбинации (например, массив byrefs).</span><span class="sxs-lookup"><span data-stu-id="57852-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of byrefs).</span></span>  
  
-   <span data-ttu-id="57852-169">Нельзя использовать отражение для вызова членов, которые содержат параметры указателя.</span><span class="sxs-lookup"><span data-stu-id="57852-169">You can't use reflection to invoke members that have pointer parameters.</span></span>  
  
-   <span data-ttu-id="57852-170">Чтобы получить или задать поле указателя, нельзя использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="57852-170">You can't use reflection to get or set a pointer field.</span></span>  
  
-   <span data-ttu-id="57852-171">Если неверное количество аргументов и тип одного из аргументов неверен, [!INCLUDE[net_native](../../../includes/net-native-md.md)] вызывает <xref:System.ArgumentException> вместо <xref:System.Reflection.TargetParameterCountException>.</span><span class="sxs-lookup"><span data-stu-id="57852-171">When the argument count is wrong and the type of one of the arguments is incorrect, [!INCLUDE[net_native](../../../includes/net-native-md.md)] throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>  
  
-   <span data-ttu-id="57852-172">Обычно двоичная сериализация исключений не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="57852-173">В результате несериализуемые объекты могут быть добавлены к словарю <xref:System.Exception.Data%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57852-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="57852-174">Неподдерживаемые сценарии и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="57852-174">Unsupported scenarios and APIs</span></span>  
 <span data-ttu-id="57852-175">В следующих разделах перечислены неподдерживаемые сценарии и интерфейсы API для общей разработки, взаимодействия и таких технологий, как HTTPClient и Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="57852-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>  
  
-   [<span data-ttu-id="57852-176">Общая разработка</span><span class="sxs-lookup"><span data-stu-id="57852-176">General development</span></span>](#General)  
  
-   [<span data-ttu-id="57852-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="57852-177">HttpClient</span></span>](#HttpClient)  
  
-   [<span data-ttu-id="57852-178">Interop</span><span class="sxs-lookup"><span data-stu-id="57852-178">Interop</span></span>](#Interop)  
  
-   [<span data-ttu-id="57852-179">Неподдерживаемые API</span><span class="sxs-lookup"><span data-stu-id="57852-179">Unsupported APIs</span></span>](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a><span data-ttu-id="57852-180">Различия общей разработки</span><span class="sxs-lookup"><span data-stu-id="57852-180">General development differences</span></span>  
 <span data-ttu-id="57852-181">**Типы значений**</span><span class="sxs-lookup"><span data-stu-id="57852-181">**Value types**</span></span>  
  
-   <span data-ttu-id="57852-182">При переопределении методов <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> и <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> для типа значения не вызывайте реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="57852-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="57852-183">В приложениях .NET для магазина Windows эти методы основаны на отражении.</span><span class="sxs-lookup"><span data-stu-id="57852-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="57852-184">Во время компиляции [!INCLUDE[net_native](../../../includes/net-native-md.md)] генерирует реализацию, которая не зависит от отражения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="57852-184">At compile time, [!INCLUDE[net_native](../../../includes/net-native-md.md)] generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="57852-185">Это означает, что если не переопределить эти два метода, они будут работать, как ожидалось, поскольку [!INCLUDE[net_native](../../../includes/net-native-md.md)] создает реализацию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="57852-185">This means that if you don't override these two methods, they will work as expected, because [!INCLUDE[net_native](../../../includes/net-native-md.md)] generates the implementation at compile time.</span></span> <span data-ttu-id="57852-186">Однако, переопределение этих методов с помощью вызова реализации базового класса приводит к возникновению исключения.</span><span class="sxs-lookup"><span data-stu-id="57852-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>  
  
-   <span data-ttu-id="57852-187">Типы значений больше одного мегабайта не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="57852-187">Value types larger than one megabyte aren't supported.</span></span>  
  
-   <span data-ttu-id="57852-188">Типы значений не могут иметь конструктор по умолчанию в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-188">Value types can't have a default constructor in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-189">(C# и Visual Basic запрещают конструкторы по умолчанию для типов значений.</span><span class="sxs-lookup"><span data-stu-id="57852-189">(C# and Visual Basic prohibit default constructors on value types.</span></span> <span data-ttu-id="57852-190">Тем не менее их можно создать в IL.)</span><span class="sxs-lookup"><span data-stu-id="57852-190">However, these can be created in IL.)</span></span>  
  
 <span data-ttu-id="57852-191">**Массивы**</span><span class="sxs-lookup"><span data-stu-id="57852-191">**Arrays**</span></span>  
  
-   <span data-ttu-id="57852-192">Массивы с нижней границей, отличной от нуля, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="57852-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="57852-193">Как правило, эти массивы создаются путем вызова перегрузки <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57852-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
-   <span data-ttu-id="57852-194">Динамическое создание многомерных массивов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="57852-195">Такие массивы обычно создаются путем вызова перегрузки метода <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType>, который включает в себя параметр `lengths`, или же путем вызова метода <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57852-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="57852-196">Многомерные массивы, имеющие четыре или более измерений не поддерживаются; т.е. их значение свойства <xref:System.Array.Rank%2A?displayProperty=nameWithType> равно или больше четырех.</span><span class="sxs-lookup"><span data-stu-id="57852-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="57852-197">Вместо этого используйте [ступенчатые массивы](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (массива массивов).</span><span class="sxs-lookup"><span data-stu-id="57852-197">Use [jagged arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="57852-198">Например `array[x,y,z]` является недопустимым, но `array[x][y][z]` нет.</span><span class="sxs-lookup"><span data-stu-id="57852-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>  
  
-   <span data-ttu-id="57852-199">Вариативность для многомерных массивов не поддерживается и вызывает исключение <xref:System.InvalidCastException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="57852-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>  
  
 <span data-ttu-id="57852-200">**Универсальные шаблоны**</span><span class="sxs-lookup"><span data-stu-id="57852-200">**Generics**</span></span>  
  
-   <span data-ttu-id="57852-201">Расширения бесконечного универсального типа приводят к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="57852-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="57852-202">Например, этот код вызывает ошибку при компиляции:</span><span class="sxs-lookup"><span data-stu-id="57852-202">For example, this code fails to compile:</span></span>  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 <span data-ttu-id="57852-203">**Pointers**</span><span class="sxs-lookup"><span data-stu-id="57852-203">**Pointers**</span></span>  
  
-   <span data-ttu-id="57852-204">Массивы указателей не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-204">Arrays of pointers aren't supported.</span></span>  
  
-   <span data-ttu-id="57852-205">Чтобы получить или задать поле указателя, нельзя использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="57852-205">You can't use reflection to get or set a pointer field.</span></span>  
  
 <span data-ttu-id="57852-206">**Сериализация**</span><span class="sxs-lookup"><span data-stu-id="57852-206">**Serialization**</span></span>  
  
 <span data-ttu-id="57852-207">Атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="57852-208">Вместо этого используйте атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .</span><span class="sxs-lookup"><span data-stu-id="57852-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>  
  
 <span data-ttu-id="57852-209">**Ресурсы**</span><span class="sxs-lookup"><span data-stu-id="57852-209">**Resources**</span></span>  
  
 <span data-ttu-id="57852-210">Использование локализованных ресурсов с классом <xref:System.Diagnostics.Tracing.EventSource> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="57852-211">Свойство <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> не определяет локализованные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="57852-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>  
  
 <span data-ttu-id="57852-212">**Делегаты**</span><span class="sxs-lookup"><span data-stu-id="57852-212">**Delegates**</span></span>  
  
 <span data-ttu-id="57852-213">`Delegate.BeginInvoke` и `Delegate.EndInvoke` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="57852-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>  
  
 <span data-ttu-id="57852-214">**Async**</span><span class="sxs-lookup"><span data-stu-id="57852-214">**Async**</span></span>  
  
 <span data-ttu-id="57852-215">Потоковая логика в перегрузках задач Task IAsync не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-215">Threading logic in overloads of Task IAsync isn't supported.</span></span>  
  
 <span data-ttu-id="57852-216">**Различные интерфейсы API**</span><span class="sxs-lookup"><span data-stu-id="57852-216">**Miscellaneous APIs**</span></span>  
  
-   <span data-ttu-id="57852-217">Свойство <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> вызывает исключение <xref:System.PlatformNotSupportedException>, если атрибут <xref:System.Runtime.InteropServices.GuidAttribute> не применяется к типу.</span><span class="sxs-lookup"><span data-stu-id="57852-217">The <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="57852-218">Идентификатор GUID используется в основном для поддержки модели COM.</span><span class="sxs-lookup"><span data-stu-id="57852-218">The GUID is used primarily for COM support.</span></span>  
  
-   <span data-ttu-id="57852-219">Метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> правильно выполняет синтаксический анализ строк, содержащих даты в коротком формате в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-219">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-220">Тем не менее он не поддерживает совместимость с синтаксическим анализом изменений даты и времени, описанным в статьях базы знаний Microsoft: [KB2803771](http://support.microsoft.com/kb/2803771) и [KB2803755](http://support.microsoft.com/kb/2803755).</span><span class="sxs-lookup"><span data-stu-id="57852-220">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](http://support.microsoft.com/kb/2803771) and [KB2803755](http://support.microsoft.com/kb/2803755).</span></span>  
  
-   <span data-ttu-id="57852-221"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")` правильно округляется в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-221"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-222">В некоторых версиях среды CLR, результирующая строка усекается вместо округления.</span><span class="sxs-lookup"><span data-stu-id="57852-222">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a><span data-ttu-id="57852-223">Различия HttpClient</span><span class="sxs-lookup"><span data-stu-id="57852-223">HttpClient differences</span></span>  
 <span data-ttu-id="57852-224">В [!INCLUDE[net_native](../../../includes/net-native-md.md)]класс <xref:System.Net.Http.HttpClientHandler> внутренним образом использует WinINet (через класс [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) вместо классов <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> , используемых в стандартных приложениях .NET для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="57852-224">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="57852-225">WinINet не поддерживает все параметры конфигурации, которые поддерживает класс <xref:System.Net.Http.HttpClientHandler> .</span><span class="sxs-lookup"><span data-stu-id="57852-225">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="57852-226">Это приводит к следующим результатам.</span><span class="sxs-lookup"><span data-stu-id="57852-226">As a result:</span></span>  
  
-   <span data-ttu-id="57852-227">Некоторые свойства возможности на <xref:System.Net.Http.HttpClientHandler> возвращают `false` на [!INCLUDE[net_native](../../../includes/net-native-md.md)], в то время как они возвращают `true` в стандартных приложениях .NET для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="57852-227">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas they return `true` in the standard .NET for Windows Store apps.</span></span>  
  
-   <span data-ttu-id="57852-228">Некоторые методы доступа к свойству конфигурации `get` всегда возвращают фиксированное значение на [!INCLUDE[net_native](../../../includes/net-native-md.md)] , которое отличается от настраиваемого значения по умолчанию в приложениях .NET для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="57852-228">Some of the configuration property `get` accessors always return a fixed value on [!INCLUDE[net_native](../../../includes/net-native-md.md)] that is different than the default configurable value in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="57852-229">В следующих подразделах описаны некоторые дополнительные различия в поведении.</span><span class="sxs-lookup"><span data-stu-id="57852-229">Some additional behavior differences are covered in the following subsections.</span></span>  
  
 <span data-ttu-id="57852-230">**Прокси-сервер**</span><span class="sxs-lookup"><span data-stu-id="57852-230">**Proxy**</span></span>  
  
 <span data-ttu-id="57852-231">Класс [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) не поддерживает настройку или переопределение прокси для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="57852-231">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="57852-232">Это означает, что все запросы на [!INCLUDE[net_native](../../../includes/net-native-md.md)] используют системные настройки прокси-сервера или прокси-сервер, в зависимости от значения свойства <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57852-232">This means that all requests on [!INCLUDE[net_native](../../../includes/net-native-md.md)] use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="57852-233">В приложениях .NET для магазина Windows, прокси-сервер определяется свойством <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57852-233">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="57852-234">В [!INCLUDE[net_native](../../../includes/net-native-md.md)] настройка <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> на значение, отличное от `null`, вызывает исключение <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="57852-234">On [!INCLUDE[net_native](../../../includes/net-native-md.md)], setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="57852-235">Свойство <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> возвращает `false` на [!INCLUDE[net_native](../../../includes/net-native-md.md)], в то время как оно возвращает `true` в стандартных приложениях .NET Framework для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="57852-235">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>  
  
 <span data-ttu-id="57852-236">**Автоматическое перенаправление**</span><span class="sxs-lookup"><span data-stu-id="57852-236">**Automatic redirection**</span></span>  
  
 <span data-ttu-id="57852-237">Класс [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) не разрешает настройку максимального числа автоматических перенаправлений.</span><span class="sxs-lookup"><span data-stu-id="57852-237">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="57852-238">Значение свойства <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> равно 50 по умолчанию в стандартных приложениях .NET для магазина Windows и может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="57852-238">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="57852-239">На [!INCLUDE[net_native](../../../includes/net-native-md.md)], значение этого свойства равно 10 и попытка его изменить вызывает исключение <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="57852-239">On [!INCLUDE[net_native](../../../includes/net-native-md.md)], the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="57852-240">Свойство <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> возвращает `false` на [!INCLUDE[net_native](../../../includes/net-native-md.md)], в то время как оно возвращает `true` в приложениях .NET для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="57852-240">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas it returns `true` in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="57852-241">**Автоматическая распаковка**</span><span class="sxs-lookup"><span data-stu-id="57852-241">**Automatic decompression**</span></span>  
  
 <span data-ttu-id="57852-242">Приложения .NET для магазина Windows позволяют задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> на <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip> или <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="57852-242">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="57852-243"> поддерживает <xref:System.Net.DecompressionMethods.Deflate> только вместе с <xref:System.Net.DecompressionMethods.GZip>или <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="57852-243"> only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="57852-244">При попытке задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> только на <xref:System.Net.DecompressionMethods.Deflate> или <xref:System.Net.DecompressionMethods.GZip> происходит его автоматическое задание на оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip>.</span><span class="sxs-lookup"><span data-stu-id="57852-244">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>  
  
 <span data-ttu-id="57852-245">**Файлы cookie**</span><span class="sxs-lookup"><span data-stu-id="57852-245">**Cookies**</span></span>  
  
 <span data-ttu-id="57852-246">Обработка файлов cookie выполняется одновременно с <xref:System.Net.Http.HttpClient> и WinINet.</span><span class="sxs-lookup"><span data-stu-id="57852-246">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="57852-247">Файлы cookie из <xref:System.Net.CookieContainer> объединяются вместе файла cookie в кэше WinINet cookie.</span><span class="sxs-lookup"><span data-stu-id="57852-247">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="57852-248">Удаление файла cookie из <xref:System.Net.CookieContainer> запрещает <xref:System.Net.Http.HttpClient> отправлять файл cookie, но если файл cookie уже был просмотрен WinINet и файлы "cookie" не были удалены пользователем, WinINet отправляет его.</span><span class="sxs-lookup"><span data-stu-id="57852-248">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="57852-249">Не существует средств программного удаления файла cookie из WinINet с использованием API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>или <xref:System.Net.CookieContainer> .</span><span class="sxs-lookup"><span data-stu-id="57852-249">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="57852-250">Задание свойства <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> на `false` вызывает только <xref:System.Net.Http.HttpClient>, чтобы остановить отправку файлов "cookie"; WinINet может по-прежнему включить свои файлы cookie в запрос.</span><span class="sxs-lookup"><span data-stu-id="57852-250">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>  
  
 <span data-ttu-id="57852-251">**Учетные данные**</span><span class="sxs-lookup"><span data-stu-id="57852-251">**Credentials**</span></span>  
  
 <span data-ttu-id="57852-252">В приложениях .NET для магазина Windows свойства <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> и <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType>работают независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="57852-252">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="57852-253">Кроме того, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> принимает любой объект, реализующий интерфейс <xref:System.Net.ICredentials> .</span><span class="sxs-lookup"><span data-stu-id="57852-253">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="57852-254">В [!INCLUDE[net_native](../../../includes/net-native-md.md)]задание свойства <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> на `true` устанавливает свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> в `null`.</span><span class="sxs-lookup"><span data-stu-id="57852-254">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="57852-255">Кроме этого, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> может быть задано только в `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>или объект типа <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="57852-255">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="57852-256">Назначение любого другого объекта <xref:System.Net.ICredentials> , наиболее популярный из которых <xref:System.Net.CredentialCache>, свойству <xref:System.Net.Http.HttpClientHandler.Credentials%2A> вызывает исключение <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="57852-256">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>  
  
 <span data-ttu-id="57852-257">**Другие неподдерживаемые и ненастраиваемые функции**</span><span class="sxs-lookup"><span data-stu-id="57852-257">**Other unsupported or unconfigurable features**</span></span>  
  
 <span data-ttu-id="57852-258">В [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="57852-258">In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
-   <span data-ttu-id="57852-259">Значение свойства <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> всегда <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="57852-259">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="57852-260">В приложения .NET для магазина Windows, по умолчанию используется <xref:System.Net.Http.ClientCertificateOption.Manual>.</span><span class="sxs-lookup"><span data-stu-id="57852-260">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>  
  
-   <span data-ttu-id="57852-261">Свойство <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> не настраивается.</span><span class="sxs-lookup"><span data-stu-id="57852-261">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>  
  
-   <span data-ttu-id="57852-262">Свойство <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> всегда имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="57852-262">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="57852-263">В приложения .NET для магазина Windows, по умолчанию используется `false`.</span><span class="sxs-lookup"><span data-stu-id="57852-263">In .NET for Windows Store apps, the default is `false`.</span></span>  
  
-   <span data-ttu-id="57852-264">Заголовок `SetCookie2` в ответах игнорируется как устаревший.</span><span class="sxs-lookup"><span data-stu-id="57852-264">The `SetCookie2` header in responses is ignored as obsolete.</span></span>  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a><span data-ttu-id="57852-265">Различия взаимодействия</span><span class="sxs-lookup"><span data-stu-id="57852-265">Interop differences</span></span>  
 <span data-ttu-id="57852-266">**Устаревшие интерфейсы API**</span><span class="sxs-lookup"><span data-stu-id="57852-266">**Deprecated APIs**</span></span>  
  
 <span data-ttu-id="57852-267">Не рекомендуется использовать несколько редко применяемых API-интерфейсов для взаимодействия с управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="57852-267">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="57852-268">При использовании с [!INCLUDE[net_native](../../../includes/net-native-md.md)]эти API-интерфейсы могут вызывать исключение <xref:System.NotImplementedException> или <xref:System.PlatformNotSupportedException> или приводят к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="57852-268">When used with [!INCLUDE[net_native](../../../includes/net-native-md.md)], these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="57852-269">В приложениях .NET для магазина Windows эти API-интерфейсы отмечены как устаревшие, хотя их вызов создает предупреждение компилятора, а не ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="57852-269">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>  
  
 <span data-ttu-id="57852-270">Устаревшие API-интерфейсы для маршалинга `VARIANT` :</span><span class="sxs-lookup"><span data-stu-id="57852-270">Deprecated APIs for `VARIANT` marshaling:</span></span>  
  
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
  
 <span data-ttu-id="57852-271"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>поддерживается, но выдает исключение в некоторых сценариях, например при использовании с [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) или ByRef.</span><span class="sxs-lookup"><span data-stu-id="57852-271"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) or byref variants.</span></span>  
  
 <span data-ttu-id="57852-272">Устаревшие интерфейсы API для поддержки [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) :</span><span class="sxs-lookup"><span data-stu-id="57852-272">Deprecated APIs for [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) support:</span></span>  
  
|<span data-ttu-id="57852-273">Тип</span><span class="sxs-lookup"><span data-stu-id="57852-273">Type</span></span>|<span data-ttu-id="57852-274">Член</span><span class="sxs-lookup"><span data-stu-id="57852-274">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>|<span data-ttu-id="57852-275">Атрибут не поддерживается</span><span class="sxs-lookup"><span data-stu-id="57852-275">Attribute isn't supported</span></span>|  
  
 <span data-ttu-id="57852-276">Устаревшие интерфейсы API для классических COM-событий:</span><span class="sxs-lookup"><span data-stu-id="57852-276">Deprecated APIs for classic COM events:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 <span data-ttu-id="57852-277">Устаревшие интерфейсы API в интерфейсе <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>, который не поддерживается в [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="57852-277">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
|<span data-ttu-id="57852-278">Тип</span><span class="sxs-lookup"><span data-stu-id="57852-278">Type</span></span>|<span data-ttu-id="57852-279">Член</span><span class="sxs-lookup"><span data-stu-id="57852-279">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>|<span data-ttu-id="57852-280">Все члены.</span><span class="sxs-lookup"><span data-stu-id="57852-280">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>|<span data-ttu-id="57852-281">Все члены.</span><span class="sxs-lookup"><span data-stu-id="57852-281">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>|<span data-ttu-id="57852-282">Все члены.</span><span class="sxs-lookup"><span data-stu-id="57852-282">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=nameWithType>|  
  
 <span data-ttu-id="57852-283">Другие неподдерживаемые функции взаимодействия:</span><span class="sxs-lookup"><span data-stu-id="57852-283">Other unsupported interop features:</span></span>  
  
|<span data-ttu-id="57852-284">Тип</span><span class="sxs-lookup"><span data-stu-id="57852-284">Type</span></span>|<span data-ttu-id="57852-285">Член</span><span class="sxs-lookup"><span data-stu-id="57852-285">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>|<span data-ttu-id="57852-286">Все члены.</span><span class="sxs-lookup"><span data-stu-id="57852-286">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>|<span data-ttu-id="57852-287">Все члены.</span><span class="sxs-lookup"><span data-stu-id="57852-287">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 <span data-ttu-id="57852-288">Редко используемые интерфейсы API маршалинга:</span><span class="sxs-lookup"><span data-stu-id="57852-288">Rarely used marshalling APIs:</span></span>  
  
|<span data-ttu-id="57852-289">Тип</span><span class="sxs-lookup"><span data-stu-id="57852-289">Type</span></span>|<span data-ttu-id="57852-290">Член</span><span class="sxs-lookup"><span data-stu-id="57852-290">Member</span></span>|  
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
  
 <span data-ttu-id="57852-291">**Вызов неуправляемого кода и совместимость взаимодействия COM**</span><span class="sxs-lookup"><span data-stu-id="57852-291">**Platform invoke and COM interop compatibility**</span></span>  
  
 <span data-ttu-id="57852-292">Большинство вызовов неуправляемого кода и сценариев COM-взаимодействия по-прежнему поддерживается в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-292">Most platform invoke and COM interop scenarios are still supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-293">В частности, поддерживаются все взаимодействия с API среды выполнения Windows (WinRT) и весь необходимый маршалинг для среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="57852-293">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="57852-294">Это включает поддержку маршалинга:</span><span class="sxs-lookup"><span data-stu-id="57852-294">This includes marshaling support for:</span></span>  
  
-   <span data-ttu-id="57852-295">Массивы (включая <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="57852-295">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>  
  
-   `BStr`  
  
-   <span data-ttu-id="57852-296">Делегаты</span><span class="sxs-lookup"><span data-stu-id="57852-296">Delegates</span></span>  
  
-   <span data-ttu-id="57852-297">Строки (Юникод, Ansi и HSTRING)</span><span class="sxs-lookup"><span data-stu-id="57852-297">Strings (Unicode, Ansi, and HSTRING)</span></span>  
  
-   <span data-ttu-id="57852-298">Структуры (`byref` и `byval`)</span><span class="sxs-lookup"><span data-stu-id="57852-298">Structs (`byref` and `byval`)</span></span>  
  
-   <span data-ttu-id="57852-299">Объединения</span><span class="sxs-lookup"><span data-stu-id="57852-299">Unions</span></span>  
  
-   <span data-ttu-id="57852-300">Дескрипторы Win32</span><span class="sxs-lookup"><span data-stu-id="57852-300">Win32 handles</span></span>  
  
-   <span data-ttu-id="57852-301">Все конструкции WinRT</span><span class="sxs-lookup"><span data-stu-id="57852-301">All WinRT constructs</span></span>  
  
-   <span data-ttu-id="57852-302">Частичная поддержка маршалинга типов variant.</span><span class="sxs-lookup"><span data-stu-id="57852-302">Partial support for marshaling variant types.</span></span> <span data-ttu-id="57852-303">Поддерживаются следующие функции:</span><span class="sxs-lookup"><span data-stu-id="57852-303">The following are supported:</span></span>  
  
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
  
    -   [<span data-ttu-id="57852-304">IUnknown</span><span class="sxs-lookup"><span data-stu-id="57852-304">IUnknown</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms680509.aspx)  
  
 <span data-ttu-id="57852-305">Однако, [!INCLUDE[net_native](../../../includes/net-native-md.md)] не поддерживается следующее:</span><span class="sxs-lookup"><span data-stu-id="57852-305">However, [!INCLUDE[net_native](../../../includes/net-native-md.md)] doesn't support the following:</span></span>  
  
-   <span data-ttu-id="57852-306">использование классических COM-событий</span><span class="sxs-lookup"><span data-stu-id="57852-306">Using classic COM events</span></span>  
  
-   <span data-ttu-id="57852-307">Реализация интерфейса <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> на управляемом типе</span><span class="sxs-lookup"><span data-stu-id="57852-307">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>  
  
-   <span data-ttu-id="57852-308">Реализация [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) интерфейса на управляемом типе через <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> атрибута.</span><span class="sxs-lookup"><span data-stu-id="57852-308">Implementing the [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="57852-309">Однако, обратите внимание, что нельзя вызывать COM-объекты через `IDispatch`, а управляемый объект не может реализовать `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="57852-309">However, note that you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>  
  
 <span data-ttu-id="57852-310">Использование отражения для вызова метода неуправляемого кода не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57852-310">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="57852-311">Это ограничение можно обойти путем заключения вызова метода в другой метод, вместо этого используя вызов оболочки.</span><span class="sxs-lookup"><span data-stu-id="57852-311">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="57852-312">Другие отличия от API-интерфейсов приложений .NET для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="57852-312">Other differences from .NET APIs for Windows Store apps</span></span>  
 <span data-ttu-id="57852-313">В этом разделе перечислены остальные интерфейсы API, которые не поддерживаются в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-313">This section lists the remaining APIs that aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-314">Самый большой набор неподдерживаемых интерфейсов API — это API-интерфейсы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="57852-314">The largest set of the unsupported APIs are Windows Communication Foundation (WCF) APIs.</span></span>  
  
 <span data-ttu-id="57852-315">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="57852-315">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>  
  
 <span data-ttu-id="57852-316">Типы в пространствах имен <xref:System.ComponentModel.DataAnnotations> и <xref:System.ComponentModel.DataAnnotations.Schema> не поддерживаются в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-316">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-317">К ним относятся следующие типы, которые присутствуют в приложениях .NET для магазина Windows для Windows 8:</span><span class="sxs-lookup"><span data-stu-id="57852-317">These include the following types that are present in the .NET for Windows Store apps for Windows 8:</span></span>  
  
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
  
 <span data-ttu-id="57852-318">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="57852-318">**Visual Basic**</span></span>  
  
 <span data-ttu-id="57852-319">Visual Basic не поддерживается в настоящее время в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-319">Visual Basic isn't currently supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-320">Следующие типы в пространствах имен <xref:Microsoft.VisualBasic> и <xref:Microsoft.VisualBasic.CompilerServices> недоступны в [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="57852-320">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
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
  
 <span data-ttu-id="57852-321">**Контекст отражения (пространство имен System.Reflection.Context)**</span><span class="sxs-lookup"><span data-stu-id="57852-321">**Reflection Context (System.Reflection.Context namespace)**</span></span>  
  
 <span data-ttu-id="57852-322">Класс <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> не поддерживается в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-322">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="57852-323">**Часы реального времени (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="57852-323">**RTC (System.Net.Http.Rtc)**</span></span>  
  
 <span data-ttu-id="57852-324">Класс <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> не поддерживается в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-324">The <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> class isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="57852-325">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="57852-325">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>  
  
 <span data-ttu-id="57852-326">Типы в [пространствах имен System.ServiceModel.*](http://msdn.microsoft.com/library/gg145010.aspx) не поддерживаются в [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57852-326">The types in the [System.ServiceModel.* namespaces](http://msdn.microsoft.com/library/gg145010.aspx) aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="57852-327">В число этих типов входят следующие:</span><span class="sxs-lookup"><span data-stu-id="57852-327">These includes the following types:</span></span>  
  
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
  
### <a name="differences-in-serializers"></a><span data-ttu-id="57852-328">Различия в сериализаторах</span><span class="sxs-lookup"><span data-stu-id="57852-328">Differences in serializers</span></span>  
 <span data-ttu-id="57852-329">Существуют следующие различия, касающиеся сериализации и десериализации с классами <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>и <xref:System.Xml.Serialization.XmlSerializer> :</span><span class="sxs-lookup"><span data-stu-id="57852-329">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>  
  
-   <span data-ttu-id="57852-330">В [!INCLUDE[net_native](../../../includes/net-native-md.md)], <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> не удается сериализовать или десериализовать производный класс, имеющий член базового класса, тип которого не является корневым тип сериализации.</span><span class="sxs-lookup"><span data-stu-id="57852-330">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="57852-331">Например, в следующем коде при сериализации или десериализации `Y` возникает ошибка:</span><span class="sxs-lookup"><span data-stu-id="57852-331">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     <span data-ttu-id="57852-332">Тип `InnerType` не известен сериализатору, так как члены базового класса не передаются во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="57852-332">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>  
  
-   <span data-ttu-id="57852-333"><xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> не удается сериализовать класс или структуру, которая реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="57852-333"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="57852-334">Например, не удается сериализовать или десериализовать следующие типы:</span><span class="sxs-lookup"><span data-stu-id="57852-334">For example, the following types fail to serialize or deserialize:</span></span>  
  
  
  
-   <span data-ttu-id="57852-335"><xref:System.Xml.Serialization.XmlSerializer> не удается сериализовать следующие значения объекта, так как он не знает точный тип объекта для сериализации:</span><span class="sxs-lookup"><span data-stu-id="57852-335"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>  
  
  
  
-   <span data-ttu-id="57852-336"><xref:System.Xml.Serialization.XmlSerializer> не удается сериализация или десериализация, если тип сериализованного объекта <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="57852-336"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>  
  
-   <span data-ttu-id="57852-337">Все сериализаторам (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и <xref:System.Xml.Serialization.XmlSerializer>) не удается создать код сериализации для типа <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> или типа, содержащего <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="57852-337">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="57852-338">Вместо этого они отображают ошибки во время построения.</span><span class="sxs-lookup"><span data-stu-id="57852-338">They display build-time errors instead.</span></span>  
  
-   <span data-ttu-id="57852-339">Следующие конструкторы типов сериализации не обязательно работают, как должны:</span><span class="sxs-lookup"><span data-stu-id="57852-339">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>  
  
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
  
-   <span data-ttu-id="57852-340"><xref:System.Xml.Serialization.XmlSerializer> не удается создать код для типа, который содержит методы, определенные любым из следующих атрибутов:</span><span class="sxs-lookup"><span data-stu-id="57852-340"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <span data-ttu-id="57852-341"><xref:System.Xml.Serialization.XmlSerializer> не поддерживает настраиваемый интерфейс сериализации <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="57852-341"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="57852-342">Если имеется класс, реализующий этот интерфейс, <xref:System.Xml.Serialization.XmlSerializer> рассматривает тип, как тип объекта (POCO) простой старой среды CLR и сериализует только его открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="57852-342">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>  
  
-   <span data-ttu-id="57852-343">Сериализация простого объекта <xref:System.Exception> , как указано ниже, плохо работает с <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span><span class="sxs-lookup"><span data-stu-id="57852-343">Serializing a plain <xref:System.Exception> object, such as the following, doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a><span data-ttu-id="57852-344">Различия в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="57852-344">Visual Studio differences</span></span>  
 <span data-ttu-id="57852-345">**Исключения и отладка**</span><span class="sxs-lookup"><span data-stu-id="57852-345">**Exceptions and debugging**</span></span>  
  
 <span data-ttu-id="57852-346">При запуске приложений, скомпилированных с помощью [!INCLUDE[net_native](../../../includes/net-native-md.md)] в отладчике исключения первого шанса включены для следующих типов исключений:</span><span class="sxs-lookup"><span data-stu-id="57852-346">When you're running apps compiled by using [!INCLUDE[net_native](../../../includes/net-native-md.md)] in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 <span data-ttu-id="57852-347">**Создание приложений**</span><span class="sxs-lookup"><span data-stu-id="57852-347">**Building apps**</span></span>  
  
 <span data-ttu-id="57852-348">Используйте средства построения x 86, которые используются по умолчанию в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="57852-348">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="57852-349">Не рекомендуется использование средств AMD64 MSBuild, которые находятся в C:\Program Files (x86)\MSBuild\12.0\bin\amd64; Это может создать проблемы построения.</span><span class="sxs-lookup"><span data-stu-id="57852-349">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>  
  
 <span data-ttu-id="57852-350">**Профилировщики**</span><span class="sxs-lookup"><span data-stu-id="57852-350">**Profilers**</span></span>  
  
-   <span data-ttu-id="57852-351">Профилировщик ЦП в Visual Studio и профилировщик памяти XAML неправильно отображают «только мой код».</span><span class="sxs-lookup"><span data-stu-id="57852-351">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>  
  
-   <span data-ttu-id="57852-352">Профилировщик памяти XAML неточно отображает данные управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="57852-352">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>  
  
-   <span data-ttu-id="57852-353">Профилировщик ЦП неправильно идентифицирует модули и отображает имена функций с префиксами.</span><span class="sxs-lookup"><span data-stu-id="57852-353">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>  
  
 <span data-ttu-id="57852-354">**Проекты модульных тестов библиотеки**</span><span class="sxs-lookup"><span data-stu-id="57852-354">**Unit Test Library projects**</span></span>  
  
 <span data-ttu-id="57852-355">Включение [!INCLUDE[net_native](../../../includes/net-native-md.md)] для библиотеки модульного тестирования проекта приложений для магазина Windows не поддерживается и приводит к сбою построения проекта.</span><span class="sxs-lookup"><span data-stu-id="57852-355">Enabling [!INCLUDE[net_native](../../../includes/net-native-md.md)] on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57852-356">См. также</span><span class="sxs-lookup"><span data-stu-id="57852-356">See Also</span></span>  
 [<span data-ttu-id="57852-357">Начало работы</span><span class="sxs-lookup"><span data-stu-id="57852-357">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="57852-358">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="57852-358">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="57852-359">Обзор приложений .NET для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="57852-359">.NET For Windows Store apps overview</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [<span data-ttu-id="57852-360">Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="57852-360">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
