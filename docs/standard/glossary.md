---
title: Глоссарий по .NET
description: Узнайте значение выбранных терминов, используемых в документации по .NET.
ms.date: 01/22/2019
ms.technology: dotnet-standard
ms.openlocfilehash: ed4dceed1a3f39c5c4ce7a278efc37bb38ed0d94
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344202"
---
# <a name="net-glossary"></a><span data-ttu-id="1c357-103">Глоссарий по .NET</span><span class="sxs-lookup"><span data-stu-id="1c357-103">.NET Glossary</span></span>

<span data-ttu-id="1c357-104">Основная цель этого глоссария — объяснить значения выбранных терминов и сокращений, которые часто встречаются в документации по .NET без определений.</span><span class="sxs-lookup"><span data-stu-id="1c357-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="1c357-105">AOT</span><span class="sxs-lookup"><span data-stu-id="1c357-105">AOT</span></span>

<span data-ttu-id="1c357-106">Компилятор AOT.</span><span class="sxs-lookup"><span data-stu-id="1c357-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="1c357-107">Аналогично [JIT](#jit), этот компилятор также преобразует [IL](#il) в машинный код.</span><span class="sxs-lookup"><span data-stu-id="1c357-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="1c357-108">В отличие от JIT-компиляции AOT-компиляция происходит до выполнения приложения и обычно осуществляется на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c357-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="1c357-109">Так как цепочки средств AOT не компилируются во время выполнения, они не сокращают время, затраченное на компиляцию.</span><span class="sxs-lookup"><span data-stu-id="1c357-109">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="1c357-110">Это означает, что они могут тратить больше времени на оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="1c357-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="1c357-111">Так как контекстом AOT является все приложение, AOT-компилятор также выполняет межмодульное связывание и анализ всей программы. Это означает, что соблюдаются все ссылки и создается один исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="1c357-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

