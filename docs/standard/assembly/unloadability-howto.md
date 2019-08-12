---
title: Использование и отладка сборок с возможностью выгрузки в .NET Core
description: Сведения об использовании собираемого AssemblyLoadContext для загрузки и выгрузки управляемых сборок, а также об отладке проблем, препятствующих успешной выгрузке.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: a3ba2c2809aedd0af03ec965089f8779c430a335
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68671249"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="94715-103">Использование и отладка сборок с возможностью выгрузки в .NET Core</span><span class="sxs-lookup"><span data-stu-id="94715-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="94715-104">Начиная с .NET Core 3.0 поддерживается возможность загрузки и последующей выгрузки набора сборок.</span><span class="sxs-lookup"><span data-stu-id="94715-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="94715-105">В .NET Framework для этой цели использовались пользовательские домены приложений, но .NET Core поддерживает только один домен приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94715-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="94715-106">.NET Core 3.0 и более поздние версии поддерживают выгрузку с помощью <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="94715-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="94715-107">Вы можете загрузить набор сборок в собираемые `AssemblyLoadContext`, выполнять в них методы или просто проверять их с помощью отражения и, наконец, выгрузить `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="94715-108">Эта операция выгружает сборки, загруженные в `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-108">That unloads the assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="94715-109">Между выгрузкой с помощью `AssemblyLoadContext` и доменов приложений есть одно важное различие.</span><span class="sxs-lookup"><span data-stu-id="94715-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="94715-110">При использовании доменов приложений выгрузка выполняется принудительно.</span><span class="sxs-lookup"><span data-stu-id="94715-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="94715-111">В момент выгрузки все потоки, работающие в целевом домене приложения, прерываются, управляемые COM-объекты, созданные в целевом домене приложения, уничтожаются и т. д. При использовании `AssemblyLoadContext` выгрузка выполняется в режиме "сотрудничества".</span><span class="sxs-lookup"><span data-stu-id="94715-111">At the unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, etc. With `AssemblyLoadContext`, the unload is "cooperative".</span></span> <span data-ttu-id="94715-112">Вызов метода <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> просто инициирует выгрузку.</span><span class="sxs-lookup"><span data-stu-id="94715-112">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="94715-113">Выгрузка завершается после того, как:</span><span class="sxs-lookup"><span data-stu-id="94715-113">The unloading finishes after:</span></span>

