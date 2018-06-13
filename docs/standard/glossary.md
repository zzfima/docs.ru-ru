---
title: Глоссарий по .NET
description: Узнайте значение выбранных терминов, используемых в документации по .NET.
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.technology: dotnet-standard
ms.openlocfilehash: 195fbb799432b9d01a5faf301c9f8f2d1edfa1ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579409"
---
# <a name="net-glossary"></a><span data-ttu-id="2911c-103">Глоссарий по .NET</span><span class="sxs-lookup"><span data-stu-id="2911c-103">.NET Glossary</span></span>

<span data-ttu-id="2911c-104">Основная цель этого глоссария — объяснить значения выбранных терминов и сокращений, которые часто встречаются в документации по .NET без определений.</span><span class="sxs-lookup"><span data-stu-id="2911c-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="2911c-105">AOT</span><span class="sxs-lookup"><span data-stu-id="2911c-105">AOT</span></span>

<span data-ttu-id="2911c-106">Компилятор AOT.</span><span class="sxs-lookup"><span data-stu-id="2911c-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="2911c-107">Аналогично [JIT](#jit), этот компилятор также преобразует [IL](#il) в машинный код.</span><span class="sxs-lookup"><span data-stu-id="2911c-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="2911c-108">В отличие от JIT-компиляции AOT-компиляция происходит до выполнения приложения и обычно осуществляется на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="2911c-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="2911c-109">Так как цепочки средств AOT не компилируются во время выполнения, они не сокращают время, затраченное на компиляцию.</span><span class="sxs-lookup"><span data-stu-id="2911c-109">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="2911c-110">Это означает, что они могут тратить больше времени на оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="2911c-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="2911c-111">Так как контекстом AOT является все приложение, AOT-компилятор также выполняет межмодульное связывание и анализ всей программы. Это означает, что соблюдаются все ссылки и создается один исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="2911c-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="2911c-112">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2911c-112">ASP.NET</span></span> 

