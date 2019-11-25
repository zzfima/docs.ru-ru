---
title: Использование и отладка сборок с возможностью выгрузки в .NET Core
description: Сведения об использовании собираемого AssemblyLoadContext для загрузки и выгрузки управляемых сборок, а также об отладке проблем, препятствующих успешной выгрузке.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 462e6d2c7f135d2ba274d78fe31ad27391eac416
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740447"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="c17b9-103">Использование и отладка сборок с возможностью выгрузки в .NET Core</span><span class="sxs-lookup"><span data-stu-id="c17b9-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="c17b9-104">Начиная с .NET Core 3.0 поддерживается возможность загрузки и последующей выгрузки набора сборок.</span><span class="sxs-lookup"><span data-stu-id="c17b9-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="c17b9-105">В .NET Framework для этой цели использовались пользовательские домены приложений, но .NET Core поддерживает только один домен приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c17b9-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="c17b9-106">.NET Core 3.0 и более поздние версии поддерживают выгрузку с помощью <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="c17b9-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="c17b9-107">Вы можете загрузить набор сборок в собираемые `AssemblyLoadContext`, выполнять в них методы или просто проверять их с помощью отражения и, наконец, выгрузить `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="c17b9-108">Эта операция выгружает сборки, загруженные в `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-108">That unloads the assemblies loaded into the `AssemblyLoadContext`.</span></span>

<span data-ttu-id="c17b9-109">Между выгрузкой с помощью `AssemblyLoadContext` и доменов приложений есть одно важное различие.</span><span class="sxs-lookup"><span data-stu-id="c17b9-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="c17b9-110">При использовании доменов приложений выгрузка выполняется принудительно.</span><span class="sxs-lookup"><span data-stu-id="c17b9-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="c17b9-111">В момент выгрузки все потоки, работающие в целевом домене приложения, прерываются, управляемые COM-объекты, созданные в целевом домене приложения, уничтожаются и т. д.</span><span class="sxs-lookup"><span data-stu-id="c17b9-111">At unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, and so on.</span></span> <span data-ttu-id="c17b9-112">При использовании `AssemblyLoadContext` выгрузка выполняется в режиме "сотрудничества".</span><span class="sxs-lookup"><span data-stu-id="c17b9-112">With `AssemblyLoadContext`, the unload is "cooperative".</span></span> <span data-ttu-id="c17b9-113">Вызов метода <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> просто инициирует выгрузку.</span><span class="sxs-lookup"><span data-stu-id="c17b9-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="c17b9-114">Выгрузка завершается после того, как:</span><span class="sxs-lookup"><span data-stu-id="c17b9-114">The unloading finishes after:</span></span>

