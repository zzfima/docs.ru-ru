---
title: Компиляция приложений с помощью машинного кода .NET
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5993cfdb0f50d8e474a4f18280d181d9ec2fdfa4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049657"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="e7af4-102">Компиляция приложений с помощью машинного кода .NET</span><span class="sxs-lookup"><span data-stu-id="e7af4-102">Compiling Apps with .NET Native</span></span>

<span data-ttu-id="e7af4-103">.NET Native — это технология предварительной компиляции для создания и развертывания приложений Windows, которые входят в состав Visual Studio 2015 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e7af4-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="e7af4-104">Она автоматически компилирует окончательные версии приложений, написанных в форме управляемого кода (C# или Visual Basic) и предназначенных для .NET Framework и Windows 10, в машинный код.</span><span class="sxs-lookup"><span data-stu-id="e7af4-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>

<span data-ttu-id="e7af4-105">Как правило приложения, предназначенные для платформа.NET Framework компилируются в промежуточный язык (IL).</span><span class="sxs-lookup"><span data-stu-id="e7af4-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="e7af4-106">Во время выполнения JIT-компилятор преобразует инструкции IL в машинный код.</span><span class="sxs-lookup"><span data-stu-id="e7af4-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="e7af4-107">Напротив, .NET Native компилирует приложения Windows непосредственно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="e7af4-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="e7af4-108">Для разработчиков это означает:</span><span class="sxs-lookup"><span data-stu-id="e7af4-108">For developers, this means:</span></span>

- <span data-ttu-id="e7af4-109">Приложения имеют производительность машинного кода.</span><span class="sxs-lookup"><span data-stu-id="e7af4-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="e7af4-110">Как правило, производительность будет представлять собой код, который сначала компилируется в IL, а затем компилируется в машинный код JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="e7af4-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span>

- <span data-ttu-id="e7af4-111">Можно продолжить программировать в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7af4-111">You can continue to program in C# or Visual Basic.</span></span>

- <span data-ttu-id="e7af4-112">Можно продолжать использовать преимущества ресурсов платформы .NET Framework, включая библиотеки классов, сбор мусора, автоматическое управление памяти и обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="e7af4-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>

<span data-ttu-id="e7af4-113">Для пользователей приложений .NET Native предоставляет следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="e7af4-113">For users of your apps, .NET Native offers these advantages:</span></span>

- <span data-ttu-id="e7af4-114">Более быстрое время выполнения большинства приложений и сценариев.</span><span class="sxs-lookup"><span data-stu-id="e7af4-114">Faster execution times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="e7af4-115">Ускоренное время запуска большинства приложений и сценариев.</span><span class="sxs-lookup"><span data-stu-id="e7af4-115">Faster startup times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="e7af4-116">Низкая стоимость развертывания и обновления.</span><span class="sxs-lookup"><span data-stu-id="e7af4-116">Low deployment and update costs.</span></span>

- <span data-ttu-id="e7af4-117">Оптимизированное использование памяти приложением.</span><span class="sxs-lookup"><span data-stu-id="e7af4-117">Optimized app memory usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7af4-118">Для большинства приложений и сценариев .NET Native предлагает значительно более быстрое время запуска и высокую производительность по сравнению с приложением, скомпилированным в IL или на образ NGEN.</span><span class="sxs-lookup"><span data-stu-id="e7af4-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="e7af4-119">Однако результаты могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="e7af4-119">However, your results may vary.</span></span> <span data-ttu-id="e7af4-120">Чтобы обеспечить преимущество приложения от улучшения производительности .NET Native, необходимо сравнить его производительность с non-.NET собственной версией приложения, используемой в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="e7af4-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="e7af4-121">Дополнительные сведения см. в разделе [Обзор сеанса анализа производительности](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="e7af4-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>

<span data-ttu-id="e7af4-122">Но .NET Native включает в себя больше, чем компиляция в машинный код.</span><span class="sxs-lookup"><span data-stu-id="e7af4-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="e7af4-123">Он преобразует способ построения и выполнения приложений на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7af4-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="e7af4-124">В частности:</span><span class="sxs-lookup"><span data-stu-id="e7af4-124">In particular:</span></span>

- <span data-ttu-id="e7af4-125">Во время предварительной компиляции необходимые части платформы .NET Framework статически связываются с приложением.</span><span class="sxs-lookup"><span data-stu-id="e7af4-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="e7af4-126">Это позволяет приложению работать с библиотеками локальных приложений платформы.NET Framework, а компилятору — выполнять глобальный анализ для улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="e7af4-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="e7af4-127">В результате приложения постоянно запускаются быстрее даже после обновлений платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7af4-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>

- <span data-ttu-id="e7af4-128">Среда выполнения .NET Native оптимизирована для статической предварительной компиляции, и в подавляющем большинстве случаев обеспечивается высочайшая производительность.</span><span class="sxs-lookup"><span data-stu-id="e7af4-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="e7af4-129">В то же время она сохраняет основные функции отражения, которые разработчики считают такими полезными.</span><span class="sxs-lookup"><span data-stu-id="e7af4-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>

- <span data-ttu-id="e7af4-130">.NET Native использует ту же серверную части, C++ что и компилятор, оптимизированный для сценариев статической предварительной компиляции.</span><span class="sxs-lookup"><span data-stu-id="e7af4-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>

<span data-ttu-id="e7af4-131">.NET Native может повысить производительность C++ для разработчиков управляемого кода, поскольку в нем используются те же или аналогичные средства C++ , что и в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="e7af4-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>

||<span data-ttu-id="e7af4-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="e7af4-132">.NET Native</span></span>|<span data-ttu-id="e7af4-133">C++</span><span class="sxs-lookup"><span data-stu-id="e7af4-133">C++</span></span>|
|-|----------------------------------------------------------------|-----------|
|<span data-ttu-id="e7af4-134">Библиотеки</span><span class="sxs-lookup"><span data-stu-id="e7af4-134">Libraries</span></span>|<span data-ttu-id="e7af4-135">Платформа.NET Framework + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="e7af4-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="e7af4-136">Win32 + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="e7af4-136">Win32 + Windows Runtime</span></span>|
|<span data-ttu-id="e7af4-137">Компилятор</span><span class="sxs-lookup"><span data-stu-id="e7af4-137">Compiler</span></span>|<span data-ttu-id="e7af4-138">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="e7af4-138">UTC optimizing compiler</span></span>|<span data-ttu-id="e7af4-139">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="e7af4-139">UTC optimizing compiler</span></span>|
|<span data-ttu-id="e7af4-140">Развернут</span><span class="sxs-lookup"><span data-stu-id="e7af4-140">Deployed</span></span>|<span data-ttu-id="e7af4-141">Готов к запуску двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="e7af4-141">Ready-to-run binaries</span></span>|<span data-ttu-id="e7af4-142">Готов к запуску двоичных файлов (ASM)</span><span class="sxs-lookup"><span data-stu-id="e7af4-142">Ready-to-run binaries (ASM)</span></span>|
|<span data-ttu-id="e7af4-143">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e7af4-143">Runtime</span></span>|<span data-ttu-id="e7af4-144">MRT.dll (минимальной среды CLR)</span><span class="sxs-lookup"><span data-stu-id="e7af4-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="e7af4-145">CRT.dll (среда выполнения C)</span><span class="sxs-lookup"><span data-stu-id="e7af4-145">CRT.dll (C Runtime)</span></span>|

<span data-ttu-id="e7af4-146">Для приложений, предназначенных для Windows 10, выполняется передача двоичных файлов компиляции машинного кода .NET в пакетах приложений (файлы APPX) в Магазин Windows.</span><span class="sxs-lookup"><span data-stu-id="e7af4-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e7af4-147">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e7af4-147">In This Section</span></span>

<span data-ttu-id="e7af4-148">Дополнительные сведения о разработке приложений при использовании компиляции машинного кода .NET см. в следующих разделах</span><span class="sxs-lookup"><span data-stu-id="e7af4-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>

- [<span data-ttu-id="e7af4-149">Начало работы компиляции кода .NET Native: Пошаговое руководство для разработчиков</span><span class="sxs-lookup"><span data-stu-id="e7af4-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](getting-started-with-net-native.md)

- <span data-ttu-id="e7af4-150">[.NET Native и компиляция:](net-native-and-compilation.md) Как .NET Native компилирует проект в машинный код.</span><span class="sxs-lookup"><span data-stu-id="e7af4-150">[.NET Native and Compilation:](net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>

- [<span data-ttu-id="e7af4-151">Отражение и .NET Native</span><span class="sxs-lookup"><span data-stu-id="e7af4-151">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

  - [<span data-ttu-id="e7af4-152">API-интерфейсы, основанные на отражении</span><span class="sxs-lookup"><span data-stu-id="e7af4-152">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)

  - [<span data-ttu-id="e7af4-153">Справочник по API отражения</span><span class="sxs-lookup"><span data-stu-id="e7af4-153">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)

  - [<span data-ttu-id="e7af4-154">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="e7af4-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)

- [<span data-ttu-id="e7af4-155">Сериализация и метаданные</span><span class="sxs-lookup"><span data-stu-id="e7af4-155">Serialization and Metadata</span></span>](serialization-and-metadata.md)

- [<span data-ttu-id="e7af4-156">Миграция приложения для Магазина Windows в .NET Native</span><span class="sxs-lookup"><span data-stu-id="e7af4-156">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)

- [<span data-ttu-id="e7af4-157">.NET Native. Устранение общих неполадок</span><span class="sxs-lookup"><span data-stu-id="e7af4-157">.NET Native General Troubleshooting</span></span>](net-native-general-troubleshooting.md)
