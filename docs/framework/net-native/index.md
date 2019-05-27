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
ms.openlocfilehash: 28b09bf07d831747be0006ffe1f1d8c5ac5171ce
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052646"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="4ca5f-102">Компиляция приложений с помощью машинного кода .NET</span><span class="sxs-lookup"><span data-stu-id="4ca5f-102">Compiling Apps with .NET Native</span></span>
<span data-ttu-id="4ca5f-103">.NET native — предварительной компиляции технология для создания и развертывания приложений Windows, которая входит в состав Visual Studio 2015 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="4ca5f-104">Она автоматически компилирует окончательные версии приложений, написанных в форме управляемого кода (C# или Visual Basic) и предназначенных для .NET Framework и Windows 10, в машинный код.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="4ca5f-105">Как правило приложения, предназначенные для платформа.NET Framework компилируются в промежуточный язык (IL).</span><span class="sxs-lookup"><span data-stu-id="4ca5f-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="4ca5f-106">Во время выполнения JIT-компилятор преобразует инструкции IL в машинный код.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="4ca5f-107">В противоположность этому .NET Native компилирует приложения Windows непосредственно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="4ca5f-108">Для разработчиков это означает:</span><span class="sxs-lookup"><span data-stu-id="4ca5f-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="4ca5f-109">Ваши приложения имеют производительность машинного кода.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="4ca5f-110">Как правило производительность будет значительно выше, для кода, сначала компилируются на языке IL и затем компилируются в машинный код JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="4ca5f-111">Можно продолжить программировать в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="4ca5f-112">Можно продолжать использовать преимущества ресурсов платформы .NET Framework, включая библиотеки классов, сбор мусора, автоматическое управление памяти и обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="4ca5f-113">Для пользователей приложений .NET Native обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="4ca5f-113">For users of your apps, .NET Native offers these advantages:</span></span>  
  
- <span data-ttu-id="4ca5f-114">Сократить время выполнения для большинства приложений и сценарии.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="4ca5f-115">Сократить время запуска для большинства приложений и сценарии.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="4ca5f-116">Низкая стоимость развертывания и обновления.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="4ca5f-117">Оптимизированное использование памяти приложением.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="4ca5f-118">Для большинства приложений и сценарии машинного кода .NET предлагает значительно сократить время запуска и высокую производительность по сравнению с приложения компиляции IL или образ NGEN.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="4ca5f-119">Тем не менее результаты могут различаться.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-119">However, your results may vary.</span></span> <span data-ttu-id="4ca5f-120">Чтобы убедиться, что приложение применяющих улучшенных возможностей .NET Native, следует сравнить ее производительность с не - машинного кода .NET версии приложения.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="4ca5f-121">Дополнительные сведения см. в разделе [Общие сведения о сеансе производительности](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="4ca5f-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="4ca5f-122">Но .NET Native включает в себя больше, чем компиляция в машинный код.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="4ca5f-123">Он преобразует способ построения и выполнения приложений на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="4ca5f-124">В частности:</span><span class="sxs-lookup"><span data-stu-id="4ca5f-124">In particular:</span></span>  
  
- <span data-ttu-id="4ca5f-125">Во время предварительной компиляции необходимые части платформы .NET Framework статически связываются с приложением.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="4ca5f-126">Это позволяет приложению работать с библиотеками локальных приложений платформы.NET Framework, а компилятору — выполнять глобальный анализ для улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="4ca5f-127">В результате приложения постоянно запускаются быстрее даже после обновлений платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="4ca5f-128">Среда выполнения .NET Native оптимизирована для статической предварительной компиляции и в подавляющем большинстве случаев предлагает более высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="4ca5f-129">В то же время она сохраняет основные функции отражения, которые разработчики считают такими полезными.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- <span data-ttu-id="4ca5f-130">.NET native использует ту же серверную как C++ компилятор, который оптимизирован для статических сценариев предварительной компиляции.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 <span data-ttu-id="4ca5f-131">.NET native способна обеспечить повышение производительности C++ управляемому кода разработчикам, так как оно использует одинаковые или похожие инструменты как C++ за кулисами, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||<span data-ttu-id="4ca5f-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="4ca5f-132">.NET Native</span></span>|<span data-ttu-id="4ca5f-133">C++</span><span class="sxs-lookup"><span data-stu-id="4ca5f-133">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="4ca5f-134">Библиотеки</span><span class="sxs-lookup"><span data-stu-id="4ca5f-134">Libraries</span></span>|<span data-ttu-id="4ca5f-135">Платформа.NET Framework + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="4ca5f-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="4ca5f-136">Win32 + среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="4ca5f-136">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="4ca5f-137">Компилятор</span><span class="sxs-lookup"><span data-stu-id="4ca5f-137">Compiler</span></span>|<span data-ttu-id="4ca5f-138">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="4ca5f-138">UTC optimizing compiler</span></span>|<span data-ttu-id="4ca5f-139">Оптимизирующий компилятор UTC</span><span class="sxs-lookup"><span data-stu-id="4ca5f-139">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="4ca5f-140">Развернут</span><span class="sxs-lookup"><span data-stu-id="4ca5f-140">Deployed</span></span>|<span data-ttu-id="4ca5f-141">Готов к запуску двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="4ca5f-141">Ready-to-run binaries</span></span>|<span data-ttu-id="4ca5f-142">Готов к запуску двоичных файлов (ASM)</span><span class="sxs-lookup"><span data-stu-id="4ca5f-142">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="4ca5f-143">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4ca5f-143">Runtime</span></span>|<span data-ttu-id="4ca5f-144">MRT.dll (минимальной среды CLR)</span><span class="sxs-lookup"><span data-stu-id="4ca5f-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="4ca5f-145">CRT.dll (среда выполнения C)</span><span class="sxs-lookup"><span data-stu-id="4ca5f-145">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="4ca5f-146">Для приложений, предназначенных для Windows 10, выполняется передача двоичных файлов компиляции машинного кода .NET в пакетах приложений (файлы APPX) в Магазин Windows.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ca5f-147">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4ca5f-147">In This Section</span></span>  
 <span data-ttu-id="4ca5f-148">Дополнительные сведения о разработке приложений при использовании компиляции машинного кода .NET см. в следующих разделах</span><span class="sxs-lookup"><span data-stu-id="4ca5f-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="4ca5f-149">Начало работы с компиляции машинного кода .NET. Пошаговое руководство для разработчиков качества</span><span class="sxs-lookup"><span data-stu-id="4ca5f-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="4ca5f-150">[.NET native и компиляция:](../../../docs/framework/net-native/net-native-and-compilation.md) Как .NET проект компилируется в машинный код.</span><span class="sxs-lookup"><span data-stu-id="4ca5f-150">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- [<span data-ttu-id="4ca5f-151">Отражение и .NET Native</span><span class="sxs-lookup"><span data-stu-id="4ca5f-151">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [<span data-ttu-id="4ca5f-152">API-интерфейсы, основанные на отражении</span><span class="sxs-lookup"><span data-stu-id="4ca5f-152">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [<span data-ttu-id="4ca5f-153">Справочник по API отражения</span><span class="sxs-lookup"><span data-stu-id="4ca5f-153">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="4ca5f-154">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="4ca5f-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [<span data-ttu-id="4ca5f-155">Сериализация и метаданные</span><span class="sxs-lookup"><span data-stu-id="4ca5f-155">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [<span data-ttu-id="4ca5f-156">Миграция приложения для Магазина Windows в .NET Native</span><span class="sxs-lookup"><span data-stu-id="4ca5f-156">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [<span data-ttu-id="4ca5f-157">.NET Native. Устранение общих неполадок</span><span class="sxs-lookup"><span data-stu-id="4ca5f-157">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