- <span data-ttu-id="94715-114">Ни один из потоков не имеет методов из сборок, загруженных в `AssemblyLoadContext` в стеках вызовов.</span><span class="sxs-lookup"><span data-stu-id="94715-114">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="94715-115">Ни на один из типов из сборок, загруженных в `AssemblyLoadContext`, экземпляры этих типов и сами сборки за пределами `AssemblyLoadContext` не ссылаются:</span><span class="sxs-lookup"><span data-stu-id="94715-115">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types and the assemblies themselves outside of the `AssemblyLoadContext` are referenced by:</span></span>
  - <span data-ttu-id="94715-116">Ссылки за пределами `AssemblyLoadContext`, за исключением слабых ссылок (<xref:System.WeakReference> или <xref:System.WeakReference%601>).</span><span class="sxs-lookup"><span data-stu-id="94715-116">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="94715-117">Строгие дескрипторы сборки мусора (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span><span class="sxs-lookup"><span data-stu-id="94715-117">Strong GC handles (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span></span> <span data-ttu-id="94715-118">или <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) как внутри, так и вне `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-118">or <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="using-collectible-assemblyloadcontext"></a><span data-ttu-id="94715-119">Использование собираемого AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="94715-119">Using collectible AssemblyLoadContext</span></span>

<span data-ttu-id="94715-120">В этом разделе содержится подробное пошаговое руководство, в котором показан простой способ загрузки приложения .NET Core в собираемый `AssemblyLoadContext`, выполнения его точки входа и последующей выгрузки.</span><span class="sxs-lookup"><span data-stu-id="94715-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="94715-121">Полный пример см. по адресу <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading>.</span><span class="sxs-lookup"><span data-stu-id="94715-121">You can find a complete sample at <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading>.</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="94715-122">Создание собираемого AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="94715-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="94715-123">Необходимо получить класс от <xref:System.Runtime.Loader.AssemblyLoadContext> и перегрузить его метод <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94715-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="94715-124">Этот метод разрешает ссылки на все сборки, которые являются зависимостями загруженных в `AssemblyLoadContext` сборок.</span><span class="sxs-lookup"><span data-stu-id="94715-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>
<span data-ttu-id="94715-125">Следующий код является примером простейшего пользовательского `AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="94715-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="94715-126">Как видите, метод `Load` возвращает `null`.</span><span class="sxs-lookup"><span data-stu-id="94715-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="94715-127">Это означает, что все сборки зависимостей загружаются в контекст по умолчанию, а новый контекст содержит только те сборки, которые были явно загружены в него.</span><span class="sxs-lookup"><span data-stu-id="94715-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="94715-128">Если требуется загрузить некоторые или все зависимости в `AssemblyLoadContext` тоже, можно использовать `AssemblyDependencyResolver` в методе `Load`.</span><span class="sxs-lookup"><span data-stu-id="94715-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="94715-129">`AssemblyDependencyResolver` разрешает имена сборок в абсолютные пути к файлам сборки с помощью файла *.deps.json*, содержащегося в каталоге основной сборки, загруженной в контекст и использующей файлы сборки в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="94715-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths using the *.deps.json* file contained in the directory of the main assembly loaded into the context and using assembly files in that directory.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="94715-130">Использование пользовательского собираемого AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="94715-130">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="94715-131">В этом разделе предполагается, что используется более простая версия `TestAssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-131">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="94715-132">Вы можете создать экземпляр пользовательского `AssemblyLoadContext` и загрузить в него сборку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94715-132">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="94715-133">Для каждой сборки, на которую ссылается загруженная сборка, вызывается метод `TestAssemblyLoadContext.Load`, чтобы `TestAssemblyLoadContext` мог решить, откуда получить сборку.</span><span class="sxs-lookup"><span data-stu-id="94715-133">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="94715-134">В нашем случае он возвращает `null`, чтобы указать, что он должен быть загружен в контекст по умолчанию из расположений, используемых средой выполнения для загрузки сборок по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94715-134">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="94715-135">Теперь, когда сборка загружена, можно выполнить из нее метод.</span><span class="sxs-lookup"><span data-stu-id="94715-135">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="94715-136">Выполните метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="94715-136">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="94715-137">После возврата метода `Main` можно инициировать выгрузку путем вызова метода `Unload` для пользовательского `AssemblyLoadContext` или удаления имеющейся ссылки на `AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="94715-137">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="94715-138">Этого достаточно для выгрузки тестовой сборки.</span><span class="sxs-lookup"><span data-stu-id="94715-138">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="94715-139">Давайте разместим все это в отдельном невстраиваемом методе, чтобы гарантировать, что, `TestAssemblyLoadContext`, `Assembly` и `MethodInfo` (`Assembly.EntryPoint`) не могут поддерживаться в активном состоянии ссылками слота стека (в реальных или введенных JIT локальных переменных).</span><span class="sxs-lookup"><span data-stu-id="94715-139">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="94715-140">Это поможет поддерживать `TestAssemblyLoadContext` и предотвратить выгрузку.</span><span class="sxs-lookup"><span data-stu-id="94715-140">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="94715-141">Кроме того, верните слабую ссылку на `AssemblyLoadContext`, чтобы можно было использовать его позже для обнаружения завершения выгрузки.</span><span class="sxs-lookup"><span data-stu-id="94715-141">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="94715-142">Теперь эту функцию можно использовать для загрузки, выполнения и выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="94715-142">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="94715-143">Однако выгрузка не завершается немедленно.</span><span class="sxs-lookup"><span data-stu-id="94715-143">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="94715-144">Как упоминалось ранее, она полагается на сборку мусора для сбора всех объектов из тестовой сборки.</span><span class="sxs-lookup"><span data-stu-id="94715-144">As previously mentioned, it relies on the GC to collect all the objects from the test assembly.</span></span> <span data-ttu-id="94715-145">Во многих случаях нет необходимости ждать завершения выгрузки.</span><span class="sxs-lookup"><span data-stu-id="94715-145">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="94715-146">Однако в некоторых случаях полезно знать, что выгрузка завершена.</span><span class="sxs-lookup"><span data-stu-id="94715-146">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="94715-147">Например, вы хотите удалить файл сборки, который был загружен в пользовательский `AssemblyLoadContext` с диска.</span><span class="sxs-lookup"><span data-stu-id="94715-147">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="94715-148">В этом случае можно использовать следующий фрагмент кода.</span><span class="sxs-lookup"><span data-stu-id="94715-148">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="94715-149">Он запускает сборку мусора и ожидает методов завершения в цикле, пока слабая ссылка на пользовательский `AssemblyLoadContext` не будет установлена на `null`, указывая, что целевой объект был собран.</span><span class="sxs-lookup"><span data-stu-id="94715-149">It triggers a GC and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="94715-150">Обратите внимание, что в большинстве случаев требуется только один проход по циклу.</span><span class="sxs-lookup"><span data-stu-id="94715-150">Note that in most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="94715-151">Однако в более сложных случаях, когда объекты, создаваемые кодом, выполняющимися в `AssemblyLoadContext`, имеют методы завершения, может потребоваться больше проходов.</span><span class="sxs-lookup"><span data-stu-id="94715-151">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="94715-152">Событие выгрузки</span><span class="sxs-lookup"><span data-stu-id="94715-152">The Unloading event</span></span>

<span data-ttu-id="94715-153">В некоторых случаях может потребоваться, чтобы код был загружен в пользовательский `AssemblyLoadContext` для выполнения очистки при инициации выгрузки.</span><span class="sxs-lookup"><span data-stu-id="94715-153">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="94715-154">Например, может потребоваться отключить потоки, очистить некоторые строгие дескрипторы сборки мусора и т. д. В таких случаях можно использовать событие `Unloading`.</span><span class="sxs-lookup"><span data-stu-id="94715-154">For example, it may need to stop threads, clean up some strong GC handles, etc. The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="94715-155">Обработчик, выполняющий необходимую очистку, может быть подключен к этому событию.</span><span class="sxs-lookup"><span data-stu-id="94715-155">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="94715-156">Устранение проблем с выгрузкой</span><span class="sxs-lookup"><span data-stu-id="94715-156">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="94715-157">Из-за сотрудничающей природы выгрузки можно легко забыть о ссылках, которые поддерживают активность элементов в собираемом `AssemblyLoadContext` и предотвращают выгрузку.</span><span class="sxs-lookup"><span data-stu-id="94715-157">Due to the cooperative nature of the unloading, it's easy to forget about references keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="94715-158">Ниже описываются элементы (некоторые из них не очевидны), которые могут содержать ссылки:</span><span class="sxs-lookup"><span data-stu-id="94715-158">Here is a summary of things (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="94715-159">Обычные ссылки за пределами собираемого `AssemblyLoadContext`, хранящегося в слоте стека или в регистре процессора (локальные переменные метода, явно созданные пользовательским кодом или неявно — JIT), статическая переменная или строгий/закрепляющий обработчик сборки мусора, транзитивно указывающие на следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="94715-159">Regular references held from outside of the collectible `AssemblyLoadContext`, stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the JIT), a static variable or a strong / pinning GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="94715-160">Сборка, загруженная в собираемый `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-160">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="94715-161">Тип из такой сборки.</span><span class="sxs-lookup"><span data-stu-id="94715-161">A type from such an assembly.</span></span>
  - <span data-ttu-id="94715-162">Экземпляр типа из такой сборки.</span><span class="sxs-lookup"><span data-stu-id="94715-162">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="94715-163">Потоки, выполняющие код из сборки, загруженной в собираемый `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-163">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="94715-164">Экземпляры пользовательских несобираемых типов `AssemblyLoadContext`, созданных в собираемом `AssemblyLoadContext`</span><span class="sxs-lookup"><span data-stu-id="94715-164">Instances of custom non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`</span></span>
- <span data-ttu-id="94715-165">Ожидающие обработки экземпляры <xref:System.Threading.RegisteredWaitHandle> с обратными вызовами, настроенными на методы в пользовательском `AssemblyLoadContext`</span><span class="sxs-lookup"><span data-stu-id="94715-165">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`</span></span>

<span data-ttu-id="94715-166">Указания для поиска слота стека или регистра процессора, где содержится корень объекта:</span><span class="sxs-lookup"><span data-stu-id="94715-166">Hints to find stack slot / processor register rooting an object:</span></span>

- <span data-ttu-id="94715-167">Передача результатов вызова функции непосредственно в другую функцию может создать корень даже при отсутствии созданной пользователем локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="94715-167">Passing function call results directly to another function may create a root even though there is no user-created local variable.</span></span>
- <span data-ttu-id="94715-168">Если ссылка на объект была доступна в любой точке метода, JIT мог решить, что ссылка будет храниться в слоте стека или регистре процессора в течение нужного ему периода в текущей функции.</span><span class="sxs-lookup"><span data-stu-id="94715-168">If a reference to an object was available at any point in a method, the JIT might have decided to keep the reference in a stack slot / processor register for as long as it wants in the current function.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="94715-169">Отладка проблем с выгрузкой</span><span class="sxs-lookup"><span data-stu-id="94715-169">Debug unloading issues</span></span>

<span data-ttu-id="94715-170">Отладка проблем с выгрузкой может быть утомительной.</span><span class="sxs-lookup"><span data-stu-id="94715-170">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="94715-171">Иногда вы не знаете, что поддерживает активность `AssemblyLoadContext`, но выгрузка завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="94715-171">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span>
<span data-ttu-id="94715-172">Лучшим решением станет WinDbg (LLDB в UNIX) с подключаемым модулем SOS.</span><span class="sxs-lookup"><span data-stu-id="94715-172">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="94715-173">Необходимо найти сведения о том, что поддерживает активность `LoaderAllocator`, принадлежащего конкретному `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-173">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span>
<span data-ttu-id="94715-174">Этот подключаемый модуль позволяет просматривать объекты кучи сборки мусора, их иерархии и корни.</span><span class="sxs-lookup"><span data-stu-id="94715-174">This plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>
<span data-ttu-id="94715-175">Чтобы загрузить подключаемый модуль в отладчик, введите следующую команду в командной строке отладчика:</span><span class="sxs-lookup"><span data-stu-id="94715-175">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="94715-176">В WinDbg (кажется, что WinDbg делает это автоматически при прерывании приложения .NET Core):</span><span class="sxs-lookup"><span data-stu-id="94715-176">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="94715-177">В LLDB:</span><span class="sxs-lookup"><span data-stu-id="94715-177">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="94715-178">Попробуем выполнить отладку примера программы, в которой возникли проблемы с выгрузкой.</span><span class="sxs-lookup"><span data-stu-id="94715-178">Let's try to debug an example program that has problems with unloading.</span></span> <span data-ttu-id="94715-179">Исходный код приводится ниже.</span><span class="sxs-lookup"><span data-stu-id="94715-179">Source code is included below.</span></span> <span data-ttu-id="94715-180">При запуске с помощью WinDbg программа переключается в отладчике сразу после попытки проверить успешность выгрузки.</span><span class="sxs-lookup"><span data-stu-id="94715-180">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="94715-181">После этого вы можете начать поиск причины проблемы.</span><span class="sxs-lookup"><span data-stu-id="94715-181">You can then start looking for the culprits.</span></span>

<span data-ttu-id="94715-182">Обратите внимание, что при отладке с помощью LLDB в Unix команды SOS в следующих примерах не содержат перед собой `!`.</span><span class="sxs-lookup"><span data-stu-id="94715-182">Note that if you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="94715-183">Эта команда выполняет дамп всех объектов с именем типа, содержащим `LoaderAllocator` в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="94715-183">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="94715-184">Пример:</span><span class="sxs-lookup"><span data-stu-id="94715-184">Here is an example:</span></span>

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

<span data-ttu-id="94715-185">В разделе "Statistics:" ниже проверьте `MT` (`MethodTable`), который принадлежит `System.Reflection.LoaderAllocator`, и именно этот объект нас интересует.</span><span class="sxs-lookup"><span data-stu-id="94715-185">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="94715-186">Затем в списке в начале найдите запись с `MT`, соответствующим этому объекту, и получите адрес самого объекта.</span><span class="sxs-lookup"><span data-stu-id="94715-186">Then in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="94715-187">В нашем случае это "000002b78000ce40"</span><span class="sxs-lookup"><span data-stu-id="94715-187">In our case, it is "000002b78000ce40"</span></span>

<span data-ttu-id="94715-188">Теперь, когда мы знаем адрес объекта `LoaderAllocator`, можно использовать другую команду для поиска его корней в сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="94715-188">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots</span></span>

```console
!gcroot -all 0x000002b78000ce40 
```

<span data-ttu-id="94715-189">Эта команда выполняет дампы цепочки ссылок на объекты, ведущих к экземпляру `LoaderAllocator`.</span><span class="sxs-lookup"><span data-stu-id="94715-189">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="94715-190">Список начинается с корня, который поддерживает активность `LoaderAllocator`, и, таким образом, является причиной проблемы, которую вы отлаживаете.</span><span class="sxs-lookup"><span data-stu-id="94715-190">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem you're debugging.</span></span> <span data-ttu-id="94715-191">Корнем может быть слот стека, регистр процессора, обработчик сборки мусора или статическая переменная.</span><span class="sxs-lookup"><span data-stu-id="94715-191">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="94715-192">Вот пример результата выходных данных команды `gcroot`:</span><span class="sxs-lookup"><span data-stu-id="94715-192">Here is an example of the output of the `gcroot` command:</span></span>

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

<span data-ttu-id="94715-193">Теперь необходимо выяснить, где расположен корень, чтобы его можно было исправить.</span><span class="sxs-lookup"><span data-stu-id="94715-193">Now you need to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="94715-194">Самый простой случай: корень — это слот стека или регистр процессора.</span><span class="sxs-lookup"><span data-stu-id="94715-194">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="94715-195">В этом случае в `gcroot` отображается имя функции, фрейм которой содержит корень, и поток, в котором выполняется эта функция.</span><span class="sxs-lookup"><span data-stu-id="94715-195">In that case, the `gcroot` shows you the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="94715-196">Сложный случай: корень является статической переменной или обработчиком сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="94715-196">The difficult case is when the root is a static variable or a GC handle.</span></span> 

<span data-ttu-id="94715-197">В предыдущем примере первый корень является локальной переменной типа `System.Reflection.RuntimeMethodInfo`, хранимого во фрейме функции `example.Program.Main(System.String[])` по адресу `rbp-20` (`rbp` — это регистр процессора `rbp`, а –20 — шестнадцатеричное смещение от этого регистра).</span><span class="sxs-lookup"><span data-stu-id="94715-197">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="94715-198">Второй корень является нормальным (строгим) `GCHandle`, который содержит ссылку на экземпляр класса `test.Test`.</span><span class="sxs-lookup"><span data-stu-id="94715-198">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span> 

<span data-ttu-id="94715-199">Третий корень является закрепленным `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="94715-199">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="94715-200">Это фактически статическая переменная.</span><span class="sxs-lookup"><span data-stu-id="94715-200">This one is actually a static variable.</span></span> <span data-ttu-id="94715-201">К сожалению, не существует способа это определить.</span><span class="sxs-lookup"><span data-stu-id="94715-201">Unfortunately, there is no way to tell.</span></span> <span data-ttu-id="94715-202">Статические переменные для ссылочных типов хранятся в управляемом массиве объектов во внутренних структурах среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="94715-202">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="94715-203">Другой вариант, который может помешать выгрузке `AssemblyLoadContext`, — когда поток содержит фрейм метода из сборки, загруженной в стек `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-203">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="94715-204">Это можно проверить, выполнив дамп управляемых стеков вызовов всех потоков:</span><span class="sxs-lookup"><span data-stu-id="94715-204">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="94715-205">Команда означает "Применить ко всем потокам команду `!clrstack`".</span><span class="sxs-lookup"><span data-stu-id="94715-205">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="94715-206">Ниже приведен результат выполнения команды для примера.</span><span class="sxs-lookup"><span data-stu-id="94715-206">The following is the output of that command for the example.</span></span> <span data-ttu-id="94715-207">К сожалению, в LLDB в UNIX нет способа применить команду ко всем потокам, поэтому необходимо будет вручную переключать потоки и повторять команду `clrstack`.</span><span class="sxs-lookup"><span data-stu-id="94715-207">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you'll need to resort to manually switching threads and repeating the `clrstack` command.</span></span>
<span data-ttu-id="94715-208">Игнорируйте все потоки, в которых отладчик сообщает: "Не удалось пройти по управляемому стеку".</span><span class="sxs-lookup"><span data-stu-id="94715-208">Ignore all threads where the debugger says "Unable to walk the managed stack."</span></span>

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

<span data-ttu-id="94715-209">Как видите, последний поток имеет `test.Program.ThreadProc()`.</span><span class="sxs-lookup"><span data-stu-id="94715-209">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="94715-210">Это функция из сборки, загруженной в `AssemblyLoadContext`, и поэтому она сохраняет активность `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="94715-210">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="94715-211">Пример источника с проблемами выгрузки</span><span class="sxs-lookup"><span data-stu-id="94715-211">Example source with unloadability issues</span></span>

<span data-ttu-id="94715-212">В предыдущем примере отладки используется следующий код.</span><span class="sxs-lookup"><span data-stu-id="94715-212">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="94715-213">Основная программа тестирования</span><span class="sxs-lookup"><span data-stu-id="94715-213">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="94715-214">Программа, загруженная в TestAssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="94715-214">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="94715-215">Следующий код представляет `test.dll`, переданный в метод `ExecuteAndUnload` в основной программе тестирования.</span><span class="sxs-lookup"><span data-stu-id="94715-215">The following code represents the `test.dll` passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