<span data-ttu-id="2911c-113">Исходная реализация ASP.NET, которая поставляется вместе с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2911c-113">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="2911c-114">Иногда ASP.NET является общим термином, который относится к обеим реализациям ASP.NET, включая ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-114">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="2911c-115">Значение термина в заданном экземпляре определяется контекстом.</span><span class="sxs-lookup"><span data-stu-id="2911c-115">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="2911c-116">Явно укажите ASP.NET 4.x в тех ситуациях, когда важно избежать путаницы, поскольку термин ASP.NET может относиться к обеим реализация.</span><span class="sxs-lookup"><span data-stu-id="2911c-116">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="2911c-117">См. [документацию по ASP.NET](/aspnet/#pivot=aspnet).</span><span class="sxs-lookup"><span data-stu-id="2911c-117">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="2911c-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2911c-118">ASP.NET Core</span></span>

<span data-ttu-id="2911c-119">Кроссплатформенная, высокопроизводительная, основанная на открытом исходном коде реализация ASP.NET, построенная на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-119">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="2911c-120">См. [документацию по ASP.NET Core](/aspnet/#pivot=core).</span><span class="sxs-lookup"><span data-stu-id="2911c-120">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="2911c-121">сборка</span><span class="sxs-lookup"><span data-stu-id="2911c-121">assembly</span></span>

<span data-ttu-id="2911c-122">Файл *DLL*/*EXE*, который содержит коллекцию API-интерфейсов, вызываемых приложениями или другими сборками.</span><span class="sxs-lookup"><span data-stu-id="2911c-122">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="2911c-123">Сборка может включать разные типы, например интерфейсы, классы, структуры, перечисления и делегаты.</span><span class="sxs-lookup"><span data-stu-id="2911c-123">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="2911c-124">Сборки в папке *bin* проекта иногда называют *двоичными файлами*.</span><span class="sxs-lookup"><span data-stu-id="2911c-124">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="2911c-125">См. также [библиотека](#library).</span><span class="sxs-lookup"><span data-stu-id="2911c-125">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="2911c-126">CLR</span><span class="sxs-lookup"><span data-stu-id="2911c-126">CLR</span></span>

<span data-ttu-id="2911c-127">Общеязыковая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="2911c-127">Common Language Runtime.</span></span>

<span data-ttu-id="2911c-128">Точное значение зависит от контекста, но обычно термин относится к среде выполнения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2911c-128">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="2911c-129">Среда CLR обрабатывает выделение памяти и управление ей.</span><span class="sxs-lookup"><span data-stu-id="2911c-129">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="2911c-130">Среда CLR также является виртуальной машиной, которая не только выполняет приложения, но также создает и компилирует код с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="2911c-130">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="2911c-131">Текущая реализация среды CLR доступна только для Windows.</span><span class="sxs-lookup"><span data-stu-id="2911c-131">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="2911c-132">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="2911c-132">CoreCLR</span></span>

<span data-ttu-id="2911c-133">Среда CLR .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-133">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="2911c-134">Эта среда CLR создана на той же базе кода, что и среда CLR.</span><span class="sxs-lookup"><span data-stu-id="2911c-134">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="2911c-135">Первоначально CoreCLR являлась средой выполнения Silverlight и должна была выполняться на нескольких платформах, в частности Windows и OS X. Теперь CoreCLR является частью .NET Core и представляет упрощенную версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2911c-135">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="2911c-136">Она по-прежнему работает как кроссплатформенная и обеспечивает поддержку многих дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="2911c-136">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="2911c-137">CoreCLR также представляет собой виртуальную машину с возможностями выполнения JIT и кода.</span><span class="sxs-lookup"><span data-stu-id="2911c-137">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="2911c-138">CoreFX</span><span class="sxs-lookup"><span data-stu-id="2911c-138">CoreFX</span></span>

<span data-ttu-id="2911c-139">Библиотека базовых классов .NET Core (BCL)</span><span class="sxs-lookup"><span data-stu-id="2911c-139">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="2911c-140">Набор библиотек, которые составляют пространства имен System.* (и в некоторой степени Microsoft*).</span><span class="sxs-lookup"><span data-stu-id="2911c-140">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="2911c-141">BCL — это универсальная платформа низкого уровня, которая является основой платформ приложений более высокого уровня, например ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-141">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="2911c-142">Исходный код BCL .NET Core содержится в [репозитории CoreFX](https://github.com/dotnet/corefx).</span><span class="sxs-lookup"><span data-stu-id="2911c-142">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="2911c-143">Но большая часть API-интерфейсов .NET Core также доступна в .NET Framework, поэтому CoreFX можно представить как ветвь BCL .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2911c-143">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="2911c-144">CoreRT</span><span class="sxs-lookup"><span data-stu-id="2911c-144">CoreRT</span></span>

<span data-ttu-id="2911c-145">Среда выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-145">.NET Core runtime.</span></span>

<span data-ttu-id="2911c-146">В отличие от среды CLR или CoreCLR, CoreRT не является виртуальной машиной, поэтому она не включает средства для создания и выполнения кода "на лету", так как в ней отсутствует [JIT](#jit).</span><span class="sxs-lookup"><span data-stu-id="2911c-146">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="2911c-147">Но она поддерживает [сборку мусора](#gc) и возможности идентификации типа среды выполнения (RTTI) и отражения.</span><span class="sxs-lookup"><span data-stu-id="2911c-147">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="2911c-148">Ее система типов разработана таким образом, что метаданные для отражения не требуется.</span><span class="sxs-lookup"><span data-stu-id="2911c-148">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="2911c-149">Это обеспечивает наличие цепочки инструментов [AOT](#aot), которая может связать лишние метаданные и (что более важно) определить код, который приложение не использует.</span><span class="sxs-lookup"><span data-stu-id="2911c-149">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="2911c-150">CoreRT находится в разработке.</span><span class="sxs-lookup"><span data-stu-id="2911c-150">CoreRT is in development.</span></span>

<span data-ttu-id="2911c-151">См.[Введение в машинный код .NET и CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-151">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="2911c-152">экосистема</span><span class="sxs-lookup"><span data-stu-id="2911c-152">ecosystem</span></span>

<span data-ttu-id="2911c-153">Все программное обеспечение среды выполнения, средства разработки и ресурсы сообщества, которые используются для построения и запуска приложений для заданной технологии.</span><span class="sxs-lookup"><span data-stu-id="2911c-153">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="2911c-154">Термин "экосистема .NET" отличается от аналогичных терминов, таких как "стек .NET", тем, что включает сторонние приложения и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="2911c-154">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="2911c-155">Ниже приведен пример термина в предложении.</span><span class="sxs-lookup"><span data-stu-id="2911c-155">Here's an example in a sentence:</span></span>

- <span data-ttu-id="2911c-156">"[.NET Standard](#net-standard) создана для того, чтобы повысить согласованность экосистемы .NET".</span><span class="sxs-lookup"><span data-stu-id="2911c-156">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="2911c-157">платформа</span><span class="sxs-lookup"><span data-stu-id="2911c-157">framework</span></span>

<span data-ttu-id="2911c-158">Обычно это всеобъемлющая коллекция API-интерфейсов, которая упрощает разработку и развертывание приложений, основанных на определенной технологии.</span><span class="sxs-lookup"><span data-stu-id="2911c-158">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="2911c-159">В этом общем смысле ASP.NET Core и Windows Forms являются примерами платформ приложений.</span><span class="sxs-lookup"><span data-stu-id="2911c-159">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="2911c-160">См. также [библиотека](#library).</span><span class="sxs-lookup"><span data-stu-id="2911c-160">See also [library](#library).</span></span>

<span data-ttu-id="2911c-161">Слово "платформа" имеет более специфичное техническое значение в следующих терминах.</span><span class="sxs-lookup"><span data-stu-id="2911c-161">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="2911c-162">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2911c-162">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="2911c-163">целевая платформа</span><span class="sxs-lookup"><span data-stu-id="2911c-163">target framework</span></span>](#target-framework)
* [<span data-ttu-id="2911c-164">TFM (моникер целевой платформы)</span><span class="sxs-lookup"><span data-stu-id="2911c-164">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="2911c-165">В существующей документации "платформа" иногда означает [реализацию .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="2911c-165">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="2911c-166">Например, в статье .NET Core может упоминаться как платформа.</span><span class="sxs-lookup"><span data-stu-id="2911c-166">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="2911c-167">Мы планируем избавиться от путаницы в документации.</span><span class="sxs-lookup"><span data-stu-id="2911c-167">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="2911c-168">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="2911c-168">GC</span></span>

<span data-ttu-id="2911c-169">Сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="2911c-169">Garbage collector.</span></span>

<span data-ttu-id="2911c-170">Сборщик мусора является реализацией автоматического управления памятью.</span><span class="sxs-lookup"><span data-stu-id="2911c-170">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="2911c-171">Сборщик мусора освобождает память, занятую объектами, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="2911c-171">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="2911c-172">См. [Сборка мусора](garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-172">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="2911c-173">IL</span><span class="sxs-lookup"><span data-stu-id="2911c-173">IL</span></span>

<span data-ttu-id="2911c-174">Промежуточный язык.</span><span class="sxs-lookup"><span data-stu-id="2911c-174">Intermediate language.</span></span>

<span data-ttu-id="2911c-175">Языки .NET более высокого уровня, например C#, компилируются до независимого от оборудования набора инструкций, который называется промежуточным языком (IL).</span><span class="sxs-lookup"><span data-stu-id="2911c-175">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="2911c-176">IL иногда называют MSIL (Microsoft IL) или CIL (общим IL).</span><span class="sxs-lookup"><span data-stu-id="2911c-176">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="2911c-177">JIT</span><span class="sxs-lookup"><span data-stu-id="2911c-177">JIT</span></span>

<span data-ttu-id="2911c-178">JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="2911c-178">Just-in-time compiler.</span></span>

<span data-ttu-id="2911c-179">Аналогично [AOT](#aot), этот компилятор преобразует [IL](#il) в машинный код, который понимает обработчик.</span><span class="sxs-lookup"><span data-stu-id="2911c-179">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="2911c-180">В отличие от AOT, JIT-компиляция происходит по требованию и осуществляется на том же компьютере, где должен выполняться код.</span><span class="sxs-lookup"><span data-stu-id="2911c-180">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="2911c-181">Так как JIT-компиляция происходит во время выполнения приложения, время компиляции является частью времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="2911c-181">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="2911c-182">Таким образом, JIT-компиляторы должны поддерживать баланс между временем оптимизации кода и экономии, к которой может привести к результирующий код.</span><span class="sxs-lookup"><span data-stu-id="2911c-182">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="2911c-183">Но JIT знает фактическое оборудование и может освободить разработчиков от поставки различных реализаций.</span><span class="sxs-lookup"><span data-stu-id="2911c-183">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="2911c-184">реализация .NET</span><span class="sxs-lookup"><span data-stu-id="2911c-184">implementation of .NET</span></span>

<span data-ttu-id="2911c-185">Реализация .NET включает в себя следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="2911c-185">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="2911c-186">Одна среда выполнения или несколько.</span><span class="sxs-lookup"><span data-stu-id="2911c-186">One or more runtimes.</span></span> <span data-ttu-id="2911c-187">Примеры: CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="2911c-187">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="2911c-188">Библиотека классов, которая реализует версию .NET Standard, а также может содержать дополнительные API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="2911c-188">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="2911c-189">Примеры: библиотека базовых классов .NET Framework, библиотека базовых классов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-189">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="2911c-190">(Необязательно) Одна платформа приложений или несколько.</span><span class="sxs-lookup"><span data-stu-id="2911c-190">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="2911c-191">Примеры: ASP.NET, Windows Forms и WPF входят в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2911c-191">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="2911c-192">(Необязательно) Средства разработки.</span><span class="sxs-lookup"><span data-stu-id="2911c-192">Optionally, development tools.</span></span> <span data-ttu-id="2911c-193">Некоторые средства разработки, являются общими для нескольких реализаций.</span><span class="sxs-lookup"><span data-stu-id="2911c-193">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="2911c-194">Примеры реализаций .NET:</span><span class="sxs-lookup"><span data-stu-id="2911c-194">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="2911c-195">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2911c-195">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="2911c-196">.NET Core</span><span class="sxs-lookup"><span data-stu-id="2911c-196">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="2911c-197">Универсальная платформа Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="2911c-197">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="2911c-198">библиотека</span><span class="sxs-lookup"><span data-stu-id="2911c-198">library</span></span>

<span data-ttu-id="2911c-199">Коллекция интерфейсов API, которые могут быть вызваны приложениями или другими библиотеками.</span><span class="sxs-lookup"><span data-stu-id="2911c-199">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="2911c-200">Библиотека .NET состоит из одной или нескольких [сборок](#assembly).</span><span class="sxs-lookup"><span data-stu-id="2911c-200">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="2911c-201">Слова "библиотека" и [платформа](#framework) часто используются как синонимы.</span><span class="sxs-lookup"><span data-stu-id="2911c-201">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="2911c-202">метапакет</span><span class="sxs-lookup"><span data-stu-id="2911c-202">metapackage</span></span>

<span data-ttu-id="2911c-203">Пакет NuGet, не имеющий собственной библиотеки, но имеющий только список зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2911c-203">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="2911c-204">Включенные пакеты при необходимости могут сформировать API для целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="2911c-204">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="2911c-205">См. [пакеты, метапакеты и платформы](../core/packages.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-205">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="2911c-206">Mono</span><span class="sxs-lookup"><span data-stu-id="2911c-206">Mono</span></span>

<span data-ttu-id="2911c-207">Mono является реализацией .NET, которая в основном используется, если требуется небольшая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="2911c-207">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="2911c-208">Это среда выполнения, которая может работать в приложениях Xamarin на Android, Mac, iOS, tvOS и watchOS. Она предназначена преимущественно для приложений, предусматривающих компактную разработку.</span><span class="sxs-lookup"><span data-stu-id="2911c-208">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="2911c-209">Она поддерживает все текущие опубликованные версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="2911c-209">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="2911c-210">Исторически Mono реализовывала крупный API .NET Framework и эмулировала некоторые из наиболее популярных возможностей в Unix.</span><span class="sxs-lookup"><span data-stu-id="2911c-210">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="2911c-211">Иногда она использовалась для запуска приложений .NET, которые применяют эти возможности в Unix.</span><span class="sxs-lookup"><span data-stu-id="2911c-211">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="2911c-212">Mono обычно используется с JIT-компилятором, но также располагает полным статическим компилятором (заблаговременная компиляция), который используется на таких платформах, как iOS.</span><span class="sxs-lookup"><span data-stu-id="2911c-212">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="2911c-213">Дополнительные сведения о Mono см. в [соответствующей документации](https://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="2911c-213">To learn more about Mono, see the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="2911c-214">.NET</span><span class="sxs-lookup"><span data-stu-id="2911c-214">.NET</span></span>

<span data-ttu-id="2911c-215">Общий термин для [.NET Standard](#net-standard) и всех [реализаций .NET](#implementation-of-net) и рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="2911c-215">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="2911c-216">Всегда пишется прописными буквами. Написание ".Net" не используется.</span><span class="sxs-lookup"><span data-stu-id="2911c-216">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="2911c-217">См. [руководство по .NET](index.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-217">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="2911c-218">.NET Core</span><span class="sxs-lookup"><span data-stu-id="2911c-218">.NET Core</span></span> 

<span data-ttu-id="2911c-219">Кроссплатформенная, высокопроизводительная, основанная на открытом исходном коде реализация .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-219">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="2911c-220">Включает в себя среду выполнения CoreCLR, среду выполнения AOT Core (CoreRT в разработке), библиотеку базовых классов Core и пакет SDK для Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-220">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="2911c-221">См. [.NET Core](../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-221">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="2911c-222">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="2911c-222">.NET Core CLI</span></span>

<span data-ttu-id="2911c-223">Кроссплатформенная цепочка инструментов для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-223">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="2911c-224">См. [Средства интерфейса командной строки (CLI) .NET Core](../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-224">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="2911c-225">Пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="2911c-225">.NET Core SDK</span></span>

<span data-ttu-id="2911c-226">Набор библиотек и средств, которые позволяют разработчикам создавать приложения и библиотеки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-226">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="2911c-227">Включает в себя [.NET Core CLI](#net-core-cli) для построения приложения, библиотеки и среды выполнения .NET Core для создания и запуска приложений и исполняемый файл dotnet (*dotnet.exe*), который выполняет команды CLI и запускает приложения.</span><span class="sxs-lookup"><span data-stu-id="2911c-227">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="2911c-228">См. [Обзор пакета SDK для .NET Core](../core/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-228">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="2911c-229">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2911c-229">.NET Framework</span></span>

<span data-ttu-id="2911c-230">Реализация .NET, работающая только в Windows.</span><span class="sxs-lookup"><span data-stu-id="2911c-230">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="2911c-231">Включает в себя Common Language Runtime (CLR), библиотеку базовых классов и библиотеки платформы приложений, например ASP.NET, Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="2911c-231">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="2911c-232">См. [Руководство по .NET Framework](../framework/index.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-232">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="2911c-233">.NET Native</span><span class="sxs-lookup"><span data-stu-id="2911c-233">.NET Native</span></span>

<span data-ttu-id="2911c-234">Цепочка инструментов компилятора, которая создает машинный код в режиме AOT в отличие от режима JIT.</span><span class="sxs-lookup"><span data-stu-id="2911c-234">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="2911c-235">Компиляция происходит на компьютере разработчика, аналогично тому, как работает компилятор и компоновщик C++.</span><span class="sxs-lookup"><span data-stu-id="2911c-235">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="2911c-236">Она удаляет неиспользуемый код и тратит больше времени на его оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="2911c-236">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="2911c-237">Она извлекает код из библиотек и объединяет их в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="2911c-237">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="2911c-238">Результатом является один модуль, который представляет все приложение.</span><span class="sxs-lookup"><span data-stu-id="2911c-238">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="2911c-239">UWP была первой платформой приложений, поддерживаемой .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2911c-239">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="2911c-240">Теперь мы поддерживаем построение собственных консольных приложений для Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2911c-240">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="2911c-241">См.[Введение в машинный код .NET и CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-241">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="2911c-242">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="2911c-242">.NET Standard</span></span>

<span data-ttu-id="2911c-243">Формальная спецификация API-интерфейсов .NET, которые доступны в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-243">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="2911c-244">Спецификацию .NET Standard иногда в документации называют библиотекой.</span><span class="sxs-lookup"><span data-stu-id="2911c-244">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="2911c-245">Так как библиотека содержит реализации API-интерфейсов, а не только спецификации (интерфейсы), неверно называть .NET Standard "библиотека".</span><span class="sxs-lookup"><span data-stu-id="2911c-245">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="2911c-246">Мы планируем исключить это использование из документации, за исключением применительно к имени метапакета .NET Standard (`NETStandard.Library`).</span><span class="sxs-lookup"><span data-stu-id="2911c-246">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="2911c-247">См. [.NET Standard](net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-247">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="2911c-248">NGEN</span><span class="sxs-lookup"><span data-stu-id="2911c-248">NGEN</span></span>

<span data-ttu-id="2911c-249">Создание образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="2911c-249">Native (image) generation.</span></span>

<span data-ttu-id="2911c-250">Эту технологию можно считать постоянным JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="2911c-250">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="2911c-251">Как правило, он компилирует код на компьютере, где код выполняется. Но компиляция обычно происходит во время установки.</span><span class="sxs-lookup"><span data-stu-id="2911c-251">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="2911c-252">пакет</span><span class="sxs-lookup"><span data-stu-id="2911c-252">package</span></span>

<span data-ttu-id="2911c-253">Пакет NuGet &mdash; или просто пакет &mdash; — это *ZIP*-файл с одной сборкой с одинаковым именем или несколькими, а также с дополнительными метаданными, такими как имя автора.</span><span class="sxs-lookup"><span data-stu-id="2911c-253">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="2911c-254">*ZIP*-файл имеет расширение *NUPKG* и может содержать ресурсы, такие как *DLL*-файлы и *XML*-файлы для нескольких целевых платформ и версий.</span><span class="sxs-lookup"><span data-stu-id="2911c-254">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="2911c-255">При установке в приложении или библиотеке выбор соответствующих ресурсов осуществляется в зависимости от целевой платформы, указанной приложением или библиотекой.</span><span class="sxs-lookup"><span data-stu-id="2911c-255">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="2911c-256">Ресурсы, которые определяют интерфейс, находятся в папке *ref*, а ресурсы, которые определяют реализацию, находятся в папке *lib*.</span><span class="sxs-lookup"><span data-stu-id="2911c-256">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="2911c-257">platform</span><span class="sxs-lookup"><span data-stu-id="2911c-257">platform</span></span>

<span data-ttu-id="2911c-258">Операционная система и оборудование, на котором она выполняется, например Windows, macOS, Linux, iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="2911c-258">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="2911c-259">Ниже приведены примеры использования в предложениях.</span><span class="sxs-lookup"><span data-stu-id="2911c-259">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="2911c-260">".NET Core — это кроссплатформенная реализация .NET".</span><span class="sxs-lookup"><span data-stu-id="2911c-260">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="2911c-261">"Профили PCL относятся к платформам Майкрософт, а .NET Standard не зависит от платформы".</span><span class="sxs-lookup"><span data-stu-id="2911c-261">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="2911c-262">В документации по .NET часто используется термин "платформа .NET" для обозначения либо реализации .NET либо стека .NET, включая все реализации.</span><span class="sxs-lookup"><span data-stu-id="2911c-262">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="2911c-263">Оба этих варианта, как правило, приводят к путанице с основным значением (ОС или оборудование), поэтому мы планируем исключить их из документации.</span><span class="sxs-lookup"><span data-stu-id="2911c-263">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="2911c-264">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="2911c-264">runtime</span></span>

<span data-ttu-id="2911c-265">Среда выполнения для управляемой программы.</span><span class="sxs-lookup"><span data-stu-id="2911c-265">The execution environment for a managed program.</span></span>

<span data-ttu-id="2911c-266">Операционная система является частью среды выполнения, но не входит в среду выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-266">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="2911c-267">Ниже приведены несколько примеров сред выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-267">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="2911c-268">Среда CLR</span><span class="sxs-lookup"><span data-stu-id="2911c-268">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="2911c-269">Общеязыковая среда выполнения Core (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="2911c-269">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="2911c-270">.NET Native (для UWP)</span><span class="sxs-lookup"><span data-stu-id="2911c-270">.NET Native (for UWP)</span></span>
- <span data-ttu-id="2911c-271">Среда выполнения Mono</span><span class="sxs-lookup"><span data-stu-id="2911c-271">Mono runtime</span></span>

<span data-ttu-id="2911c-272">Иногда в документации по .NET термин "среда выполнения" используется для обозначения реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-272">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="2911c-273">Например, в следующих предложениях термин содержит "среда выполнения" следует заменить на "реализация".</span><span class="sxs-lookup"><span data-stu-id="2911c-273">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="2911c-274">"Различные среды выполнения .NET реализуют конкретные версии .NET Standard".</span><span class="sxs-lookup"><span data-stu-id="2911c-274">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="2911c-275">"Библиотеки, предназначенные для различных сред выполнения, должны быть нацелены на эту платформу".</span><span class="sxs-lookup"><span data-stu-id="2911c-275">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="2911c-276">(по отношению к .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="2911c-276">(referring to .NET Standard)</span></span>
- <span data-ttu-id="2911c-277">"Различные среды выполнения .NET реализуют конкретные версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="2911c-277">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="2911c-278">…</span><span class="sxs-lookup"><span data-stu-id="2911c-278">…</span></span> <span data-ttu-id="2911c-279">Каждая версия среды выполнения .NET объявляет наибольшую версию поддерживаемой .NET Standard."</span><span class="sxs-lookup"><span data-stu-id="2911c-279">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="2911c-280">Мы планируем исключить это несогласованное использование.</span><span class="sxs-lookup"><span data-stu-id="2911c-280">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="2911c-281">стек</span><span class="sxs-lookup"><span data-stu-id="2911c-281">stack</span></span>

<span data-ttu-id="2911c-282">Набор программных технологий, которые используются совместно для сборки и запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="2911c-282">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="2911c-283">"Стек .NET" относится к .NET Standard и всем реализациям .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-283">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="2911c-284">"Стеком .NET" может называться одна реализация .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-284">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="2911c-285">целевая платформа</span><span class="sxs-lookup"><span data-stu-id="2911c-285">target framework</span></span>

<span data-ttu-id="2911c-286">Коллекция API-интерфейсов, которую использует приложение или библиотека .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-286">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="2911c-287">Приложение или библиотека могут быть предназначены для версии .NET Standard (например, .NET Standard 2.0), которая представляет собой спецификацию для стандартного набора API-интерфейсов во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-287">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="2911c-288">Приложение или библиотека могут также работать в версии конкретной реализации .NET. В этом случае они получают доступ к API-интерфейсам конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="2911c-288">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="2911c-289">Например, приложение, предназначенное для Xamarin.iOS, получает доступ к предоставляемым Xamarin программам-оболочкам API iOS.</span><span class="sxs-lookup"><span data-stu-id="2911c-289">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="2911c-290">Для некоторых целевых платформ (например, .NET Framework) доступные API-интерфейсы определяются сборками, устанавливаемыми реализацией .NET в системе, в число которых могут входить API-интерфейсы платформ приложений (например, ASP.NET, WinForms).</span><span class="sxs-lookup"><span data-stu-id="2911c-290">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="2911c-291">Для целевых платформ на основе пакетов (например, .NET Standard и .NET Core) API-интерфейсы платформы определяются пакетами, установленными в приложении или библиотеке.</span><span class="sxs-lookup"><span data-stu-id="2911c-291">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="2911c-292">В этом случае целевая платформа неявно задает метапакет, который ссылается на все пакеты, составляющие платформу.</span><span class="sxs-lookup"><span data-stu-id="2911c-292">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="2911c-293">См. [Требуемые версии .NET Framework](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-293">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="2911c-294">TFM</span><span class="sxs-lookup"><span data-stu-id="2911c-294">TFM</span></span>

<span data-ttu-id="2911c-295">Моникер целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="2911c-295">Target framework moniker.</span></span>

<span data-ttu-id="2911c-296">Стандартизированный формат маркера для указания целевой платформы приложения или библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="2911c-296">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="2911c-297">Целевые платформы обычно называются короткими именами, например `net462`.</span><span class="sxs-lookup"><span data-stu-id="2911c-297">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="2911c-298">Существуют полноформатные TFM (например. NETFramework, версия = 4.6.2), но они обычно не используются для указания целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="2911c-298">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="2911c-299">См. [Требуемые версии .NET Framework](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2911c-299">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="2911c-300">UWP</span><span class="sxs-lookup"><span data-stu-id="2911c-300">UWP</span></span>

<span data-ttu-id="2911c-301">Универсальная платформа Windows.</span><span class="sxs-lookup"><span data-stu-id="2911c-301">Universal Windows Platform.</span></span>

<span data-ttu-id="2911c-302">Реализация .NET, которая используется для создания современных приложений Windows с поддержкой сенсорного ввода и программного обеспечения для Интернета вещей (IoT).</span><span class="sxs-lookup"><span data-stu-id="2911c-302">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="2911c-303">Она предназначена для объединения различных типов устройств, которые могут потребоваться, включая ПК, планшеты, планшетофоны, телефоны и даже Xbox.</span><span class="sxs-lookup"><span data-stu-id="2911c-303">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="2911c-304">UWP предоставляет много служб, таких как централизованный магазин приложений, среда выполнения (AppContainer) и набор API-интерфейсов Windows для использования вместо Win32 (WinRT).</span><span class="sxs-lookup"><span data-stu-id="2911c-304">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="2911c-305">Приложения могут быть написаны на C++, C#, VB.NET и JavaScript.</span><span class="sxs-lookup"><span data-stu-id="2911c-305">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="2911c-306">При использовании C# и VB.NET API-интерфейсы .NET предоставляются .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2911c-306">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="2911c-307">См. также</span><span class="sxs-lookup"><span data-stu-id="2911c-307">See also</span></span>

[<span data-ttu-id="2911c-308">Руководство по .NET</span><span class="sxs-lookup"><span data-stu-id="2911c-308">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="2911c-309">Руководство по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2911c-309">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="2911c-310">.NET Core</span><span class="sxs-lookup"><span data-stu-id="2911c-310">.NET Core</span></span>](../core/index.md)  
[<span data-ttu-id="2911c-311">Обзор ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2911c-311">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
[<span data-ttu-id="2911c-312">Обзор ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2911c-312">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  

