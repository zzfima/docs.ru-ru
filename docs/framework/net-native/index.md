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
ms.openlocfilehash: 1f176e81905fe68c6d740a13240fe814659a7a59
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128374"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="eb9c1-102">Компиляция приложений с помощью машинного кода .NET</span><span class="sxs-lookup"><span data-stu-id="eb9c1-102">Compiling Apps with .NET Native</span></span>

<span data-ttu-id="eb9c1-103">.NET Native — это технология предварительной компиляции для создания и развертывания приложений Windows, которые входят в состав Visual Studio 2015 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="eb9c1-104">Она автоматически компилирует окончательные версии приложений, написанных в форме управляемого кода (C# или Visual Basic) и предназначенных для .NET Framework и Windows 10, в машинный код.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>

<span data-ttu-id="eb9c1-105">Как правило приложения, предназначенные для платформа.NET Framework компилируются в промежуточный язык (IL).</span><span class="sxs-lookup"><span data-stu-id="eb9c1-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="eb9c1-106">Во время выполнения JIT-компилятор преобразует инструкции IL в машинный код.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="eb9c1-107">Напротив, .NET Native компилирует приложения Windows непосредственно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="eb9c1-108">Для разработчиков это означает:</span><span class="sxs-lookup"><span data-stu-id="eb9c1-108">For developers, this means:</span></span>

- <span data-ttu-id="eb9c1-109">Приложения имеют производительность машинного кода.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="eb9c1-110">Как правило, производительность будет представлять собой код, который сначала компилируется в IL, а затем компилируется в машинный код JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span>

- <span data-ttu-id="eb9c1-111">Можно продолжить программировать в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-111">You can continue to program in C# or Visual Basic.</span></span>

- <span data-ttu-id="eb9c1-112">Можно продолжать использовать преимущества ресурсов платформы .NET Framework, включая библиотеки классов, сбор мусора, автоматическое управление памяти и обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>

<span data-ttu-id="eb9c1-113">Для пользователей приложений .NET Native предоставляет следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="eb9c1-113">For users of your apps, .NET Native offers these advantages:</span></span>

- <span data-ttu-id="eb9c1-114">Более быстрое время выполнения большинства приложений и сценариев.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-114">Faster execution times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="eb9c1-115">Ускоренное время запуска большинства приложений и сценариев.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-115">Faster startup times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="eb9c1-116">Низкая стоимость развертывания и обновления.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-116">Low deployment and update costs.</span></span>

- <span data-ttu-id="eb9c1-117">Оптимизированное использование памяти приложением.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-117">Optimized app memory usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb9c1-118">Для большинства приложений и сценариев .NET Native предлагает значительно более быстрое время запуска и высокую производительность по сравнению с приложением, скомпилированным в IL или на образ NGEN.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="eb9c1-119">Однако результаты могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-119">However, your results may vary.</span></span> <span data-ttu-id="eb9c1-120">Чтобы обеспечить преимущество приложения от улучшения производительности .NET Native, необходимо сравнить его производительность с non-.NET собственной версией приложения, используемой в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="eb9c1-121">Дополнительные сведения см. в разделе [Обзор сеанса анализа производительности](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="eb9c1-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>

<span data-ttu-id="eb9c1-122">Но .NET Native включает в себя больше, чем компиляция в машинный код.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="eb9c1-123">Он преобразует способ построения и выполнения приложений на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="eb9c1-124">В частности:</span><span class="sxs-lookup"><span data-stu-id="eb9c1-124">In particular:</span></span>

- <span data-ttu-id="eb9c1-125">Во время предварительной компиляции необходимые части платформы .NET Framework статически связываются с приложением.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="eb9c1-126">Это позволяет приложению работать с библиотеками локальных приложений платформы.NET Framework, а компилятору — выполнять глобальный анализ для улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="eb9c1-127">В результате приложения постоянно запускаются быстрее даже после обновлений платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>

- <span data-ttu-id="eb9c1-128">Среда выполнения .NET Native оптимизирована для статической предварительной компиляции, и в подавляющем большинстве случаев обеспечивается высочайшая производительность.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="eb9c1-129">В то же время она сохраняет основные функции отражения, которые разработчики считают такими полезными.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>

- <span data-ttu-id="eb9c1-130">.NET Native использует ту же серверную части, C++ что и компилятор, оптимизированный для сценариев статической предварительной компиляции.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>

<span data-ttu-id="eb9c1-131">.NET Native может повысить производительность C++ для разработчиков управляемого кода, поскольку в нем используются те же или аналогичные средства C++ , что и в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>

||<span data-ttu-id="eb9c1-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="eb9c1-132">.NET Native</span></span>|<span data-ttu-id="eb9c1-133">C++</span><span class="sxs-lookup"><span data-stu-id="eb9c1-133">C++</span></span>|
|-|----------------------------------------------------------------|-----------|
|<span data-ttu-id="eb9c1-134">Библиотеки</span><span class="sxs-lookup"><span data-stu-id="eb9c1-134">Libraries</span></span>|<span data-ttu-id="eb9c1-135">Платформа.NET Framework + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="eb9c1-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="eb9c1-136">Win32 + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="eb9c1-136">Win32 + Windows Runtime</span></span>|
|<span data-ttu-id="eb9c1-137">Компилятор</span><span class="sxs-lookup"><span data-stu-id="eb9c1-137">Compiler</span></span>|<span data-ttu-id="eb9c1-138">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="eb9c1-138">UTC optimizing compiler</span></span>|<span data-ttu-id="eb9c1-139">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="eb9c1-139">UTC optimizing compiler</span></span>|
|<span data-ttu-id="eb9c1-140">Развернут</span><span class="sxs-lookup"><span data-stu-id="eb9c1-140">Deployed</span></span>|<span data-ttu-id="eb9c1-141">Готов к запуску двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="eb9c1-141">Ready-to-run binaries</span></span>|<span data-ttu-id="eb9c1-142">Готов к запуску двоичных файлов (ASM)</span><span class="sxs-lookup"><span data-stu-id="eb9c1-142">Ready-to-run binaries (ASM)</span></span>|
|<span data-ttu-id="eb9c1-143">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="eb9c1-143">Runtime</span></span>|<span data-ttu-id="eb9c1-144">MRT.dll (минимальной среды CLR)</span><span class="sxs-lookup"><span data-stu-id="eb9c1-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="eb9c1-145">CRT.dll (среда выполнения C)</span><span class="sxs-lookup"><span data-stu-id="eb9c1-145">CRT.dll (C Runtime)</span></span>|

<span data-ttu-id="eb9c1-146">Для приложений, предназначенных для Windows 10, выполняется передача двоичных файлов компиляции машинного кода .NET в пакетах приложений (файлы APPX) в Магазин Windows.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eb9c1-147">Содержание</span><span class="sxs-lookup"><span data-stu-id="eb9c1-147">In This Section</span></span>

<span data-ttu-id="eb9c1-148">Дополнительные сведения о разработке приложений при использовании компиляции машинного кода .NET см. в следующих разделах</span><span class="sxs-lookup"><span data-stu-id="eb9c1-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>

- [<span data-ttu-id="eb9c1-149">Приступая к компиляции кода с помощью машинного кода .NET: пошаговое руководство разработчика</span><span class="sxs-lookup"><span data-stu-id="eb9c1-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](getting-started-with-net-native.md)

- <span data-ttu-id="eb9c1-150">[Машинный код .NET и компиляция](net-native-and-compilation.md) — как проект компилируется в машинный код .NET.</span><span class="sxs-lookup"><span data-stu-id="eb9c1-150">[.NET Native and Compilation:](net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>

- [<span data-ttu-id="eb9c1-151">Отражение и .NET Native</span><span class="sxs-lookup"><span data-stu-id="eb9c1-151">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

  - [<span data-ttu-id="eb9c1-152">API-интерфейсы, основанные на отражении</span><span class="sxs-lookup"><span data-stu-id="eb9c1-152">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)

  - [<span data-ttu-id="eb9c1-153">Справочник по API отражения</span><span class="sxs-lookup"><span data-stu-id="eb9c1-153">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)

  - [<span data-ttu-id="eb9c1-154">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="eb9c1-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)

- [<span data-ttu-id="eb9c1-155">Сериализация и метаданные</span><span class="sxs-lookup"><span data-stu-id="eb9c1-155">Serialization and Metadata</span></span>](serialization-and-metadata.md)

- [<span data-ttu-id="eb9c1-156">Миграция приложения для Магазина Windows в .NET Native</span><span class="sxs-lookup"><span data-stu-id="eb9c1-156">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)

- [<span data-ttu-id="eb9c1-157">.NET Native. Устранение общих неполадок</span><span class="sxs-lookup"><span data-stu-id="eb9c1-157">.NET Native General Troubleshooting</span></span>](net-native-general-troubleshooting.md)
