---
title: Необходимые компоненты для .NET Core в Windows
description: Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows.
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: bbf54c8d215783656830f0fa035708be82a7c39c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482614"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="8926d-103">Необходимые компоненты для .NET Core в Windows</span><span class="sxs-lookup"><span data-stu-id="8926d-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="8926d-104">В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="8926d-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="8926d-105">Поддерживаемые версии ОС, а также перечисленные ниже зависимости относятся к трем способам разработки приложений .NET Core в Windows:</span><span class="sxs-lookup"><span data-stu-id="8926d-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="8926d-106">командная строка;</span><span class="sxs-lookup"><span data-stu-id="8926d-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="8926d-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8926d-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="8926d-108">Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8926d-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="8926d-109">Версии Windows, поддерживаемые .NET Core</span><span class="sxs-lookup"><span data-stu-id="8926d-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="8926d-110">Платформа .NET Core поддерживается в следующих версиях:</span><span class="sxs-lookup"><span data-stu-id="8926d-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="8926d-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="8926d-111">Windows 7 SP1</span></span>
* <span data-ttu-id="8926d-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8926d-112">Windows 8.1</span></span>
* <span data-ttu-id="8926d-113">Windows 10, юбилейное обновление (версия 1607) или более поздние версии</span><span class="sxs-lookup"><span data-stu-id="8926d-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="8926d-114">Windows Server 2008 R2 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)</span><span class="sxs-lookup"><span data-stu-id="8926d-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="8926d-115">Windows Server 2012 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)</span><span class="sxs-lookup"><span data-stu-id="8926d-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="8926d-116">Windows Server 2012 R2 (полный сервер или основные серверные компоненты)</span><span class="sxs-lookup"><span data-stu-id="8926d-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="8926d-117">Windows Server 2016 или более поздних версий (полный вариант сервера, основные серверные компоненты или сервер Nano)</span><span class="sxs-lookup"><span data-stu-id="8926d-117">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="8926d-118">В следующих статьях содержится полный список операционных систем с указанием версий, в которых поддерживается .NET Core:</span><span class="sxs-lookup"><span data-stu-id="8926d-118">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* <span data-ttu-id="8926d-119">[.NET Core 2.1 - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1 — поддерживаемые версии ОС)</span><span class="sxs-lookup"><span data-stu-id="8926d-119">[.NET Core 2.1 - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)</span></span>
* <span data-ttu-id="8926d-120">[.NET Core 2.0 - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.0 — поддерживаемые версии ОС)</span><span class="sxs-lookup"><span data-stu-id="8926d-120">[.NET Core 2.0 - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)</span></span>
* <span data-ttu-id="8926d-121">[.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x — поддерживаемые версии ОС)</span><span class="sxs-lookup"><span data-stu-id="8926d-121">[.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="8926d-122">Зависимости .NET Core</span><span class="sxs-lookup"><span data-stu-id="8926d-122">.NET Core dependencies</span></span>

<span data-ttu-id="8926d-123">Для работы .NET Core 1.1 и более ранних версий в версиях Windows, более ранних, чем Windows 10 и Windows Server 2016, требуется распространяемый пакет Visual C++.</span><span class="sxs-lookup"><span data-stu-id="8926d-123">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="8926d-124">Эту зависимость автоматически устанавливает установщик .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8926d-124">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="8926d-125">[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685) необходимо установить вручную в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="8926d-125">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="8926d-126">при установке .NET Core с помощью [скрипта установщика](./tools/dotnet-install-script.md);</span><span class="sxs-lookup"><span data-stu-id="8926d-126">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="8926d-127">при развертывании автономного приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8926d-127">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="8926d-128">сборка продукта из исходного кода;</span><span class="sxs-lookup"><span data-stu-id="8926d-128">Building the product from source.</span></span>
* <span data-ttu-id="8926d-129">установка .NET Core из файла *.zip*,</span><span class="sxs-lookup"><span data-stu-id="8926d-129">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="8926d-130">включая серверы сборки/непрерывной интеграции/непрерывного развертывания.</span><span class="sxs-lookup"><span data-stu-id="8926d-130">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="8926d-131">**Для Windows 8.1 и более ранних версий или Windows Server 2012 R2 и более ранних версий:**</span><span class="sxs-lookup"><span data-stu-id="8926d-131">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="8926d-132">Убедитесь, что установленная версия Windows актуальна и содержит обновление [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), которое можно установить через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="8926d-132">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="8926d-133">Если это обновление не установлено, при запуске приложения .NET Core появится следующая ошибка: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="8926d-133">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="8926d-134">**Для Windows 7 или Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="8926d-134">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="8926d-135">Убедитесь, что помимо обновления KB2999226 также установлено обновление [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="8926d-135">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="8926d-136">Если это обновление не установлено, при запуске приложения .NET Core появится примерно следующая ошибка: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="8926d-136">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="8926d-137">Необходимые компоненты для Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8926d-137">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="8926d-138">Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор.</span><span class="sxs-lookup"><span data-stu-id="8926d-138">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="8926d-139">[Visual Studio 2017](#visual-studio-2017) предоставляет интегрированную среду разработки для приложений .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="8926d-139">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="8926d-140">Дополнительные сведения об обновлениях Visual Studio 2017 см. в [заметках о выпуске](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="8926d-140">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8926d-141">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8926d-141">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="8926d-142">Для разработки приложений .NET Core 2.1 в Visual Studio 2017 выполните указанные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="8926d-142">To develop .NET Core 2.1 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="8926d-143">[Скачайте и установите Visual Studio 2017 версии 15.7.0 или более поздней версии](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).</span><span class="sxs-lookup"><span data-stu-id="8926d-143">[Download and install Visual Studio 2017 version 15.7.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-15-8-workloads.jpg)

<span data-ttu-id="8926d-145">После установки набора инструментов **Кроссплатформенная разработка .NET Core** среда Visual Studio 2017 15.7 по умолчанию использует пакет SDK для .NET Core версии 2.0, а среда Visual Studio 2017 15.8 — пакет SDK для .NET Core версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="8926d-145">After the **.NET Core cross-platform development** toolset is installed, by default, Visual Studio 2017 15.7 uses .NET Core 2.0 SDK and Visual Studio 2017 15.8 uses 2.1 SDK.</span></span>

 2. <span data-ttu-id="8926d-146">Если вы используете среду Visual Studio 2017 версии 15.7, установите [пакет SDK для .NET Core 2.1](https://www.microsoft.com/net/download/core) или обновите среду до Visual Studio 2017 версии 15.8.</span><span class="sxs-lookup"><span data-stu-id="8926d-146">If you're using Visual Studio 2017 15.7, install the [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) or upgrade to Visual Studio 2017 15.8.</span></span>

 3. <span data-ttu-id="8926d-147">Перенацельте существующие или новые проекты .NET Core на .NET Core 2.1, выполнив приведенные ниже инструкции:</span><span class="sxs-lookup"><span data-stu-id="8926d-147">Retarget existing or new .NET Core projects to .NET Core 2.1 using the following instructions:</span></span>
    * <span data-ttu-id="8926d-148">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8926d-148">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="8926d-149">В меню **Целевая платформа** выберите значение **.NET Core 2.1**.</span><span class="sxs-lookup"><span data-stu-id="8926d-149">In the **Target framework** selection menu, set the value to **.NET Core 2.1**.</span></span>

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.0" в меню целевой платформы](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="8926d-151">Настроив Visual Studio для работы с пакетом SDK для .NET Core 2.1, вы можете выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8926d-151">Once you have Visual Studio configured with .NET Core 2.1 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="8926d-152">открытие, сборка и запуск существующих проектов .NET Core 1.x и 2.x;</span><span class="sxs-lookup"><span data-stu-id="8926d-152">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="8926d-153">перенацеливание проектов .NET Core 1.x и 2.0 на .NET Core 2.1, сборка и запуск.</span><span class="sxs-lookup"><span data-stu-id="8926d-153">Retarget .NET Core 1.x and 2.0 projects to .NET Core 2.1, build, and run.</span></span>
* <span data-ttu-id="8926d-154">создание проектов .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="8926d-154">Create new .NET Core 2.1 projects.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8926d-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8926d-155">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="8926d-156">Для разработки приложений .NET Core 2.0 в Visual Studio 2017 выполните указанные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="8926d-156">To develop .NET Core 2.0 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="8926d-157">[Скачайте и установите Visual Studio 2017 версии 15.3.0 или более поздней](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).</span><span class="sxs-lookup"><span data-stu-id="8926d-157">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="8926d-159">После установки набора инструментов **Кроссплатформенная разработка .NET Core** среда Visual Studio 2017 по умолчанию использует .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="8926d-159">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="8926d-160">Чтобы в среде Visual Studio 2017 поддерживалась платформа .NET Core 2.0, установите пакет SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="8926d-160">Install the .NET Core 2.0 SDK to get .NET Core 2.0 support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="8926d-161">Установите [пакет SDK для .NET Core 2.0](https://www.microsoft.com/net/download/dotnet-core/2.0).</span><span class="sxs-lookup"><span data-stu-id="8926d-161">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).</span></span>
 3. <span data-ttu-id="8926d-162">Перенацельте существующие или новые проекты .NET Core 1.x на .NET Core 2.0, выполнив приведенные ниже инструкции:</span><span class="sxs-lookup"><span data-stu-id="8926d-162">Retarget existing or new .NET Core 1.x projects to .NET Core 2.0 using the following instructions:</span></span>
    * <span data-ttu-id="8926d-163">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8926d-163">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="8926d-164">В меню **Целевая платформа** выберите значение **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="8926d-164">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.0" в меню целевой платформы](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="8926d-166">После установки пакета SDK для .NET Core 2.0 среда Visual Studio 2017 по умолчанию использует пакет SDK для .NET Core 2.0 и поддерживает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8926d-166">Once the .NET Core 2.0 SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.0 by default, and supports the following actions:</span></span>

* <span data-ttu-id="8926d-167">открытие, сборка и запуск существующих проектов .NET Core 1.x;</span><span class="sxs-lookup"><span data-stu-id="8926d-167">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="8926d-168">перенацеливание проектов .NET Core 1.x на .NET Core 2.0, сборка и запуск;</span><span class="sxs-lookup"><span data-stu-id="8926d-168">Retarget .NET Core 1.x projects to .NET Core 2.0, build, and run.</span></span>
* <span data-ttu-id="8926d-169">создание проектов .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="8926d-169">Create new .NET Core 2.0 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8926d-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8926d-170">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="8926d-171">Для разработки приложений .NET Core 1.x в Visual Studio [скачайте и установите Visual Studio 2017](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).</span><span class="sxs-lookup"><span data-stu-id="8926d-171">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="8926d-173">Для разработки приложений .NET Core 1.x можно использовать среду Visual Studio 2015, но делать этого не рекомендуется по указанным ниже причинам.</span><span class="sxs-lookup"><span data-stu-id="8926d-173">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="8926d-174">Средства .NET Core доступны в виде предварительной версии, которая не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8926d-174">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="8926d-175">Проекты основаны на файлах project.json, которые являются нерекомендуемыми.</span><span class="sxs-lookup"><span data-stu-id="8926d-175">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="8926d-176">Дополнительные сведения об изменениях формата проектов см. в этом [обзоре](./tools/cli-msbuild-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="8926d-176">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="8926d-177">Чтобы проверить установленную версию Visual Studio 2017, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8926d-177">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="8926d-178">В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="8926d-178">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="8926d-179">В диалоговом окне **О программе Microsoft Visual Studio** проверьте номер версии.</span><span class="sxs-lookup"><span data-stu-id="8926d-179">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="8926d-180">Для приложений .NET Core 2.2, предварительная версия 1 — Visual Studio 2017 версии 15.9 (предварительная версия) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8926d-180">For .NET Core 2.2 Preview 1 apps, Visual Studio 2017 version 15.9 (currently in Preview) or higher.</span></span>
>   * <span data-ttu-id="8926d-181">Для приложений .NET Core 2.1 — Visual Studio 2017 версии 15.7 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8926d-181">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="8926d-182">Для приложений .NET Core 2.0 — Visual Studio 2017 версии 15.3 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="8926d-182">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="8926d-183">Для приложений .NET Core 1.x — Visual Studio 2017 версии 15.0 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="8926d-183">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