- <span data-ttu-id="c17b9-115">Ни один из потоков не имеет методов из сборок, загруженных в `AssemblyLoadContext` в стеках вызовов.</span><span class="sxs-lookup"><span data-stu-id="c17b9-115">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="c17b9-116">Ни на один из типов из сборок, загруженных в `AssemblyLoadContext`, экземпляры этих типов и сами сборки не ссылаются:</span><span class="sxs-lookup"><span data-stu-id="c17b9-116">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types, and the assemblies themselves are referenced by:</span></span>
  - <span data-ttu-id="c17b9-117">Ссылки за пределами `AssemblyLoadContext`, за исключением слабых ссылок (<xref:System.WeakReference> или <xref:System.WeakReference%601>).</span><span class="sxs-lookup"><span data-stu-id="c17b9-117">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="c17b9-118">Строгие дескрипторы сборщика мусора ([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) или [GCHandleType.Pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) как внутри, так и за пределами `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-118">Strong garbage collector (GC) handles ([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) or [GCHandleType.Pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="use-collectible-assemblyloadcontext"></a><span data-ttu-id="c17b9-119">Использование забираемого AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="c17b9-119">Use collectible AssemblyLoadContext</span></span>

<span data-ttu-id="c17b9-120">В этом разделе содержится подробное пошаговое руководство, в котором показан простой способ загрузки приложения .NET Core в собираемый `AssemblyLoadContext`, выполнения его точки входа и последующей выгрузки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="c17b9-121">Полный пример см. по адресу [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span><span class="sxs-lookup"><span data-stu-id="c17b9-121">You can find a complete sample at [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="c17b9-122">Создание собираемого AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="c17b9-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="c17b9-123">Необходимо получить класс от <xref:System.Runtime.Loader.AssemblyLoadContext> и перегрузить его метод <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c17b9-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c17b9-124">Этот метод разрешает ссылки на все сборки, которые являются зависимостями загруженных в `AssemblyLoadContext` сборок.</span><span class="sxs-lookup"><span data-stu-id="c17b9-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="c17b9-125">Следующий код является примером простейшего пользовательского `AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="c17b9-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="c17b9-126">Как видите, метод `Load` возвращает `null`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="c17b9-127">Это означает, что все сборки зависимостей загружаются в контекст по умолчанию, а новый контекст содержит только те сборки, которые были явно загружены в него.</span><span class="sxs-lookup"><span data-stu-id="c17b9-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="c17b9-128">Если требуется загрузить некоторые или все зависимости в `AssemblyLoadContext` тоже, можно использовать `AssemblyDependencyResolver` в методе `Load`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="c17b9-129">`AssemblyDependencyResolver` разрешает имена сборок в абсолютные пути к файлам сборки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths.</span></span> <span data-ttu-id="c17b9-130">Сопоставитель использует файл *.deps.json* и файлы сборки в каталоге основной сборки, загруженной в контекст.</span><span class="sxs-lookup"><span data-stu-id="c17b9-130">The resolver uses the *.deps.json* file and assembly files in the directory of the main assembly loaded into the context.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="c17b9-131">Использование пользовательского собираемого AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="c17b9-131">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="c17b9-132">В этом разделе предполагается, что используется более простая версия `TestAssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-132">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="c17b9-133">Вы можете создать экземпляр пользовательского `AssemblyLoadContext` и загрузить в него сборку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c17b9-133">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="c17b9-134">Для каждой сборки, на которую ссылается загруженная сборка, вызывается метод `TestAssemblyLoadContext.Load`, чтобы `TestAssemblyLoadContext` мог решить, откуда получить сборку.</span><span class="sxs-lookup"><span data-stu-id="c17b9-134">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="c17b9-135">В нашем случае он возвращает `null`, чтобы указать, что он должен быть загружен в контекст по умолчанию из расположений, используемых средой выполнения для загрузки сборок по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c17b9-135">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="c17b9-136">Теперь, когда сборка загружена, можно выполнить из нее метод.</span><span class="sxs-lookup"><span data-stu-id="c17b9-136">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="c17b9-137">Выполните метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="c17b9-137">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="c17b9-138">После возврата метода `Main` можно инициировать выгрузку путем вызова метода `Unload` для пользовательского `AssemblyLoadContext` или удаления имеющейся ссылки на `AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="c17b9-138">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="c17b9-139">Этого достаточно для выгрузки тестовой сборки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-139">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="c17b9-140">Давайте разместим все это в отдельном невстраиваемом методе, чтобы гарантировать, что, `TestAssemblyLoadContext`, `Assembly` и `MethodInfo` (`Assembly.EntryPoint`) не могут поддерживаться в активном состоянии ссылками слота стека (в реальных или введенных JIT локальных переменных).</span><span class="sxs-lookup"><span data-stu-id="c17b9-140">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="c17b9-141">Это поможет поддерживать `TestAssemblyLoadContext` и предотвратить выгрузку.</span><span class="sxs-lookup"><span data-stu-id="c17b9-141">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="c17b9-142">Кроме того, верните слабую ссылку на `AssemblyLoadContext`, чтобы можно было использовать его позже для обнаружения завершения выгрузки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-142">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="c17b9-143">Теперь эту функцию можно использовать для загрузки, выполнения и выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-143">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="c17b9-144">Однако выгрузка не завершается немедленно.</span><span class="sxs-lookup"><span data-stu-id="c17b9-144">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="c17b9-145">Как упоминалось ранее, она полагается на сборщика мусора для сбора всех объектов из тестовой сборки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-145">As previously mentioned, it relies on the garbage collector to collect all the objects from the test assembly.</span></span> <span data-ttu-id="c17b9-146">Во многих случаях нет необходимости ждать завершения выгрузки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-146">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="c17b9-147">Однако в некоторых случаях полезно знать, что выгрузка завершена.</span><span class="sxs-lookup"><span data-stu-id="c17b9-147">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="c17b9-148">Например, вы хотите удалить файл сборки, который был загружен в пользовательский `AssemblyLoadContext` с диска.</span><span class="sxs-lookup"><span data-stu-id="c17b9-148">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="c17b9-149">В этом случае можно использовать следующий фрагмент кода.</span><span class="sxs-lookup"><span data-stu-id="c17b9-149">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="c17b9-150">Он запускает сборку мусора и ожидает методы завершения ожидания в цикле, пока слабая ссылка на пользовательский `AssemblyLoadContext` не будет установлена на `null`, указывая, что целевой объект был собран.</span><span class="sxs-lookup"><span data-stu-id="c17b9-150">It triggers garbage collection and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="c17b9-151">В большинстве случаев требуется только один проход по циклу.</span><span class="sxs-lookup"><span data-stu-id="c17b9-151">In most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="c17b9-152">Однако в более сложных случаях, когда объекты, создаваемые кодом, выполняющимися в `AssemblyLoadContext`, имеют методы завершения, может потребоваться больше проходов.</span><span class="sxs-lookup"><span data-stu-id="c17b9-152">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="c17b9-153">Событие выгрузки</span><span class="sxs-lookup"><span data-stu-id="c17b9-153">The Unloading event</span></span>

<span data-ttu-id="c17b9-154">В некоторых случаях может потребоваться, чтобы код был загружен в пользовательский `AssemblyLoadContext` для выполнения очистки при инициации выгрузки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-154">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="c17b9-155">Например, может потребоваться отключить потоки или очистить некоторые строгие дескрипторы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c17b9-155">For example, it may need to stop threads or clean up strong GC handles.</span></span> <span data-ttu-id="c17b9-156">В таких случаях можно использовать событие `Unloading`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-156">The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="c17b9-157">Обработчик, выполняющий необходимую очистку, может быть подключен к этому событию.</span><span class="sxs-lookup"><span data-stu-id="c17b9-157">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="c17b9-158">Устранение проблем с выгрузкой</span><span class="sxs-lookup"><span data-stu-id="c17b9-158">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="c17b9-159">Из-за сотрудничающей природы выгрузки можно легко забыть о ссылках, которые поддерживают активность элементов в собираемом `AssemblyLoadContext` и предотвращают выгрузку.</span><span class="sxs-lookup"><span data-stu-id="c17b9-159">Due to the cooperative nature of the unloading, it's easy to forget about references that may be keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="c17b9-160">Ниже описываются сущности (некоторые из них не очевидны), которые могут содержать ссылки:</span><span class="sxs-lookup"><span data-stu-id="c17b9-160">Here is a summary of entities (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="c17b9-161">Обычные ссылки за пределами собираемого `AssemblyLoadContext`, хранящегося в слоте стека или в регистре процессора (локальные переменные метода, явно созданные пользовательским кодом или неявно JIT-компилятором), статическая переменная или строгий/закрепляющий обработчик сборки мусора, транзитивно указывающие на следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="c17b9-161">Regular references held from outside of the collectible `AssemblyLoadContext` that are stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the just-in-time (JIT) compiler), a static variable, or a strong (pinning) GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="c17b9-162">Сборка, загруженная в собираемый `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-162">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="c17b9-163">Тип из такой сборки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-163">A type from such an assembly.</span></span>
  - <span data-ttu-id="c17b9-164">Экземпляр типа из такой сборки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-164">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="c17b9-165">Потоки, выполняющие код из сборки, загруженной в собираемый `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-165">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="c17b9-166">Экземпляры пользовательских несобираемых типов `AssemblyLoadContext`, созданных в собираемом `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-166">Instances of custom, non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="c17b9-167">Ожидающие обработки экземпляры <xref:System.Threading.RegisteredWaitHandle> с обратными вызовами, настроенными на методы в пользовательском `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-167">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`.</span></span>

> [!TIP]
> <span data-ttu-id="c17b9-168">Ссылки на объекты, которые хранятся в слотах стека или регистрах процессора и которые могут предотвратить выгрузку `AssemblyLoadContext`, могут возникать в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="c17b9-168">Object references that are stored in stack slots or processor registers and that could prevent unloading of an `AssemblyLoadContext` can occur in the following situations:</span></span>
>
> - <span data-ttu-id="c17b9-169">Когда результаты вызова функции передаются непосредственно в другую функцию, несмотря на отсутствие созданной пользователем локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="c17b9-169">When function call results are passed directly to another function, even though there is no user-created local variable.</span></span>
> - <span data-ttu-id="c17b9-170">Когда JIT-компилятор сохраняет ссылку на объект, который был доступен в определенный момент в методе.</span><span class="sxs-lookup"><span data-stu-id="c17b9-170">When the JIT compiler keeps a reference to an object that was available at some point in a method.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="c17b9-171">Отладка проблем с выгрузкой</span><span class="sxs-lookup"><span data-stu-id="c17b9-171">Debug unloading issues</span></span>

<span data-ttu-id="c17b9-172">Отладка проблем с выгрузкой может быть утомительной.</span><span class="sxs-lookup"><span data-stu-id="c17b9-172">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="c17b9-173">Иногда вы не знаете, что поддерживает активность `AssemblyLoadContext`, но выгрузка завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c17b9-173">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span> <span data-ttu-id="c17b9-174">Лучшим решением станет WinDbg (LLDB в UNIX) с подключаемым модулем SOS.</span><span class="sxs-lookup"><span data-stu-id="c17b9-174">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="c17b9-175">Необходимо найти сведения о том, что поддерживает активность `LoaderAllocator`, принадлежащего конкретному `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-175">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span> <span data-ttu-id="c17b9-176">Подключаемый модуль SOS позволяет просматривать объекты кучи GC, их иерархии и корни.</span><span class="sxs-lookup"><span data-stu-id="c17b9-176">The SOS plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>

<span data-ttu-id="c17b9-177">Чтобы загрузить подключаемый модуль в отладчик, введите следующую команду в командной строке отладчика:</span><span class="sxs-lookup"><span data-stu-id="c17b9-177">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="c17b9-178">В WinDbg (кажется, что WinDbg делает это автоматически при прерывании приложения .NET Core):</span><span class="sxs-lookup"><span data-stu-id="c17b9-178">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="c17b9-179">В LLDB:</span><span class="sxs-lookup"><span data-stu-id="c17b9-179">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="c17b9-180">Давайте выполним отладку примера программы, в которой возникли проблемы с выгрузкой.</span><span class="sxs-lookup"><span data-stu-id="c17b9-180">Let's debug an example program that has problems with unloading.</span></span> <span data-ttu-id="c17b9-181">Исходный код приводится ниже.</span><span class="sxs-lookup"><span data-stu-id="c17b9-181">Source code is included below.</span></span> <span data-ttu-id="c17b9-182">При запуске с помощью WinDbg программа переключается в отладчике сразу после попытки проверить успешность выгрузки.</span><span class="sxs-lookup"><span data-stu-id="c17b9-182">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="c17b9-183">После этого вы можете начать поиск причины проблемы.</span><span class="sxs-lookup"><span data-stu-id="c17b9-183">You can then start looking for the culprits.</span></span>

> [!TIP]
> <span data-ttu-id="c17b9-184">При отладке с помощью LLDB в Unix команды SOS в следующих примерах не содержат перед собой `!`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-184">If you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="c17b9-185">Эта команда выполняет дамп всех объектов с именем типа, содержащим `LoaderAllocator` в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="c17b9-185">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="c17b9-186">Пример:</span><span class="sxs-lookup"><span data-stu-id="c17b9-186">Here is an example:</span></span>

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48     
000002b78000ceb0 00007ffadc93a218       24     

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

<span data-ttu-id="c17b9-187">В разделе "Statistics:" ниже проверьте `MT` (`MethodTable`), который принадлежит `System.Reflection.LoaderAllocator`, и именно этот объект нас интересует.</span><span class="sxs-lookup"><span data-stu-id="c17b9-187">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="c17b9-188">Затем в списке в начале найдите запись с `MT`, соответствующим этому объекту, и получите адрес самого объекта.</span><span class="sxs-lookup"><span data-stu-id="c17b9-188">Then, in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="c17b9-189">В нашем случае это 000002b78000ce40.</span><span class="sxs-lookup"><span data-stu-id="c17b9-189">In our case, it is "000002b78000ce40".</span></span>

<span data-ttu-id="c17b9-190">Теперь, когда мы знаем адрес объекта `LoaderAllocator`, можно использовать другую команду для поиска его корней в сборке мусора:</span><span class="sxs-lookup"><span data-stu-id="c17b9-190">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots:</span></span>

```console
!gcroot -all 0x000002b78000ce40
```

<span data-ttu-id="c17b9-191">Эта команда выполняет дампы цепочки ссылок на объекты, ведущих к экземпляру `LoaderAllocator`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-191">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="c17b9-192">Список начинается с корня, который поддерживает активность `LoaderAllocator`, и, таким образом, является причиной проблемы.</span><span class="sxs-lookup"><span data-stu-id="c17b9-192">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem.</span></span> <span data-ttu-id="c17b9-193">Корнем может быть слот стека, регистр процессора, обработчик сборки мусора или статическая переменная.</span><span class="sxs-lookup"><span data-stu-id="c17b9-193">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="c17b9-194">Вот пример результата выходных данных команды `gcroot`:</span><span class="sxs-lookup"><span data-stu-id="c17b9-194">Here is an example of the output of the `gcroot` command:</span></span>

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

<span data-ttu-id="c17b9-195">Следующий шаг — выяснить, где находится корень, чтобы его можно было исправить.</span><span class="sxs-lookup"><span data-stu-id="c17b9-195">The next step is to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="c17b9-196">Самый простой случай: корень — это слот стека или регистр процессора.</span><span class="sxs-lookup"><span data-stu-id="c17b9-196">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="c17b9-197">В этом случае в `gcroot` отображается имя функции, фрейм которой содержит корень, и поток, в котором выполняется эта функция.</span><span class="sxs-lookup"><span data-stu-id="c17b9-197">In that case, the `gcroot` shows the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="c17b9-198">Сложный случай: корень является статической переменной или обработчиком сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c17b9-198">The difficult case is when the root is a static variable or a GC handle.</span></span>

<span data-ttu-id="c17b9-199">В предыдущем примере первый корень является локальной переменной типа `System.Reflection.RuntimeMethodInfo`, хранимого во фрейме функции `example.Program.Main(System.String[])` по адресу `rbp-20` (`rbp` — это регистр процессора `rbp`, а –20 — шестнадцатеричное смещение от этого регистра).</span><span class="sxs-lookup"><span data-stu-id="c17b9-199">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="c17b9-200">Второй корень является нормальным (строгим) `GCHandle`, который содержит ссылку на экземпляр класса `test.Test`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-200">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span>

<span data-ttu-id="c17b9-201">Третий корень является закрепленным `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-201">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="c17b9-202">На самом деле это статическая переменная, но к сожалению, нет способа определить это.</span><span class="sxs-lookup"><span data-stu-id="c17b9-202">This one is actually a static variable, but unfortunately, there is no way to tell.</span></span> <span data-ttu-id="c17b9-203">Статические переменные для ссылочных типов хранятся в управляемом массиве объектов во внутренних структурах среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c17b9-203">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="c17b9-204">Другой вариант, который может помешать выгрузке `AssemblyLoadContext`, — когда поток содержит фрейм метода из сборки, загруженной в стек `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-204">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="c17b9-205">Это можно проверить, выполнив дамп управляемых стеков вызовов всех потоков:</span><span class="sxs-lookup"><span data-stu-id="c17b9-205">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="c17b9-206">Команда означает "Применить ко всем потокам команду `!clrstack`".</span><span class="sxs-lookup"><span data-stu-id="c17b9-206">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="c17b9-207">Ниже приведен результат выполнения команды для примера.</span><span class="sxs-lookup"><span data-stu-id="c17b9-207">The following is the output of that command for the example.</span></span> <span data-ttu-id="c17b9-208">К сожалению, в LLDB в Unix нет способа применить команду ко всем потокам, поэтому необходимо будет вручную переключать потоки и повторять команду `clrstack`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-208">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you must manually switch threads and repeat the `clrstack` command.</span></span> <span data-ttu-id="c17b9-209">Игнорируйте все потоки, в которых отладчик сообщает: "Не удалось пройти по управляемому стеку".</span><span class="sxs-lookup"><span data-stu-id="c17b9-209">Ignore all threads where the debugger says "Unable to walk the managed stack".</span></span>

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998] 
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28] 
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0] 
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000 
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568] 
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0] 

```

<span data-ttu-id="c17b9-210">Как видите, последний поток имеет `test.Program.ThreadProc()`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-210">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="c17b9-211">Это функция из сборки, загруженной в `AssemblyLoadContext`, и поэтому она сохраняет активность `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="c17b9-211">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="c17b9-212">Пример источника с проблемами выгрузки</span><span class="sxs-lookup"><span data-stu-id="c17b9-212">Example source with unloadability issues</span></span>

<span data-ttu-id="c17b9-213">В предыдущем примере отладки используется следующий код.</span><span class="sxs-lookup"><span data-stu-id="c17b9-213">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="c17b9-214">Основная программа тестирования</span><span class="sxs-lookup"><span data-stu-id="c17b9-214">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="c17b9-215">Программа, загруженная в TestAssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="c17b9-215">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="c17b9-216">Следующий код представляет *test.dll*, переданный в метод `ExecuteAndUnload` в основной программе тестирования.</span><span class="sxs-lookup"><span data-stu-id="c17b9-216">The following code represents the *test.dll* passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
