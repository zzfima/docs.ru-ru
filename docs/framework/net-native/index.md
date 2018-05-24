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
ms.openlocfilehash: 6900bca2bd94f52ea5603c752681163cde52ce19
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="9a997-102">Компиляция приложений с помощью машинного кода .NET</span><span class="sxs-lookup"><span data-stu-id="9a997-102">Compiling Apps with .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="9a997-103"> Технология предварительной компиляции для построения и развертывания приложений Windows, входит в состав Visual Studio 2015 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="9a997-103"> is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="9a997-104">Она автоматически компилирует окончательные версии приложений, написанных в форме управляемого кода (C# или Visual Basic) и предназначенных для .NET Framework и Windows 10, в машинный код.</span><span class="sxs-lookup"><span data-stu-id="9a997-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="9a997-105">Как правило приложения, предназначенные для платформа.NET Framework компилируются в промежуточный язык (IL).</span><span class="sxs-lookup"><span data-stu-id="9a997-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="9a997-106">Во время выполнения JIT-компилятор преобразует инструкции IL в машинный код.</span><span class="sxs-lookup"><span data-stu-id="9a997-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="9a997-107">В отличие от этого [!INCLUDE[net_native](../../../includes/net-native-md.md)] компилирует приложения Windows непосредственно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="9a997-107">In contrast, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiles Windows apps directly to native code.</span></span> <span data-ttu-id="9a997-108">Для разработчиков это означает:</span><span class="sxs-lookup"><span data-stu-id="9a997-108">For developers, this means:</span></span>  
  
-   <span data-ttu-id="9a997-109">Приложения компонента производительность машинного кода.</span><span class="sxs-lookup"><span data-stu-id="9a997-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="9a997-110">Как правило производительность будет выше код, который сначала компилируется в IL и затем скомпилировать в машинный код с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="9a997-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
-   <span data-ttu-id="9a997-111">Можно продолжить программировать в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9a997-111">You can continue to program in C# or Visual Basic.</span></span>  
  
-   <span data-ttu-id="9a997-112">Можно продолжать использовать преимущества ресурсов платформы .NET Framework, включая библиотеки классов, сбор мусора, автоматическое управление памяти и обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="9a997-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="9a997-113">Для пользователей приложений [!INCLUDE[net_native](../../../includes/net-native-md.md)] обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="9a997-113">For users of your apps, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offers these advantages:</span></span>  
  
-   <span data-ttu-id="9a997-114">Сократить время выполнения для большинства приложений и сценариев.</span><span class="sxs-lookup"><span data-stu-id="9a997-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
-   <span data-ttu-id="9a997-115">Сократить время запуска для большинства приложений и сценариев.</span><span class="sxs-lookup"><span data-stu-id="9a997-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
-   <span data-ttu-id="9a997-116">Низкая стоимость развертывания и обновления.</span><span class="sxs-lookup"><span data-stu-id="9a997-116">Low deployment and update costs.</span></span>  
  
-   <span data-ttu-id="9a997-117">Оптимизированное использование памяти приложением.</span><span class="sxs-lookup"><span data-stu-id="9a997-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="9a997-118">Для большинства приложений и сценарии машинного кода .NET предлагает значительно сократить время запуска и более высокой производительностью по сравнению с приложение компилируется IL или образ NGEN.</span><span class="sxs-lookup"><span data-stu-id="9a997-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="9a997-119">Однако результаты могут различаться.</span><span class="sxs-lookup"><span data-stu-id="9a997-119">However, your results may vary.</span></span> <span data-ttu-id="9a997-120">Чтобы убедиться, что приложение улучшенных в результате усовершенствования для повышения производительности собственной платформы .NET, следует сравнить его производительность с не - .NET Native версии приложения.</span><span class="sxs-lookup"><span data-stu-id="9a997-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="9a997-121">Дополнительные сведения см. в разделе [Общие сведения о сеансе производительности](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="9a997-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="9a997-122">Но [!INCLUDE[net_native](../../../includes/net-native-md.md)] не ограничивается только компиляцией в машинный код.</span><span class="sxs-lookup"><span data-stu-id="9a997-122">But [!INCLUDE[net_native](../../../includes/net-native-md.md)] involves more than a compilation to native code.</span></span> <span data-ttu-id="9a997-123">Он преобразует способ построения и выполнения приложений на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a997-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="9a997-124">В частности:</span><span class="sxs-lookup"><span data-stu-id="9a997-124">In particular:</span></span>  
  
-   <span data-ttu-id="9a997-125">Во время предварительной компиляции необходимые части платформы .NET Framework статически связываются с приложением.</span><span class="sxs-lookup"><span data-stu-id="9a997-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="9a997-126">Это позволяет приложению работать с библиотеками локальных приложений платформы.NET Framework, а компилятору — выполнять глобальный анализ для улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="9a997-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="9a997-127">В результате приложения постоянно запускаются быстрее даже после обновлений платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a997-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
-   <span data-ttu-id="9a997-128">[!INCLUDE[net_native](../../../includes/net-native-md.md)] Среды выполнения оптимизирована для статической предварительной компиляции и в большинстве случаев обеспечивает высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="9a997-128">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="9a997-129">В то же время она сохраняет основные функции отражения, которые разработчики считают такими полезными.</span><span class="sxs-lookup"><span data-stu-id="9a997-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="9a997-130"> использует то же сервер, что и компилятор C++, который оптимизирован для статических сценариев предварительной компиляции.</span><span class="sxs-lookup"><span data-stu-id="9a997-130"> uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="9a997-131"> способна обеспечить повышение производительности для C++ разработчиков управляемого кода, так как она использует такие же или аналогичные средства, что и C++ за кулисами, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9a997-131"> is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|<span data-ttu-id="9a997-132">C++</span><span class="sxs-lookup"><span data-stu-id="9a997-132">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="9a997-133">Библиотеки</span><span class="sxs-lookup"><span data-stu-id="9a997-133">Libraries</span></span>|<span data-ttu-id="9a997-134">Платформа.NET Framework + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="9a997-134">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="9a997-135">Win32 + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="9a997-135">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="9a997-136">Компилятор</span><span class="sxs-lookup"><span data-stu-id="9a997-136">Compiler</span></span>|<span data-ttu-id="9a997-137">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="9a997-137">UTC optimizing compiler</span></span>|<span data-ttu-id="9a997-138">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="9a997-138">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="9a997-139">Развернут</span><span class="sxs-lookup"><span data-stu-id="9a997-139">Deployed</span></span>|<span data-ttu-id="9a997-140">Готов к запуску двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="9a997-140">Ready-to-run binaries</span></span>|<span data-ttu-id="9a997-141">Готов к запуску двоичных файлов (ASM)</span><span class="sxs-lookup"><span data-stu-id="9a997-141">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="9a997-142">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="9a997-142">Runtime</span></span>|<span data-ttu-id="9a997-143">MRT.dll (минимальной среды CLR)</span><span class="sxs-lookup"><span data-stu-id="9a997-143">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="9a997-144">CRT.dll (среда выполнения C)</span><span class="sxs-lookup"><span data-stu-id="9a997-144">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="9a997-145">Для приложений, предназначенных для Windows 10, выполняется передача двоичных файлов компиляции машинного кода .NET в пакетах приложений (файлы APPX) в Магазин Windows.</span><span class="sxs-lookup"><span data-stu-id="9a997-145">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a997-146">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9a997-146">In This Section</span></span>  
 <span data-ttu-id="9a997-147">Дополнительные сведения о разработке приложений при использовании компиляции машинного кода .NET см. в следующих разделах</span><span class="sxs-lookup"><span data-stu-id="9a997-147">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
-   [<span data-ttu-id="9a997-148">Приступая к компиляции кода с помощью машинного кода .NET: пошаговое руководство разработчика</span><span class="sxs-lookup"><span data-stu-id="9a997-148">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   <span data-ttu-id="9a997-149">[Машинный код .NET и компиляция](../../../docs/framework/net-native/net-native-and-compilation.md) — как проект компилируется в машинный код .NET.</span><span class="sxs-lookup"><span data-stu-id="9a997-149">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
-   [<span data-ttu-id="9a997-150">Отражение и .NET Native</span><span class="sxs-lookup"><span data-stu-id="9a997-150">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [<span data-ttu-id="9a997-151">API-интерфейсы, основанные на отражении</span><span class="sxs-lookup"><span data-stu-id="9a997-151">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [<span data-ttu-id="9a997-152">Справочник по API отражения</span><span class="sxs-lookup"><span data-stu-id="9a997-152">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [<span data-ttu-id="9a997-153">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="9a997-153">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [<span data-ttu-id="9a997-154">Сериализация и метаданные</span><span class="sxs-lookup"><span data-stu-id="9a997-154">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [<span data-ttu-id="9a997-155">Миграция приложения для Магазина Windows в .NET Native</span><span class="sxs-lookup"><span data-stu-id="9a997-155">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [<span data-ttu-id="9a997-156">.NET Native. Устранение общих неполадок</span><span class="sxs-lookup"><span data-stu-id="9a997-156">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
