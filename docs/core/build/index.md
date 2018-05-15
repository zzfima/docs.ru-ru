---
title: Сборка .NET Core из исходного кода
description: Узнайте, как выполнять сборку .NET Core и интерфейса командной строки .NET Core из исходного кода.
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.openlocfilehash: 55a35223a4bc11156e056cceb7f86365c4906222
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="869e4-103">Сборка .NET Core из исходного кода</span><span class="sxs-lookup"><span data-stu-id="869e4-103">Build .NET Core from source</span></span>

<span data-ttu-id="869e4-104">Возможность сборки .NET Core из своего исходного кода важна по многим причинам: это упрощает перенос кода .NET Core на новые платформы, позволяет вносить в продукт дополнения и исправления, а также создавать пользовательские версии .NET.</span><span class="sxs-lookup"><span data-stu-id="869e4-104">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="869e4-105">В статье представлены рекомендации для разработчиков, которые хотят осуществлять сборку и распространение собственных версий .NET Core.</span><span class="sxs-lookup"><span data-stu-id="869e4-105">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="869e4-106">Сборка среды CLR из исходного кода</span><span class="sxs-lookup"><span data-stu-id="869e4-106">Build the CLR from source</span></span>

<span data-ttu-id="869e4-107">Исходный код .NET CoreCLR можно найти в репозитории [dotnet/coreclr](https://github.com/dotnet/coreclr/) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="869e4-107">The source code for the .NET CoreCLR can be found in the [dotnet/coreclr](https://github.com/dotnet/coreclr/) repository on GitHub.</span></span>

<span data-ttu-id="869e4-108">Для сборки сейчас необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="869e4-108">The build currently depends on the following prerequisites:</span></span>
* [<span data-ttu-id="869e4-109">Git</span><span class="sxs-lookup"><span data-stu-id="869e4-109">Git</span></span>](https://git-scm.com/)
* [<span data-ttu-id="869e4-110">CMake</span><span class="sxs-lookup"><span data-stu-id="869e4-110">CMake</span></span>](https://cmake.org/)
* [<span data-ttu-id="869e4-111">Python</span><span class="sxs-lookup"><span data-stu-id="869e4-111">Python</span></span>](https://www.python.org/)
* <span data-ttu-id="869e4-112">Компилятор C++</span><span class="sxs-lookup"><span data-stu-id="869e4-112">a C++ compiler.</span></span>

<span data-ttu-id="869e4-113">После установки необходимых компонентов вы можете выполнить сборку CLR, запустив скрипт (`build.cmd` в Windows или `build.sh` в Linux и macOS) из корня репозитория [dotnet/coreclr](https://github.com/dotnet/coreclr/).</span><span class="sxs-lookup"><span data-stu-id="869e4-113">After you've installed these prerequisites are installed, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of the [dotnet/coreclr](https://github.com/dotnet/coreclr/) repository.</span></span>

<span data-ttu-id="869e4-114">Устанавливаемые компоненты отличаются в зависимости от операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="869e4-114">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="869e4-115">Инструкции по сборке для конкретных ОС:</span><span class="sxs-lookup"><span data-stu-id="869e4-115">See the build instructions for your specific OS:</span></span>

 * [<span data-ttu-id="869e4-116">Windows</span><span class="sxs-lookup"><span data-stu-id="869e4-116">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
 * [<span data-ttu-id="869e4-117">Linux</span><span class="sxs-lookup"><span data-stu-id="869e4-117">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
 * [<span data-ttu-id="869e4-118">macOS</span><span class="sxs-lookup"><span data-stu-id="869e4-118">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
 * [<span data-ttu-id="869e4-119">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="869e4-119">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md) 
 * [<span data-ttu-id="869e4-120">NetBSD</span><span class="sxs-lookup"><span data-stu-id="869e4-120">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="869e4-121">Сборка из одной ОС под другие ОС не поддерживается (за исключением ARM, где сборка осуществляется на X64).</span><span class="sxs-lookup"><span data-stu-id="869e4-121">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="869e4-122">Сборка под конкретную платформу должна осуществляться на этой же платформе.</span><span class="sxs-lookup"><span data-stu-id="869e4-122">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="869e4-123">Сборка имеет два основных типа `buildTypes`:</span><span class="sxs-lookup"><span data-stu-id="869e4-123">The build has two main `buildTypes`:</span></span>

 * <span data-ttu-id="869e4-124">Debug — применяется по умолчанию; компилирует среду выполнения с минимальным уровнем оптимизации и использованием дополнительных проверок среды выполнения (утверждения assert).</span><span class="sxs-lookup"><span data-stu-id="869e4-124">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="869e4-125">Понижение уровня оптимизации и дополнительные проверки замедляют работу среды выполнения, но это необходимо делать для отладки.</span><span class="sxs-lookup"><span data-stu-id="869e4-125">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="869e4-126">Этот тип рекомендуется использовать со средами разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="869e4-126">This is the recommended setting for development and testing environments.</span></span>
 * <span data-ttu-id="869e4-127">Release — компилирует среду выполнения с исходным уровнем оптимизации и без использования дополнительных проверок среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="869e4-127">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="869e4-128">Это существенно ускоряет выполнение, но сборка займет немного больше времени, а отладка будет затруднена.</span><span class="sxs-lookup"><span data-stu-id="869e4-128">This will yield much faster run time performance but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="869e4-129">Чтобы выбрать этот тип сборки, передайте `release` в соответствующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="869e4-129">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="869e4-130">Кроме того, по умолчанию сборка не только создает исполняемые файлы среды выполнения, но и создает все тесты.</span><span class="sxs-lookup"><span data-stu-id="869e4-130">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="869e4-131">Тестов довольно много, и они занимают немало времени. Однако, если вы хотите просто поэкспериментировать с изменениями, использовать тесты не обязательно.</span><span class="sxs-lookup"><span data-stu-id="869e4-131">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="869e4-132">Вы можете пропустить создание тестов, добавив аргумент в сценарий сборки `skiptests`, как показано в следующем примере (замените `.\build` на `./build.sh` на компьютерах с ОС Unix):</span><span class="sxs-lookup"><span data-stu-id="869e4-132">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests 
```

<span data-ttu-id="869e4-133">В предыдущем примере показано, как выполнить сборку типа `Debug`со включенными проверками времени разработки (утверждения assert) и отключенной оптимизацией.</span><span class="sxs-lookup"><span data-stu-id="869e4-133">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="869e4-134">Чтобы создать конфигурацию Release (Выпуск), обеспечивающую максимальную скорость работы, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="869e4-134">To build the release (full speed) flavor, do the following:</span></span>

```bat 
    .\build release skiptests
```

<span data-ttu-id="869e4-135">Чтобы просмотреть другие варианты сборки, запустите build с квалификатором "-?"</span><span class="sxs-lookup"><span data-stu-id="869e4-135">You can find more build options with build by using the -?</span></span> <span data-ttu-id="869e4-136">или "-help".</span><span class="sxs-lookup"><span data-stu-id="869e4-136">or -help qualifier.</span></span>   

### <a name="using-your-build"></a><span data-ttu-id="869e4-137">Использование сборки</span><span class="sxs-lookup"><span data-stu-id="869e4-137">Using Your Build</span></span>

<span data-ttu-id="869e4-138">Сборка помещает все созданные файлы в каталог `bin` в корне репозитория.</span><span class="sxs-lookup"><span data-stu-id="869e4-138">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="869e4-139">Каталог *bin\Log* содержит созданные во время сборки файлы журнала (они особенно полезны при неудачной сборке).</span><span class="sxs-lookup"><span data-stu-id="869e4-139">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="869e4-140">Фактический результат размещается в каталоге *bin\Product\[платформа].[архитектура_процессора].[тип_сборки]*, например *bin\Product\Windows_NT.x64.Release*.</span><span class="sxs-lookup"><span data-stu-id="869e4-140">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="869e4-141">Хотя "сырой" результат сборки иногда бывает полезен, обычно вам нужны только пакеты NuGet, которые размещаются в подкаталоге `.nuget\pkg` предыдущего выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="869e4-141">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="869e4-142">Существует два основных метода использования новой среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="869e4-142">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="869e4-143">**Использование dotnet.exe и NuGet для создания приложения**.</span><span class="sxs-lookup"><span data-stu-id="869e4-143">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="869e4-144">Воспользуйтесь указаниями на странице [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) (Использование сборки), чтобы создать программу, использующую вашу новую среду выполнения, на основе только что созданных вами пакетов NuGet и интерфейса командной строки dotnet.</span><span class="sxs-lookup"><span data-stu-id="869e4-144">See [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="869e4-145">Разработчики, не работающие в среде выполнения, скорее всего будут взаимодействовать с вашей новой средой выполнения именно таким способом.</span><span class="sxs-lookup"><span data-stu-id="869e4-145">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>    

 2. <span data-ttu-id="869e4-146">**Использование corerun.exe для запуска приложения с помощью неупакованных библиотек DLL**.</span><span class="sxs-lookup"><span data-stu-id="869e4-146">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="869e4-147">Этот репозиторий также задает простое основное приложение corerun.exe, у которого НЕТ зависимостей в NuGet.</span><span class="sxs-lookup"><span data-stu-id="869e4-147">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="869e4-148">Необходимо сообщить этому приложению, где получить именно те библиотеки DLL, которые вы используете. Вам нужно будет собрать эти библиотеки вместе вручную.</span><span class="sxs-lookup"><span data-stu-id="869e4-148">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="869e4-149">Этот метод используется во всех тестах в репозитории [dotnet/coreclr](https://github.com/dotnet/coreclr). Его можно использовать для быстрого локального проведения цикла "правка — компиляция — отладка", например при предварительном модульном тестировании.</span><span class="sxs-lookup"><span data-stu-id="869e4-149">This technique is used by all the tests in the [dotnet/coreclr](https://github.com/dotnet/coreclr) repo, and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="869e4-150">Подробнее об использовании этого метода см. в статье [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) (Запуск приложений .NET Core с помощью CoreRun.exe).</span><span class="sxs-lookup"><span data-stu-id="869e4-150">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="869e4-151">Сборка интерфейса командной строки из исходного кода</span><span class="sxs-lookup"><span data-stu-id="869e4-151">Build the CLI from source</span></span>

<span data-ttu-id="869e4-152">Исходный код для .NET Core CLI находится в репозитории [dotnet/cli](https://github.com/dotnet/cli/) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="869e4-152">The source code for the .NET Core CLI can be found in the [dotnet/cli](https://github.com/dotnet/cli/) repository on GitHub.</span></span>

<span data-ttu-id="869e4-153">Для сборки CLI-интерфейса .NET Core на компьютеры должны быть установлены следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="869e4-153">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

* <span data-ttu-id="869e4-154">Windows и Linux:</span><span class="sxs-lookup"><span data-stu-id="869e4-154">Windows & Linux:</span></span>
    - <span data-ttu-id="869e4-155">git в каталоге переменной PATH</span><span class="sxs-lookup"><span data-stu-id="869e4-155">git on the PATH</span></span>
* <span data-ttu-id="869e4-156">macOS:</span><span class="sxs-lookup"><span data-stu-id="869e4-156">macOS:</span></span>
    - <span data-ttu-id="869e4-157">git в каталоге переменной PATH</span><span class="sxs-lookup"><span data-stu-id="869e4-157">git on the PATH</span></span>
    - <span data-ttu-id="869e4-158">Xcode</span><span class="sxs-lookup"><span data-stu-id="869e4-158">Xcode</span></span>
    - <span data-ttu-id="869e4-159">Openssl</span><span class="sxs-lookup"><span data-stu-id="869e4-159">OpenSSL</span></span>

<span data-ttu-id="869e4-160">Чтобы выполнить сборку, запустите `build.cmd` в Windows или `build.sh` в Linux и macOS из корня.</span><span class="sxs-lookup"><span data-stu-id="869e4-160">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="869e4-161">Если вы не хотите выполнять тесты, используйте `build.cmd /t:Compile` или `./build.sh /t:Compile`.</span><span class="sxs-lookup"><span data-stu-id="869e4-161">If you don't want to execute tests, run `build.cmd /t:Compile` or `./build.sh /t:Compile`.</span></span> <span data-ttu-id="869e4-162">Для сборки CLI в macOS Sierra задайте значение переменной среды DOTNET_RUNTIME_ID, выполнив `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="869e4-162">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="869e4-163">Использование сборки</span><span class="sxs-lookup"><span data-stu-id="869e4-163">Using your build</span></span>

<span data-ttu-id="869e4-164">Чтобы испытать созданный CLI-интерфейс, используйте исполняемый файл `dotnet` из *artifacts/{os}-{arch}/stage2*.</span><span class="sxs-lookup"><span data-stu-id="869e4-164">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="869e4-165">Если вы хотите использовать результат сборки при вызове `dotnet` из текущей консоли, вы можете также добавить *artifacts/{os}-{arch}/stage2* в переменную PATH.</span><span class="sxs-lookup"><span data-stu-id="869e4-165">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="869e4-166">См. также</span><span class="sxs-lookup"><span data-stu-id="869e4-166">See also</span></span>

* [<span data-ttu-id="869e4-167">Общеязыковая среда выполнения .NET Core (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="869e4-167">.NET Core Common Language Runtime (CoreCLR)</span></span>](https://github.com/dotnet/coreclr/blob/master/README.md)
* [<span data-ttu-id="869e4-168">Руководство разработчика по интерфейсу командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="869e4-168">.NET Core CLI Developer Guide</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
* [<span data-ttu-id="869e4-169">Упаковка дистрибутивов .NET Core</span><span class="sxs-lookup"><span data-stu-id="869e4-169">.NET Core distribution packaging</span></span>](./distribution-packaging.md)