<span data-ttu-id="1c357-112">См. разделы [CoreRT](#corert) и [.NET Native](#net-native).</span><span class="sxs-lookup"><span data-stu-id="1c357-112">See [CoreRT](#corert) and [.NET Native](#net-native).</span></span>

## <a name="aspnet"></a><span data-ttu-id="1c357-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1c357-113">ASP.NET</span></span>

<span data-ttu-id="1c357-114">Исходная реализация ASP.NET, которая поставляется вместе с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c357-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="1c357-115">Иногда ASP.NET является общим термином, который относится к обеим реализациям ASP.NET, включая ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="1c357-116">Значение термина в заданном экземпляре определяется контекстом.</span><span class="sxs-lookup"><span data-stu-id="1c357-116">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="1c357-117">Обратитесь к ASP.NET 4.x в тех ситуациях, когда важно избежать путаницы, поскольку термин ASP.NET может относиться к обеим реализациям.</span><span class="sxs-lookup"><span data-stu-id="1c357-117">Refer to ASP.NET 4.x when you want to make it clear that you're not using ASP.NET to mean both implementations.</span></span>

<span data-ttu-id="1c357-118">См. [документацию по ASP.NET](/aspnet/#pivot=aspnet).</span><span class="sxs-lookup"><span data-stu-id="1c357-118">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="1c357-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1c357-119">ASP.NET Core</span></span>

<span data-ttu-id="1c357-120">Кроссплатформенная, высокопроизводительная, основанная на открытом исходном коде реализация ASP.NET, построенная на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-120">A cross-platform, high-performance, open-source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="1c357-121">См. [документацию по ASP.NET Core](/aspnet/#pivot=core).</span><span class="sxs-lookup"><span data-stu-id="1c357-121">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="1c357-122">сборка</span><span class="sxs-lookup"><span data-stu-id="1c357-122">assembly</span></span>

<span data-ttu-id="1c357-123">Файл *DLL*/*EXE*, который содержит коллекцию API-интерфейсов, вызываемых приложениями или другими сборками.</span><span class="sxs-lookup"><span data-stu-id="1c357-123">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by applications or other assemblies.</span></span>

<span data-ttu-id="1c357-124">Сборка может включать разные типы, например интерфейсы, классы, структуры, перечисления и делегаты.</span><span class="sxs-lookup"><span data-stu-id="1c357-124">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="1c357-125">Сборки в папке *bin* проекта иногда называют *двоичными файлами*.</span><span class="sxs-lookup"><span data-stu-id="1c357-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="1c357-126">См. также [библиотека](#library).</span><span class="sxs-lookup"><span data-stu-id="1c357-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="1c357-127">CLR</span><span class="sxs-lookup"><span data-stu-id="1c357-127">CLR</span></span>

<span data-ttu-id="1c357-128">Общеязыковая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="1c357-128">Common Language Runtime.</span></span>

<span data-ttu-id="1c357-129">Точное значение зависит от контекста, но поддержка общеязыковой среды выполнения (CLR) относится к среде выполнения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c357-129">The exact meaning depends on the context, but Common Language Runtime usually refers to the runtime of .NET Framework.</span></span> <span data-ttu-id="1c357-130">Среда CLR обрабатывает выделение памяти и управление ей.</span><span class="sxs-lookup"><span data-stu-id="1c357-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="1c357-131">Среда CLR также является виртуальной машиной, которая не только выполняет приложения, но и создает, а также компилирует код с помощью [JIT](#jit)-компилятора.</span><span class="sxs-lookup"><span data-stu-id="1c357-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a [JIT](#jit) compiler.</span></span> <span data-ttu-id="1c357-132">Текущая реализация среды CLR доступна только для Windows.</span><span class="sxs-lookup"><span data-stu-id="1c357-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="1c357-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="1c357-133">CoreCLR</span></span>

<span data-ttu-id="1c357-134">Среда CLR .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="1c357-135">Эта среда CLR создана на той же базе кода, что и среда CLR.</span><span class="sxs-lookup"><span data-stu-id="1c357-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="1c357-136">Первоначально CoreCLR являлась средой выполнения Silverlight и должна была выполняться на нескольких платформах, в частности Windows и OS X. Теперь CoreCLR является частью .NET Core и представляет упрощенную версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1c357-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="1c357-137">Она по-прежнему работает как [кроссплатформенная](#cross-platform) и обеспечивает поддержку многих дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="1c357-137">It's still a [cross-platform](#cross-platform) runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="1c357-138">CoreCLR также представляет собой виртуальную машину с возможностями выполнения JIT и кода.</span><span class="sxs-lookup"><span data-stu-id="1c357-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="1c357-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="1c357-139">CoreFX</span></span>

<span data-ttu-id="1c357-140">Библиотека базовых классов .NET Core (BCL)</span><span class="sxs-lookup"><span data-stu-id="1c357-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="1c357-141">Набор библиотек, которые составляют пространства имен System.\* (и в некоторой степени Microsoft.\*).</span><span class="sxs-lookup"><span data-stu-id="1c357-141">A set of libraries that comprise the System.\* (and to a limited extent Microsoft.\*) namespaces.</span></span> <span data-ttu-id="1c357-142">BCL — это универсальная платформа низкого уровня, которая является основой платформ приложений более высокого уровня, например ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="1c357-143">Исходный код BCL .NET Core содержится в [репозитории .NET Core](https://github.com/dotnet/runtime).</span><span class="sxs-lookup"><span data-stu-id="1c357-143">The source code of the .NET Core BCL is contained in the [.NET Core runtime repository](https://github.com/dotnet/runtime).</span></span> <span data-ttu-id="1c357-144">Но большая часть API-интерфейсов .NET Core также доступна в .NET Framework, поэтому CoreFX можно представить как ветвь BCL .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c357-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="1c357-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="1c357-145">CoreRT</span></span>

<span data-ttu-id="1c357-146">Среда выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-146">.NET Core runtime.</span></span>

<span data-ttu-id="1c357-147">В отличие от среды CLR или CoreCLR, CoreRT не является виртуальной машиной, поэтому она не включает средства для создания и выполнения кода "на лету", так как в ней отсутствует [JIT](#jit).</span><span class="sxs-lookup"><span data-stu-id="1c357-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="1c357-148">Но она поддерживает [сборку мусора](#gc) и возможности идентификации типа среды выполнения (RTTI) и отражения.</span><span class="sxs-lookup"><span data-stu-id="1c357-148">It does, however, include the [GC](#gc) and the ability for run-time type identification (RTTI) and reflection.</span></span> <span data-ttu-id="1c357-149">Ее система типов разработана таким образом, что метаданные для отражения не требуется.</span><span class="sxs-lookup"><span data-stu-id="1c357-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="1c357-150">Отсутствие необходимости в метаданных обеспечивает наличие цепочки инструментов [AOT](#aot), которая может связать лишние метаданные и (что более важно) определить код, который приложение не использует.</span><span class="sxs-lookup"><span data-stu-id="1c357-150">Not requiring metadata enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="1c357-151">CoreRT находится в разработке.</span><span class="sxs-lookup"><span data-stu-id="1c357-151">CoreRT is in development.</span></span>

<span data-ttu-id="1c357-152">См. сведения о [.NET Native и CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span></span>

## <a name="cross-platform"></a><span data-ttu-id="1c357-153">кроссплатформенный</span><span class="sxs-lookup"><span data-stu-id="1c357-153">cross-platform</span></span>

<span data-ttu-id="1c357-154">Возможность разрабатывать и выполнять приложение, которое можно использовать в разных операционных системах, например в Linux, Windows и iOS, без необходимости переписывать его специально для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="1c357-154">The ability to develop and execute an application that can be used on multiple different operating systems, such as Linux, Windows, and iOS, without having to rewrite specifically for each one.</span></span> <span data-ttu-id="1c357-155">Это позволяет повторно использовать код и обеспечивает согласованность приложений на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="1c357-155">This enables code reuse and consistency between applications on different platforms.</span></span>

## <a name="ecosystem"></a><span data-ttu-id="1c357-156">экосистема</span><span class="sxs-lookup"><span data-stu-id="1c357-156">ecosystem</span></span>

<span data-ttu-id="1c357-157">Все программное обеспечение среды выполнения, средства разработки и ресурсы сообщества, которые используются для построения и запуска приложений для заданной технологии.</span><span class="sxs-lookup"><span data-stu-id="1c357-157">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="1c357-158">Термин "экосистема .NET" отличается от аналогичных терминов, таких как "стек .NET", тем, что включает сторонние приложения и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="1c357-158">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="1c357-159">Ниже приведен пример термина в предложении.</span><span class="sxs-lookup"><span data-stu-id="1c357-159">Here's an example in a sentence:</span></span>

- <span data-ttu-id="1c357-160">"[.NET Standard](#net-standard) создана для того, чтобы повысить согласованность экосистемы .NET".</span><span class="sxs-lookup"><span data-stu-id="1c357-160">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span>

## <a name="framework"></a><span data-ttu-id="1c357-161">платформа</span><span class="sxs-lookup"><span data-stu-id="1c357-161">framework</span></span>

<span data-ttu-id="1c357-162">Обычно это всеобъемлющая коллекция API-интерфейсов, которая упрощает разработку и развертывание приложений, основанных на определенной технологии.</span><span class="sxs-lookup"><span data-stu-id="1c357-162">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="1c357-163">В этом общем смысле ASP.NET Core и Windows Forms являются примерами платформ приложений.</span><span class="sxs-lookup"><span data-stu-id="1c357-163">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="1c357-164">См. также [библиотека](#library).</span><span class="sxs-lookup"><span data-stu-id="1c357-164">See also [library](#library).</span></span>

<span data-ttu-id="1c357-165">Слово "платформа" имеет более специфичное техническое значение в следующих терминах.</span><span class="sxs-lookup"><span data-stu-id="1c357-165">The word "framework" has a more specific technical meaning in the following terms:</span></span>

- [<span data-ttu-id="1c357-166">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c357-166">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="1c357-167">целевая платформа</span><span class="sxs-lookup"><span data-stu-id="1c357-167">target framework</span></span>](#target-framework)
- [<span data-ttu-id="1c357-168">TFM (моникер целевой платформы)</span><span class="sxs-lookup"><span data-stu-id="1c357-168">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="1c357-169">В существующей документации "платформа" иногда означает [реализацию .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="1c357-169">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="1c357-170">Например, в статье .NET Core может упоминаться как платформа.</span><span class="sxs-lookup"><span data-stu-id="1c357-170">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="1c357-171">Мы планируем избавиться от путаницы в документации.</span><span class="sxs-lookup"><span data-stu-id="1c357-171">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="1c357-172">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="1c357-172">GC</span></span>

<span data-ttu-id="1c357-173">Сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="1c357-173">Garbage collector.</span></span>

<span data-ttu-id="1c357-174">Сборщик мусора является реализацией автоматического управления памятью.</span><span class="sxs-lookup"><span data-stu-id="1c357-174">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="1c357-175">Сборщик мусора освобождает память, занятую объектами, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="1c357-175">The GC frees memory occupied by objects that are no longer in use.</span></span>

<span data-ttu-id="1c357-176">См. [Сборка мусора](garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-176">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="1c357-177">IL</span><span class="sxs-lookup"><span data-stu-id="1c357-177">IL</span></span>

<span data-ttu-id="1c357-178">Промежуточный язык.</span><span class="sxs-lookup"><span data-stu-id="1c357-178">Intermediate language.</span></span>

<span data-ttu-id="1c357-179">Языки .NET более высокого уровня, например C#, компилируются до независимого от оборудования набора инструкций, который называется промежуточным языком (IL).</span><span class="sxs-lookup"><span data-stu-id="1c357-179">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="1c357-180">IL иногда называют MSIL (Microsoft IL) или CIL (общим IL).</span><span class="sxs-lookup"><span data-stu-id="1c357-180">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="1c357-181">JIT</span><span class="sxs-lookup"><span data-stu-id="1c357-181">JIT</span></span>

<span data-ttu-id="1c357-182">JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="1c357-182">Just-in-time compiler.</span></span>

<span data-ttu-id="1c357-183">Аналогично [AOT](#aot), этот компилятор преобразует [IL](#il) в машинный код, который понимает обработчик.</span><span class="sxs-lookup"><span data-stu-id="1c357-183">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="1c357-184">В отличие от AOT, JIT-компиляция происходит по требованию и осуществляется на том же компьютере, где должен выполняться код.</span><span class="sxs-lookup"><span data-stu-id="1c357-184">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="1c357-185">Так как JIT-компиляция происходит во время выполнения приложения, время компиляции является частью времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="1c357-185">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="1c357-186">Таким образом, JIT-компиляторы должны поддерживать баланс между временем оптимизации кода и экономии, к которой может привести к результирующий код.</span><span class="sxs-lookup"><span data-stu-id="1c357-186">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="1c357-187">Но JIT знает фактическое оборудование и может освободить разработчиков от поставки различных реализаций.</span><span class="sxs-lookup"><span data-stu-id="1c357-187">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="1c357-188">реализация .NET</span><span class="sxs-lookup"><span data-stu-id="1c357-188">implementation of .NET</span></span>

<span data-ttu-id="1c357-189">Реализация .NET включает в себя:</span><span class="sxs-lookup"><span data-stu-id="1c357-189">An implementation of .NET includes:</span></span>

- <span data-ttu-id="1c357-190">Одна среда выполнения или несколько.</span><span class="sxs-lookup"><span data-stu-id="1c357-190">One or more runtimes.</span></span> <span data-ttu-id="1c357-191">Примеры CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="1c357-191">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="1c357-192">Библиотека классов, которая реализует версию .NET Standard, а также может содержать дополнительные API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="1c357-192">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="1c357-193">Примеры: библиотека базовых классов .NET Framework, библиотека базовых классов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-193">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="1c357-194">(Необязательно) Одна платформа приложений или несколько.</span><span class="sxs-lookup"><span data-stu-id="1c357-194">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="1c357-195">Примеры ASP.NET, Windows Forms и WPF входят в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c357-195">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="1c357-196">(Необязательно) Средства разработки.</span><span class="sxs-lookup"><span data-stu-id="1c357-196">Optionally, development tools.</span></span> <span data-ttu-id="1c357-197">Некоторые средства разработки, являются общими для нескольких реализаций.</span><span class="sxs-lookup"><span data-stu-id="1c357-197">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="1c357-198">Примеры реализаций .NET:</span><span class="sxs-lookup"><span data-stu-id="1c357-198">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="1c357-199">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c357-199">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="1c357-200">.NET Core</span><span class="sxs-lookup"><span data-stu-id="1c357-200">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="1c357-201">Универсальная платформа Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="1c357-201">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="1c357-202">библиотека</span><span class="sxs-lookup"><span data-stu-id="1c357-202">library</span></span>

<span data-ttu-id="1c357-203">Коллекция интерфейсов API, которые могут быть вызваны приложениями или другими библиотеками.</span><span class="sxs-lookup"><span data-stu-id="1c357-203">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="1c357-204">Библиотека .NET состоит из одной или нескольких [сборок](#assembly).</span><span class="sxs-lookup"><span data-stu-id="1c357-204">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="1c357-205">Слова "библиотека" и [платформа](#framework) часто используются как синонимы.</span><span class="sxs-lookup"><span data-stu-id="1c357-205">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="1c357-206">метапакет</span><span class="sxs-lookup"><span data-stu-id="1c357-206">metapackage</span></span>

<span data-ttu-id="1c357-207">Пакет NuGet, не имеющий собственной библиотеки, но имеющий только список зависимостей.</span><span class="sxs-lookup"><span data-stu-id="1c357-207">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="1c357-208">Включенные пакеты при необходимости могут сформировать API для целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="1c357-208">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="1c357-209">См. статью [Пакеты, метапакеты и платформы](../core/packages.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-209">See [Packages, Metapackages, and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="1c357-210">Mono</span><span class="sxs-lookup"><span data-stu-id="1c357-210">Mono</span></span>

<span data-ttu-id="1c357-211">Mono является [кроссплатформенной](#cross-platform) реализацией .NET с открытым кодом, которая в основном используется, если требуется небольшая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="1c357-211">Mono is an open source, [cross-platform](#cross-platform) .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="1c357-212">Это среда выполнения, которая может работать в приложениях Xamarin на Android, Mac, iOS, tvOS и watchOS. Она предназначена преимущественно для приложений, предусматривающих компактную разработку.</span><span class="sxs-lookup"><span data-stu-id="1c357-212">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS, and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="1c357-213">Она поддерживает все текущие опубликованные версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="1c357-213">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="1c357-214">Исторически Mono реализовывала крупный API .NET Framework и эмулировала некоторые из наиболее популярных возможностей в Unix.</span><span class="sxs-lookup"><span data-stu-id="1c357-214">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="1c357-215">Иногда она использовалась для запуска приложений .NET, которые применяют эти возможности в Unix.</span><span class="sxs-lookup"><span data-stu-id="1c357-215">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="1c357-216">Mono обычно используется с JIT-компилятором, но также располагает полным статическим компилятором (заблаговременная компиляция), который используется на таких платформах, как iOS.</span><span class="sxs-lookup"><span data-stu-id="1c357-216">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="1c357-217">Дополнительные сведения о Mono см. в [соответствующей документации](https://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="1c357-217">To learn more about Mono, see the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="1c357-218">.NET</span><span class="sxs-lookup"><span data-stu-id="1c357-218">.NET</span></span>

<span data-ttu-id="1c357-219">Общий термин для [.NET Standard](#net-standard) и всех [реализаций .NET](#implementation-of-net) и рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="1c357-219">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="1c357-220">Всегда пишется полностью прописными буквами. Написание ".Net" не используется.</span><span class="sxs-lookup"><span data-stu-id="1c357-220">Always fully capitalized, never ".Net".</span></span>

<span data-ttu-id="1c357-221">См. [руководство по .NET](index.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-221">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="1c357-222">.NET Core</span><span class="sxs-lookup"><span data-stu-id="1c357-222">.NET Core</span></span>

<span data-ttu-id="1c357-223">Кроссплатформенная, высокопроизводительная, основанная на открытом исходном коде реализация .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-223">A cross-platform, high-performance, open-source implementation of .NET.</span></span> <span data-ttu-id="1c357-224">Включает в себя среду выполнения CoreCLR, среду выполнения AOT Core (CoreRT в разработке), библиотеку базовых классов Core и пакет SDK для Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-224">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="1c357-225">См. [.NET Core](../core/index.yml).</span><span class="sxs-lookup"><span data-stu-id="1c357-225">See [.NET Core](../core/index.yml).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="1c357-226">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c357-226">.NET Core CLI</span></span>

<span data-ttu-id="1c357-227">Кроссплатформенная цепочка инструментов для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-227">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="1c357-228">См. сведения о [.NET Core CLI](../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-228">See [.NET Core CLI](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="1c357-229">Пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c357-229">.NET Core SDK</span></span>

<span data-ttu-id="1c357-230">Набор библиотек и средств, которые позволяют разработчикам создавать приложения и библиотеки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-230">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="1c357-231">Включает в себя [.NET Core CLI](#net-core-cli) для построения приложения, библиотеки и среды выполнения .NET Core для создания и запуска приложений и исполняемый файл dotnet (*dotnet.exe*), который выполняет команды CLI и запускает приложения.</span><span class="sxs-lookup"><span data-stu-id="1c357-231">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="1c357-232">См. [Обзор пакета SDK для .NET Core](../core/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-232">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="1c357-233">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c357-233">.NET Framework</span></span>

<span data-ttu-id="1c357-234">Реализация .NET, работающая только в Windows.</span><span class="sxs-lookup"><span data-stu-id="1c357-234">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="1c357-235">Включает в себя Common Language Runtime (CLR), библиотеку базовых классов и библиотеки платформы приложений, например ASP.NET, Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="1c357-235">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="1c357-236">См. [Руководство по .NET Framework](../framework/index.yml).</span><span class="sxs-lookup"><span data-stu-id="1c357-236">See [.NET Framework Guide](../framework/index.yml).</span></span>

## <a name="net-native"></a><span data-ttu-id="1c357-237">.NET Native</span><span class="sxs-lookup"><span data-stu-id="1c357-237">.NET Native</span></span>

<span data-ttu-id="1c357-238">Цепочка инструментов компилятора, которая создает машинный код в режиме AOT в отличие от режима JIT.</span><span class="sxs-lookup"><span data-stu-id="1c357-238">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="1c357-239">Компиляция происходит на компьютере разработчика, аналогично тому, как работает компилятор и компоновщик C++.</span><span class="sxs-lookup"><span data-stu-id="1c357-239">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="1c357-240">Она удаляет неиспользуемый код и тратит больше времени на его оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="1c357-240">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="1c357-241">Она извлекает код из библиотек и объединяет их в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="1c357-241">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="1c357-242">Результатом является один модуль, который представляет все приложение.</span><span class="sxs-lookup"><span data-stu-id="1c357-242">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="1c357-243">UWP была первой платформой приложений, поддерживаемой .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1c357-243">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="1c357-244">Теперь мы поддерживаем построение собственных консольных приложений для Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="1c357-244">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="1c357-245">См.[Введение в машинный код .NET и CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-245">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="1c357-246">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="1c357-246">.NET Standard</span></span>

<span data-ttu-id="1c357-247">Формальная спецификация API-интерфейсов .NET, которые доступны в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-247">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="1c357-248">Спецификацию .NET Standard иногда в документации называют библиотекой.</span><span class="sxs-lookup"><span data-stu-id="1c357-248">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="1c357-249">Так как библиотека содержит реализации API-интерфейсов, а не только спецификации (интерфейсы), неверно называть .NET Standard "библиотека".</span><span class="sxs-lookup"><span data-stu-id="1c357-249">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="1c357-250">Мы планируем исключить это использование из документации, за исключением применительно к имени метапакета .NET Standard (`NETStandard.Library`).</span><span class="sxs-lookup"><span data-stu-id="1c357-250">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="1c357-251">См. [.NET Standard](net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-251">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="1c357-252">NGEN</span><span class="sxs-lookup"><span data-stu-id="1c357-252">NGEN</span></span>

<span data-ttu-id="1c357-253">Создание образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="1c357-253">Native (image) generation.</span></span>

<span data-ttu-id="1c357-254">Эту технологию можно считать постоянным JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="1c357-254">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="1c357-255">Как правило, он компилирует код на компьютере, где код выполняется. Но компиляция обычно происходит во время установки.</span><span class="sxs-lookup"><span data-stu-id="1c357-255">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="1c357-256">пакет</span><span class="sxs-lookup"><span data-stu-id="1c357-256">package</span></span>

<span data-ttu-id="1c357-257">Пакет NuGet &mdash; или просто пакет &mdash; — это *ZIP*-файл с одной сборкой с одинаковым именем или несколькими, а также с дополнительными метаданными, такими как имя автора.</span><span class="sxs-lookup"><span data-stu-id="1c357-257">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="1c357-258">*ZIP*-файл имеет расширение *NUPKG* и может содержать ресурсы, такие как *DLL*-файлы и *XML*-файлы для нескольких целевых платформ и версий.</span><span class="sxs-lookup"><span data-stu-id="1c357-258">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="1c357-259">При установке в приложении или библиотеке выбор соответствующих ресурсов осуществляется в зависимости от целевой платформы, указанной приложением или библиотекой.</span><span class="sxs-lookup"><span data-stu-id="1c357-259">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="1c357-260">Ресурсы, которые определяют интерфейс, находятся в папке *ref*, а ресурсы, которые определяют реализацию, находятся в папке *lib*.</span><span class="sxs-lookup"><span data-stu-id="1c357-260">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="1c357-261">platform</span><span class="sxs-lookup"><span data-stu-id="1c357-261">platform</span></span>

<span data-ttu-id="1c357-262">Операционная система и оборудование, на котором она выполняется, например Windows, macOS, Linux, iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="1c357-262">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="1c357-263">Ниже приведены примеры использования в предложениях.</span><span class="sxs-lookup"><span data-stu-id="1c357-263">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="1c357-264">".NET Core — это кроссплатформенная реализация .NET".</span><span class="sxs-lookup"><span data-stu-id="1c357-264">".NET Core is a cross-platform implementation of .NET."</span></span>
- <span data-ttu-id="1c357-265">"Профили PCL относятся к платформам Майкрософт, а .NET Standard не зависит от платформы".</span><span class="sxs-lookup"><span data-stu-id="1c357-265">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="1c357-266">В документации по .NET часто используется термин "платформа .NET" для обозначения либо реализации .NET либо стека .NET, включая все реализации.</span><span class="sxs-lookup"><span data-stu-id="1c357-266">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="1c357-267">Оба этих варианта, как правило, приводят к путанице с основным значением (ОС или оборудование), поэтому мы планируем исключить их из документации.</span><span class="sxs-lookup"><span data-stu-id="1c357-267">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="1c357-268">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="1c357-268">runtime</span></span>

<span data-ttu-id="1c357-269">Среда выполнения для управляемой программы.</span><span class="sxs-lookup"><span data-stu-id="1c357-269">The execution environment for a managed program.</span></span>

<span data-ttu-id="1c357-270">Операционная система является частью среды выполнения, но не входит в среду выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-270">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="1c357-271">Ниже приведены несколько примеров сред выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-271">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="1c357-272">Среда CLR</span><span class="sxs-lookup"><span data-stu-id="1c357-272">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="1c357-273">Общеязыковая среда выполнения Core (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="1c357-273">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="1c357-274">.NET Native (для UWP)</span><span class="sxs-lookup"><span data-stu-id="1c357-274">.NET Native (for UWP)</span></span>
- <span data-ttu-id="1c357-275">Среда выполнения Mono</span><span class="sxs-lookup"><span data-stu-id="1c357-275">Mono runtime</span></span>

<span data-ttu-id="1c357-276">Иногда в документации по .NET термин "среда выполнения" используется для обозначения реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-276">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="1c357-277">Например, в следующих предложениях термин содержит "среда выполнения" следует заменить на "реализация".</span><span class="sxs-lookup"><span data-stu-id="1c357-277">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="1c357-278">"Различные среды выполнения .NET реализуют конкретные версии .NET Standard".</span><span class="sxs-lookup"><span data-stu-id="1c357-278">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="1c357-279">"Библиотеки, предназначенные для различных сред выполнения, должны быть нацелены на эту платформу".</span><span class="sxs-lookup"><span data-stu-id="1c357-279">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="1c357-280">(по отношению к .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="1c357-280">(referring to .NET Standard)</span></span>
- <span data-ttu-id="1c357-281">"Различные среды выполнения .NET реализуют конкретные версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="1c357-281">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="1c357-282">…</span><span class="sxs-lookup"><span data-stu-id="1c357-282">…</span></span> <span data-ttu-id="1c357-283">Каждая версия среды выполнения .NET объявляет наибольшую версию поддерживаемой .NET Standard."</span><span class="sxs-lookup"><span data-stu-id="1c357-283">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="1c357-284">Мы планируем исключить это несогласованное использование.</span><span class="sxs-lookup"><span data-stu-id="1c357-284">We plan to eliminate this inconsistent usage.</span></span>

## <a name="stack"></a><span data-ttu-id="1c357-285">стек</span><span class="sxs-lookup"><span data-stu-id="1c357-285">stack</span></span>

<span data-ttu-id="1c357-286">Набор программных технологий, которые используются совместно для сборки и запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="1c357-286">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="1c357-287">"Стек .NET" относится к .NET Standard и всем реализациям .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-287">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="1c357-288">"Стеком .NET" может называться одна реализация .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-288">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span>

## <a name="target-framework"></a><span data-ttu-id="1c357-289">целевая платформа</span><span class="sxs-lookup"><span data-stu-id="1c357-289">target framework</span></span>

<span data-ttu-id="1c357-290">Коллекция API-интерфейсов, которую использует приложение или библиотека .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-290">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="1c357-291">Приложение или библиотека могут быть предназначены для версии .NET Standard (например, .NET Standard 2.0), которая представляет собой спецификацию для стандартного набора API-интерфейсов во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-291">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="1c357-292">Приложение или библиотека могут также работать в версии конкретной реализации .NET. В этом случае они получают доступ к API-интерфейсам конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="1c357-292">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="1c357-293">Например, приложение, предназначенное для Xamarin.iOS, получает доступ к предоставляемым Xamarin программам-оболочкам API iOS.</span><span class="sxs-lookup"><span data-stu-id="1c357-293">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="1c357-294">Для некоторых целевых платформ (например, .NET Framework) доступные API-интерфейсы определяются сборками, устанавливаемыми реализацией .NET в системе, в число которых могут входить API-интерфейсы платформ приложений (например, ASP.NET, WinForms).</span><span class="sxs-lookup"><span data-stu-id="1c357-294">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="1c357-295">Для целевых платформ на основе пакетов (например, .NET Standard и .NET Core) API-интерфейсы платформы определяются пакетами, установленными в приложении или библиотеке.</span><span class="sxs-lookup"><span data-stu-id="1c357-295">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="1c357-296">В этом случае целевая платформа неявно задает метапакет, который ссылается на все пакеты, составляющие платформу.</span><span class="sxs-lookup"><span data-stu-id="1c357-296">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="1c357-297">См. [Требуемые версии .NET Framework](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-297">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="1c357-298">TFM</span><span class="sxs-lookup"><span data-stu-id="1c357-298">TFM</span></span>

<span data-ttu-id="1c357-299">Моникер целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="1c357-299">Target framework moniker.</span></span>

<span data-ttu-id="1c357-300">Стандартизированный формат маркера для указания целевой платформы приложения или библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="1c357-300">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="1c357-301">Целевые платформы обычно называются короткими именами, например `net462`.</span><span class="sxs-lookup"><span data-stu-id="1c357-301">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="1c357-302">Существуют полноформатные TFM (например. NETFramework, версия = 4.6.2), но они обычно не используются для указания целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="1c357-302">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="1c357-303">См. [Требуемые версии .NET Framework](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1c357-303">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="1c357-304">UWP</span><span class="sxs-lookup"><span data-stu-id="1c357-304">UWP</span></span>

<span data-ttu-id="1c357-305">Универсальная платформа Windows.</span><span class="sxs-lookup"><span data-stu-id="1c357-305">Universal Windows Platform.</span></span>

<span data-ttu-id="1c357-306">Реализация .NET, которая используется для создания современных приложений Windows с поддержкой сенсорного ввода и программного обеспечения для Интернета вещей (IoT).</span><span class="sxs-lookup"><span data-stu-id="1c357-306">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="1c357-307">Она предназначена для объединения различных типов устройств, которые могут потребоваться, включая ПК, планшеты, телефоны и даже Xbox.</span><span class="sxs-lookup"><span data-stu-id="1c357-307">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phones, and even the Xbox.</span></span> <span data-ttu-id="1c357-308">UWP предоставляет много служб, таких как централизованный магазин приложений, среда выполнения (AppContainer) и набор API-интерфейсов Windows для использования вместо Win32 (WinRT).</span><span class="sxs-lookup"><span data-stu-id="1c357-308">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="1c357-309">Приложения могут быть написаны на C++, C#, Visual Basic и JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1c357-309">Apps can be written in C++, C#, Visual Basic, and JavaScript.</span></span> <span data-ttu-id="1c357-310">При использовании C# и Visual Basic API .NET предоставляются .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c357-310">When using C# and Visual Basic, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c357-311">См. также</span><span class="sxs-lookup"><span data-stu-id="1c357-311">See also</span></span>

- [<span data-ttu-id="1c357-312">Руководство по .NET</span><span class="sxs-lookup"><span data-stu-id="1c357-312">.NET Guide</span></span>](index.md)
- [<span data-ttu-id="1c357-313">Руководство по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c357-313">.NET Framework Guide</span></span>](../framework/index.yml)
- [<span data-ttu-id="1c357-314">.NET Core</span><span class="sxs-lookup"><span data-stu-id="1c357-314">.NET Core</span></span>](../core/index.yml)
- [<span data-ttu-id="1c357-315">Обзор ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1c357-315">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)
- [<span data-ttu-id="1c357-316">Обзор ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1c357-316">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)
