---
title: Глоссарий по .NET
description: Узнайте значение выбранных терминов, используемых в документации по .NET.
keywords: Глоссарий по .NET, словарь .NET, терминология .NET, платформа .NET, среда .NET, среда выполнения .NET
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33123732514a53574036f6f8e948b2cf9acb9229
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="net-glossary"></a><span data-ttu-id="685cd-104">Глоссарий по .NET</span><span class="sxs-lookup"><span data-stu-id="685cd-104">.NET Glossary</span></span>

<span data-ttu-id="685cd-105">Основная цель этого глоссария — объяснить значения выбранных терминов и сокращений, которые часто встречаются в документации по .NET без определений.</span><span class="sxs-lookup"><span data-stu-id="685cd-105">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="685cd-106">AOT</span><span class="sxs-lookup"><span data-stu-id="685cd-106">AOT</span></span>

<span data-ttu-id="685cd-107">Компилятор AOT.</span><span class="sxs-lookup"><span data-stu-id="685cd-107">Ahead-of-time compiler.</span></span>

<span data-ttu-id="685cd-108">Аналогично [JIT](#jit), этот компилятор также преобразует [IL](#il) в машинный код.</span><span class="sxs-lookup"><span data-stu-id="685cd-108">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="685cd-109">В отличие от JIT-компиляции AOT-компиляция происходит до выполнения приложения и обычно осуществляется на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="685cd-109">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="685cd-110">Так как цепочки средств AOT не компилируются во время выполнения, они не сокращают время, затраченное на компиляцию.</span><span class="sxs-lookup"><span data-stu-id="685cd-110">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="685cd-111">Это означает, что они могут тратить больше времени на оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="685cd-111">That means they can spend more time optimizing.</span></span> <span data-ttu-id="685cd-112">Так как контекстом AOT является все приложение, AOT-компилятор также выполняет межмодульное связывание и анализ всей программы. Это означает, что соблюдаются все ссылки и создается один исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="685cd-112">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="685cd-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="685cd-113">ASP.NET</span></span> 

<span data-ttu-id="685cd-114">Исходная реализация ASP.NET, которая поставляется вместе с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="685cd-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="685cd-115">Иногда ASP.NET является общим термином, который относится к обеим реализациям ASP.NET, включая ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="685cd-116">Значение термина в заданном экземпляре определяется контекстом.</span><span class="sxs-lookup"><span data-stu-id="685cd-116">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="685cd-117">Явно укажите ASP.NET 4.x в тех ситуациях, когда важно избежать путаницы, поскольку термин ASP.NET может относиться к обеим реализация.</span><span class="sxs-lookup"><span data-stu-id="685cd-117">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="685cd-118">См. [документацию по ASP.NET](/aspnet/#pivot=aspnet).</span><span class="sxs-lookup"><span data-stu-id="685cd-118">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="685cd-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="685cd-119">ASP.NET Core</span></span>

<span data-ttu-id="685cd-120">Кроссплатформенная, высокопроизводительная, основанная на открытом исходном коде реализация ASP.NET, построенная на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-120">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="685cd-121">См. [документацию по ASP.NET Core](/aspnet/#pivot=core).</span><span class="sxs-lookup"><span data-stu-id="685cd-121">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="685cd-122">сборка</span><span class="sxs-lookup"><span data-stu-id="685cd-122">assembly</span></span>

<span data-ttu-id="685cd-123">Файл *DLL*/*EXE*, который содержит коллекцию API-интерфейсов, вызываемых приложениями или другими сборками.</span><span class="sxs-lookup"><span data-stu-id="685cd-123">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="685cd-124">Сборка может включать разные типы, например интерфейсы, классы, структуры, перечисления и делегаты.</span><span class="sxs-lookup"><span data-stu-id="685cd-124">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="685cd-125">Сборки в папке *bin* проекта иногда называют *двоичными файлами*.</span><span class="sxs-lookup"><span data-stu-id="685cd-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="685cd-126">См. также [библиотека](#library).</span><span class="sxs-lookup"><span data-stu-id="685cd-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="685cd-127">CLR</span><span class="sxs-lookup"><span data-stu-id="685cd-127">CLR</span></span>

<span data-ttu-id="685cd-128">Общеязыковая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="685cd-128">Common Language Runtime.</span></span>

<span data-ttu-id="685cd-129">Точное значение зависит от контекста, но обычно термин относится к среде выполнения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="685cd-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="685cd-130">Среда CLR обрабатывает выделение памяти и управление ей.</span><span class="sxs-lookup"><span data-stu-id="685cd-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="685cd-131">Среда CLR также является виртуальной машиной, которая не только выполняет приложения, но также создает и компилирует код с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="685cd-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="685cd-132">Текущая реализация среды CLR доступна только для Windows.</span><span class="sxs-lookup"><span data-stu-id="685cd-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="685cd-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="685cd-133">CoreCLR</span></span>

<span data-ttu-id="685cd-134">Среда CLR .NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="685cd-135">Эта среда CLR создана на той же базе кода, что и среда CLR.</span><span class="sxs-lookup"><span data-stu-id="685cd-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="685cd-136">Первоначально CoreCLR являлась средой выполнения Silverlight и должна была выполняться на нескольких платформах, в частности Windows и OS X. Теперь CoreCLR является частью .NET Core и представляет упрощенную версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="685cd-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="685cd-137">Она по-прежнему работает как кроссплатформенная и обеспечивает поддержку многих дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="685cd-137">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="685cd-138">CoreCLR также представляет собой виртуальную машину с возможностями выполнения JIT и кода.</span><span class="sxs-lookup"><span data-stu-id="685cd-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="685cd-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="685cd-139">CoreFX</span></span>

<span data-ttu-id="685cd-140">Библиотека базовых классов .NET Core (BCL)</span><span class="sxs-lookup"><span data-stu-id="685cd-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="685cd-141">Набор библиотек, которые составляют пространства имен System.* (и в некоторой степени Microsoft*).</span><span class="sxs-lookup"><span data-stu-id="685cd-141">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="685cd-142">BCL — это универсальная платформа низкого уровня, которая является основой платформ приложений более высокого уровня, например ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="685cd-143">Исходный код BCL .NET Core содержится в [репозитории CoreFX](https://github.com/dotnet/corefx).</span><span class="sxs-lookup"><span data-stu-id="685cd-143">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="685cd-144">Но большая часть API-интерфейсов .NET Core также доступна в .NET Framework, поэтому CoreFX можно представить как ветвь BCL .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="685cd-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="685cd-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="685cd-145">CoreRT</span></span>

<span data-ttu-id="685cd-146">Среда выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-146">.NET Core runtime.</span></span>

<span data-ttu-id="685cd-147">В отличие от среды CLR или CoreCLR, CoreRT не является виртуальной машиной, поэтому она не включает средства для создания и выполнения кода "на лету", так как в ней отсутствует [JIT](#jit).</span><span class="sxs-lookup"><span data-stu-id="685cd-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="685cd-148">Но она поддерживает [сборку мусора](#gc) и возможности идентификации типа среды выполнения (RTTI) и отражения.</span><span class="sxs-lookup"><span data-stu-id="685cd-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="685cd-149">Ее система типов разработана таким образом, что метаданные для отражения не требуется.</span><span class="sxs-lookup"><span data-stu-id="685cd-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="685cd-150">Это обеспечивает наличие цепочки инструментов [AOT](#aot), которая может связать лишние метаданные и (что более важно) определить код, который приложение не использует.</span><span class="sxs-lookup"><span data-stu-id="685cd-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="685cd-151">CoreRT находится в разработке.</span><span class="sxs-lookup"><span data-stu-id="685cd-151">CoreRT is in development.</span></span>

<span data-ttu-id="685cd-152">См.[Введение в машинный код .NET и CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="685cd-153">экосистема</span><span class="sxs-lookup"><span data-stu-id="685cd-153">ecosystem</span></span>

<span data-ttu-id="685cd-154">Все программное обеспечение среды выполнения, средства разработки и ресурсы сообщества, которые используются для построения и запуска приложений для заданной технологии.</span><span class="sxs-lookup"><span data-stu-id="685cd-154">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="685cd-155">Термин "экосистема .NET" отличается от аналогичных терминов, таких как "стек .NET", тем, что включает сторонние приложения и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="685cd-155">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="685cd-156">Ниже приведен пример термина в предложении.</span><span class="sxs-lookup"><span data-stu-id="685cd-156">Here's an example in a sentence:</span></span>

- <span data-ttu-id="685cd-157">"[.NET Standard](#net-standard) создана для того, чтобы повысить согласованность экосистемы .NET".</span><span class="sxs-lookup"><span data-stu-id="685cd-157">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="685cd-158">платформа</span><span class="sxs-lookup"><span data-stu-id="685cd-158">framework</span></span>

<span data-ttu-id="685cd-159">Обычно это всеобъемлющая коллекция API-интерфейсов, которая упрощает разработку и развертывание приложений, основанных на определенной технологии.</span><span class="sxs-lookup"><span data-stu-id="685cd-159">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="685cd-160">В этом общем смысле ASP.NET Core и Windows Forms являются примерами платформ приложений.</span><span class="sxs-lookup"><span data-stu-id="685cd-160">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="685cd-161">См. также [библиотека](#library).</span><span class="sxs-lookup"><span data-stu-id="685cd-161">See also [library](#library).</span></span>

<span data-ttu-id="685cd-162">Слово "платформа" имеет более специфичное техническое значение в следующих терминах.</span><span class="sxs-lookup"><span data-stu-id="685cd-162">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="685cd-163">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="685cd-163">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="685cd-164">целевая платформа</span><span class="sxs-lookup"><span data-stu-id="685cd-164">target framework</span></span>](#target-framework)
* [<span data-ttu-id="685cd-165">TFM (моникер целевой платформы)</span><span class="sxs-lookup"><span data-stu-id="685cd-165">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="685cd-166">В существующей документации "платформа" иногда означает [реализацию .NET](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="685cd-166">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="685cd-167">Например, в статье .NET Core может упоминаться как платформа.</span><span class="sxs-lookup"><span data-stu-id="685cd-167">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="685cd-168">Мы планируем избавиться от путаницы в документации.</span><span class="sxs-lookup"><span data-stu-id="685cd-168">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="685cd-169">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="685cd-169">GC</span></span>

<span data-ttu-id="685cd-170">Сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="685cd-170">Garbage collector.</span></span>

<span data-ttu-id="685cd-171">Сборщик мусора является реализацией автоматического управления памятью.</span><span class="sxs-lookup"><span data-stu-id="685cd-171">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="685cd-172">Сборщик мусора освобождает память, занятую объектами, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="685cd-172">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="685cd-173">См. [Сборка мусора](garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-173">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="685cd-174">IL</span><span class="sxs-lookup"><span data-stu-id="685cd-174">IL</span></span>

<span data-ttu-id="685cd-175">Промежуточный язык.</span><span class="sxs-lookup"><span data-stu-id="685cd-175">Intermediate language.</span></span>

<span data-ttu-id="685cd-176">Языки .NET более высокого уровня, например C#, компилируются до независимого от оборудования набора инструкций, который называется промежуточным языком (IL).</span><span class="sxs-lookup"><span data-stu-id="685cd-176">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="685cd-177">IL иногда называют MSIL (Microsoft IL) или CIL (общим IL).</span><span class="sxs-lookup"><span data-stu-id="685cd-177">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="685cd-178">JIT</span><span class="sxs-lookup"><span data-stu-id="685cd-178">JIT</span></span>

<span data-ttu-id="685cd-179">JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="685cd-179">Just-in-time compiler.</span></span>

<span data-ttu-id="685cd-180">Аналогично [AOT](#aot), этот компилятор преобразует [IL](#il) в машинный код, который понимает обработчик.</span><span class="sxs-lookup"><span data-stu-id="685cd-180">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="685cd-181">В отличие от AOT, JIT-компиляция происходит по требованию и осуществляется на том же компьютере, где должен выполняться код.</span><span class="sxs-lookup"><span data-stu-id="685cd-181">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="685cd-182">Так как JIT-компиляция происходит во время выполнения приложения, время компиляции является частью времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="685cd-182">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="685cd-183">Таким образом, JIT-компиляторы должны поддерживать баланс между временем оптимизации кода и экономии, к которой может привести к результирующий код.</span><span class="sxs-lookup"><span data-stu-id="685cd-183">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="685cd-184">Но JIT знает фактическое оборудование и может освободить разработчиков от поставки различных реализаций.</span><span class="sxs-lookup"><span data-stu-id="685cd-184">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="685cd-185">реализация .NET</span><span class="sxs-lookup"><span data-stu-id="685cd-185">implementation of .NET</span></span>

<span data-ttu-id="685cd-186">Реализация .NET включает в себя следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="685cd-186">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="685cd-187">Одна среда выполнения или несколько.</span><span class="sxs-lookup"><span data-stu-id="685cd-187">One or more runtimes.</span></span> <span data-ttu-id="685cd-188">Примеры: CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="685cd-188">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="685cd-189">Библиотека классов, которая реализует версию .NET Standard, а также может содержать дополнительные API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="685cd-189">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="685cd-190">Примеры: библиотека базовых классов .NET Framework, библиотека базовых классов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-190">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="685cd-191">(Необязательно) Одна платформа приложений или несколько.</span><span class="sxs-lookup"><span data-stu-id="685cd-191">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="685cd-192">Примеры: ASP.NET, Windows Forms и WPF входят в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="685cd-192">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="685cd-193">(Необязательно) Средства разработки.</span><span class="sxs-lookup"><span data-stu-id="685cd-193">Optionally, development tools.</span></span> <span data-ttu-id="685cd-194">Некоторые средства разработки, являются общими для нескольких реализаций.</span><span class="sxs-lookup"><span data-stu-id="685cd-194">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="685cd-195">Примеры реализаций .NET:</span><span class="sxs-lookup"><span data-stu-id="685cd-195">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="685cd-196">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="685cd-196">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="685cd-197">.NET Core</span><span class="sxs-lookup"><span data-stu-id="685cd-197">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="685cd-198">Универсальная платформа Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="685cd-198">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="685cd-199">библиотека</span><span class="sxs-lookup"><span data-stu-id="685cd-199">library</span></span>

<span data-ttu-id="685cd-200">Коллекция интерфейсов API, которые могут быть вызваны приложениями или другими библиотеками.</span><span class="sxs-lookup"><span data-stu-id="685cd-200">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="685cd-201">Библиотека .NET состоит из одной или нескольких [сборок](#assembly).</span><span class="sxs-lookup"><span data-stu-id="685cd-201">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="685cd-202">Слова "библиотека" и [платформа](#framework) часто используются как синонимы.</span><span class="sxs-lookup"><span data-stu-id="685cd-202">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="685cd-203">метапакет</span><span class="sxs-lookup"><span data-stu-id="685cd-203">metapackage</span></span>

<span data-ttu-id="685cd-204">Пакет NuGet, не имеющий собственной библиотеки, но имеющий только список зависимостей.</span><span class="sxs-lookup"><span data-stu-id="685cd-204">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="685cd-205">Включенные пакеты при необходимости могут сформировать API для целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="685cd-205">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="685cd-206">См. [пакеты, метапакеты и платформы](../core/packages.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-206">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="685cd-207">Mono</span><span class="sxs-lookup"><span data-stu-id="685cd-207">Mono</span></span>

<span data-ttu-id="685cd-208">Mono является реализацией .NET, которая в основном используется, если требуется небольшая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="685cd-208">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="685cd-209">Это среда выполнения, которая может работать в приложениях Xamarin на Android, Mac, iOS, tvOS и watchOS. Она предназначена преимущественно для приложений, предусматривающих компактную разработку.</span><span class="sxs-lookup"><span data-stu-id="685cd-209">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="685cd-210">Она поддерживает все текущие опубликованные версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="685cd-210">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="685cd-211">Исторически Mono реализовывала крупный API .NET Framework и эмулировала некоторые из наиболее популярных возможностей в Unix.</span><span class="sxs-lookup"><span data-stu-id="685cd-211">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="685cd-212">Иногда она использовалась для запуска приложений .NET, которые применяют эти возможности в Unix.</span><span class="sxs-lookup"><span data-stu-id="685cd-212">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="685cd-213">Mono обычно используется с JIT-компилятором, но также располагает полным статическим компилятором (заблаговременная компиляция), который используется на таких платформах, как iOS.</span><span class="sxs-lookup"><span data-stu-id="685cd-213">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="685cd-214">Дополнительные сведения о Mono см. в [соответствующей документации](http://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="685cd-214">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="685cd-215">.NET</span><span class="sxs-lookup"><span data-stu-id="685cd-215">.NET</span></span>

<span data-ttu-id="685cd-216">Общий термин для [.NET Standard](#net-standard) и всех [реализаций .NET](#implementation-of-net) и рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="685cd-216">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="685cd-217">Всегда пишется прописными буквами. Написание ".Net" не используется.</span><span class="sxs-lookup"><span data-stu-id="685cd-217">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="685cd-218">См. [руководство по .NET](index.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-218">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="685cd-219">.NET Core</span><span class="sxs-lookup"><span data-stu-id="685cd-219">.NET Core</span></span> 

<span data-ttu-id="685cd-220">Кроссплатформенная, высокопроизводительная, основанная на открытом исходном коде реализация .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-220">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="685cd-221">Включает в себя среду выполнения CoreCLR, среду выполнения AOT Core (CoreRT в разработке), библиотеку базовых классов Core и пакет SDK для Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-221">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="685cd-222">См. [.NET Core](../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-222">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="685cd-223">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="685cd-223">.NET Core CLI</span></span>

<span data-ttu-id="685cd-224">Кроссплатформенная цепочка инструментов для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-224">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="685cd-225">См. [Средства интерфейса командной строки (CLI) .NET Core](../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-225">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="685cd-226">Пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="685cd-226">.NET Core SDK</span></span>

<span data-ttu-id="685cd-227">Набор библиотек и средств, которые позволяют разработчикам создавать приложения и библиотеки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-227">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="685cd-228">Включает в себя [.NET Core CLI](#net-core-cli) для построения приложения, библиотеки и среды выполнения .NET Core для создания и запуска приложений и исполняемый файл dotnet (*dotnet.exe*), который выполняет команды CLI и запускает приложения.</span><span class="sxs-lookup"><span data-stu-id="685cd-228">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="685cd-229">См. [Обзор пакета SDK для .NET Core](../core/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-229">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="685cd-230">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="685cd-230">.NET Framework</span></span>

<span data-ttu-id="685cd-231">Реализация .NET, работающая только в Windows.</span><span class="sxs-lookup"><span data-stu-id="685cd-231">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="685cd-232">Включает в себя Common Language Runtime (CLR), библиотеку базовых классов и библиотеки платформы приложений, например ASP.NET, Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="685cd-232">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="685cd-233">См. [Руководство по .NET Framework](../framework/index.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-233">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="685cd-234">.NET Native</span><span class="sxs-lookup"><span data-stu-id="685cd-234">.NET Native</span></span>

<span data-ttu-id="685cd-235">Цепочка инструментов компилятора, которая создает машинный код в режиме AOT в отличие от режима JIT.</span><span class="sxs-lookup"><span data-stu-id="685cd-235">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="685cd-236">Компиляция происходит на компьютере разработчика, аналогично тому, как работает компилятор и компоновщик C++.</span><span class="sxs-lookup"><span data-stu-id="685cd-236">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="685cd-237">Она удаляет неиспользуемый код и тратит больше времени на его оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="685cd-237">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="685cd-238">Она извлекает код из библиотек и объединяет их в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="685cd-238">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="685cd-239">Результатом является один модуль, который представляет все приложение.</span><span class="sxs-lookup"><span data-stu-id="685cd-239">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="685cd-240">UWP была первой платформой приложений, поддерживаемой .NET Native.</span><span class="sxs-lookup"><span data-stu-id="685cd-240">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="685cd-241">Теперь мы поддерживаем построение собственных консольных приложений для Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="685cd-241">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="685cd-242">См.[Введение в машинный код .NET и CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-242">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="685cd-243">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="685cd-243">.NET Standard</span></span>

<span data-ttu-id="685cd-244">Формальная спецификация API-интерфейсов .NET, которые доступны в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-244">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="685cd-245">Спецификацию .NET Standard иногда в документации называют библиотекой.</span><span class="sxs-lookup"><span data-stu-id="685cd-245">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="685cd-246">Так как библиотека содержит реализации API-интерфейсов, а не только спецификации (интерфейсы), неверно называть .NET Standard "библиотека".</span><span class="sxs-lookup"><span data-stu-id="685cd-246">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="685cd-247">Мы планируем исключить это использование из документации, за исключением применительно к имени метапакета .NET Standard (`NETStandard.Library`).</span><span class="sxs-lookup"><span data-stu-id="685cd-247">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="685cd-248">См. [.NET Standard](net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-248">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="685cd-249">NGEN</span><span class="sxs-lookup"><span data-stu-id="685cd-249">NGEN</span></span>

<span data-ttu-id="685cd-250">Создание образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="685cd-250">Native (image) generation.</span></span>

<span data-ttu-id="685cd-251">Эту технологию можно считать постоянным JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="685cd-251">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="685cd-252">Как правило, он компилирует код на компьютере, где код выполняется. Но компиляция обычно происходит во время установки.</span><span class="sxs-lookup"><span data-stu-id="685cd-252">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="685cd-253">пакет</span><span class="sxs-lookup"><span data-stu-id="685cd-253">package</span></span>

<span data-ttu-id="685cd-254">Пакет NuGet &mdash; или просто пакет &mdash; — это *ZIP*-файл с одной сборкой с одинаковым именем или несколькими, а также с дополнительными метаданными, такими как имя автора.</span><span class="sxs-lookup"><span data-stu-id="685cd-254">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="685cd-255">*ZIP*-файл имеет расширение *NUPKG* и может содержать ресурсы, такие как *DLL*-файлы и *XML*-файлы для нескольких целевых платформ и версий.</span><span class="sxs-lookup"><span data-stu-id="685cd-255">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="685cd-256">При установке в приложении или библиотеке выбор соответствующих ресурсов осуществляется в зависимости от целевой платформы, указанной приложением или библиотекой.</span><span class="sxs-lookup"><span data-stu-id="685cd-256">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="685cd-257">Ресурсы, которые определяют интерфейс, находятся в папке *ref*, а ресурсы, которые определяют реализацию, находятся в папке *lib*.</span><span class="sxs-lookup"><span data-stu-id="685cd-257">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="685cd-258">platform</span><span class="sxs-lookup"><span data-stu-id="685cd-258">platform</span></span>

<span data-ttu-id="685cd-259">Операционная система и оборудование, на котором она выполняется, например Windows, macOS, Linux, iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="685cd-259">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="685cd-260">Ниже приведены примеры использования в предложениях.</span><span class="sxs-lookup"><span data-stu-id="685cd-260">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="685cd-261">".NET Core — это кроссплатформенная реализация .NET".</span><span class="sxs-lookup"><span data-stu-id="685cd-261">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="685cd-262">"Профили PCL относятся к платформам Майкрософт, а .NET Standard не зависит от платформы".</span><span class="sxs-lookup"><span data-stu-id="685cd-262">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="685cd-263">В документации по .NET часто используется термин "платформа .NET" для обозначения либо реализации .NET либо стека .NET, включая все реализации.</span><span class="sxs-lookup"><span data-stu-id="685cd-263">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="685cd-264">Оба этих варианта, как правило, приводят к путанице с основным значением (ОС или оборудование), поэтому мы планируем исключить их из документации.</span><span class="sxs-lookup"><span data-stu-id="685cd-264">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="685cd-265">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="685cd-265">runtime</span></span>

<span data-ttu-id="685cd-266">Среда выполнения для управляемой программы.</span><span class="sxs-lookup"><span data-stu-id="685cd-266">The execution environment for a managed program.</span></span>

<span data-ttu-id="685cd-267">Операционная система является частью среды выполнения, но не входит в среду выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-267">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="685cd-268">Ниже приведены несколько примеров сред выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-268">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="685cd-269">Среда CLR</span><span class="sxs-lookup"><span data-stu-id="685cd-269">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="685cd-270">Общеязыковая среда выполнения Core (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="685cd-270">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="685cd-271">.NET Native (для UWP)</span><span class="sxs-lookup"><span data-stu-id="685cd-271">.NET Native (for UWP)</span></span>
- <span data-ttu-id="685cd-272">Среда выполнения Mono</span><span class="sxs-lookup"><span data-stu-id="685cd-272">Mono runtime</span></span>

<span data-ttu-id="685cd-273">Иногда в документации по .NET термин "среда выполнения" используется для обозначения реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-273">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="685cd-274">Например, в следующих предложениях термин содержит "среда выполнения" следует заменить на "реализация".</span><span class="sxs-lookup"><span data-stu-id="685cd-274">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="685cd-275">"Различные среды выполнения .NET реализуют конкретные версии .NET Standard".</span><span class="sxs-lookup"><span data-stu-id="685cd-275">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="685cd-276">"Библиотеки, предназначенные для различных сред выполнения, должны быть нацелены на эту платформу".</span><span class="sxs-lookup"><span data-stu-id="685cd-276">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="685cd-277">(по отношению к .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="685cd-277">(referring to .NET Standard)</span></span>
- <span data-ttu-id="685cd-278">"Различные среды выполнения .NET реализуют конкретные версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="685cd-278">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="685cd-279">…</span><span class="sxs-lookup"><span data-stu-id="685cd-279">…</span></span> <span data-ttu-id="685cd-280">Каждая версия среды выполнения .NET объявляет наибольшую версию поддерживаемой .NET Standard."</span><span class="sxs-lookup"><span data-stu-id="685cd-280">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="685cd-281">Мы планируем исключить это несогласованное использование.</span><span class="sxs-lookup"><span data-stu-id="685cd-281">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="685cd-282">стек</span><span class="sxs-lookup"><span data-stu-id="685cd-282">stack</span></span>

<span data-ttu-id="685cd-283">Набор программных технологий, которые используются совместно для сборки и запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="685cd-283">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="685cd-284">"Стек .NET" относится к .NET Standard и всем реализациям .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-284">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="685cd-285">"Стеком .NET" может называться одна реализация .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-285">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="685cd-286">целевая платформа</span><span class="sxs-lookup"><span data-stu-id="685cd-286">target framework</span></span>

<span data-ttu-id="685cd-287">Коллекция API-интерфейсов, которую использует приложение или библиотека .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-287">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="685cd-288">Приложение или библиотека могут быть предназначены для версии .NET Standard (например, .NET Standard 2.0), которая представляет собой спецификацию для стандартного набора API-интерфейсов во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-288">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="685cd-289">Приложение или библиотека могут также работать в версии конкретной реализации .NET. В этом случае они получают доступ к API-интерфейсам конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="685cd-289">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="685cd-290">Например, приложение, предназначенное для Xamarin.iOS, получает доступ к предоставляемым Xamarin программам-оболочкам API iOS.</span><span class="sxs-lookup"><span data-stu-id="685cd-290">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="685cd-291">Для некоторых целевых платформ (например, .NET Framework) доступные API-интерфейсы определяются сборками, устанавливаемыми реализацией .NET в системе, в число которых могут входить API-интерфейсы платформ приложений (например, ASP.NET, WinForms).</span><span class="sxs-lookup"><span data-stu-id="685cd-291">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="685cd-292">Для целевых платформ на основе пакетов (например, .NET Standard и .NET Core) API-интерфейсы платформы определяются пакетами, установленными в приложении или библиотеке.</span><span class="sxs-lookup"><span data-stu-id="685cd-292">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="685cd-293">В этом случае целевая платформа неявно задает метапакет, который ссылается на все пакеты, составляющие платформу.</span><span class="sxs-lookup"><span data-stu-id="685cd-293">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="685cd-294">См. [Требуемые версии .NET Framework](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-294">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="685cd-295">TFM</span><span class="sxs-lookup"><span data-stu-id="685cd-295">TFM</span></span>

<span data-ttu-id="685cd-296">Моникер целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="685cd-296">Target framework moniker.</span></span>

<span data-ttu-id="685cd-297">Стандартизированный формат маркера для указания целевой платформы приложения или библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="685cd-297">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="685cd-298">Целевые платформы обычно называются короткими именами, например `net462`.</span><span class="sxs-lookup"><span data-stu-id="685cd-298">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="685cd-299">Существуют полноформатные TFM (например. NETFramework, версия = 4.6.2), но они обычно не используются для указания целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="685cd-299">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="685cd-300">См. [Требуемые версии .NET Framework](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="685cd-300">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="685cd-301">UWP</span><span class="sxs-lookup"><span data-stu-id="685cd-301">UWP</span></span>

<span data-ttu-id="685cd-302">Универсальная платформа Windows.</span><span class="sxs-lookup"><span data-stu-id="685cd-302">Universal Windows Platform.</span></span>

<span data-ttu-id="685cd-303">Реализация .NET, которая используется для создания современных приложений Windows с поддержкой сенсорного ввода и программного обеспечения для Интернета вещей (IoT).</span><span class="sxs-lookup"><span data-stu-id="685cd-303">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="685cd-304">Она предназначена для объединения различных типов устройств, которые могут потребоваться, включая ПК, планшеты, планшетофоны, телефоны и даже Xbox.</span><span class="sxs-lookup"><span data-stu-id="685cd-304">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="685cd-305">UWP предоставляет много служб, таких как централизованный магазин приложений, среда выполнения (AppContainer) и набор API-интерфейсов Windows для использования вместо Win32 (WinRT).</span><span class="sxs-lookup"><span data-stu-id="685cd-305">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="685cd-306">Приложения могут быть написаны на C++, C#, VB.NET и JavaScript.</span><span class="sxs-lookup"><span data-stu-id="685cd-306">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="685cd-307">При использовании C# и VB.NET API-интерфейсы .NET предоставляются .NET Core.</span><span class="sxs-lookup"><span data-stu-id="685cd-307">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="685cd-308">См. также</span><span class="sxs-lookup"><span data-stu-id="685cd-308">See also</span></span>

[<span data-ttu-id="685cd-309">Руководство по .NET</span><span class="sxs-lookup"><span data-stu-id="685cd-309">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="685cd-310">Руководство по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="685cd-310">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="685cd-311">.NET Core</span><span class="sxs-lookup"><span data-stu-id="685cd-311">.NET Core</span></span>](../core/index.md)  
[<span data-ttu-id="685cd-312">Обзор ASP.NET</span><span class="sxs-lookup"><span data-stu-id="685cd-312">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
[<span data-ttu-id="685cd-313">Обзор ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="685cd-313">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  

