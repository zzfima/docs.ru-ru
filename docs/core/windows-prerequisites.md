---
title: Необходимые компоненты для .NET Core в Windows
description: Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows.
author: JRAlexander
ms.author: johalex
ms.date: 04/24/2018
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: ac898ea87c0247581154eb7de65e8cbe6ea6ba15
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="8dfe3-103">Необходимые компоненты для .NET Core в Windows</span><span class="sxs-lookup"><span data-stu-id="8dfe3-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="8dfe3-104">В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="8dfe3-105">Поддерживаемые версии ОС, а также перечисленные ниже зависимости относятся к трем способам разработки приложений .NET Core в Windows:</span><span class="sxs-lookup"><span data-stu-id="8dfe3-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="8dfe3-106">командная строка;</span><span class="sxs-lookup"><span data-stu-id="8dfe3-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="8dfe3-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8dfe3-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="8dfe3-108">Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="8dfe3-109">Версии Windows, поддерживаемые .NET Core</span><span class="sxs-lookup"><span data-stu-id="8dfe3-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="8dfe3-110">Платформа .NET Core поддерживается в следующих версиях:</span><span class="sxs-lookup"><span data-stu-id="8dfe3-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="8dfe3-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="8dfe3-111">Windows 7 SP1</span></span>
* <span data-ttu-id="8dfe3-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8dfe3-112">Windows 8.1</span></span>
* <span data-ttu-id="8dfe3-113">Windows 10, юбилейное обновление (версия 1607) или более поздние версии</span><span class="sxs-lookup"><span data-stu-id="8dfe3-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="8dfe3-114">Windows Server 2008 R2 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)</span><span class="sxs-lookup"><span data-stu-id="8dfe3-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="8dfe3-115">Windows Server 2012 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)</span><span class="sxs-lookup"><span data-stu-id="8dfe3-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="8dfe3-116">Windows Server 2012 R2 (полный сервер или основные серверные компоненты)</span><span class="sxs-lookup"><span data-stu-id="8dfe3-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="8dfe3-117">Windows Server 2016 (полный сервер, основные серверные компоненты или сервер Nano)</span><span class="sxs-lookup"><span data-stu-id="8dfe3-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="8dfe3-118">Полный список операционных систем, поддерживаемых .NET Core 2.x, см. в статье [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="8dfe3-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="8dfe3-119">Полный список операционных систем, поддерживаемых .NET Core 1.x, см. в статье [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="8dfe3-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="8dfe3-120">Зависимости .NET Core</span><span class="sxs-lookup"><span data-stu-id="8dfe3-120">.NET Core dependencies</span></span>

<span data-ttu-id="8dfe3-121">Для работы .NET Core 1.1 и более ранних версий в версиях Windows, более ранних, чем Windows 10 и Windows Server 2016, требуется распространяемый пакет Visual C++.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-121">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="8dfe3-122">Эту зависимость автоматически устанавливает установщик .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="8dfe3-123">[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685) необходимо установить вручную в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="8dfe3-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="8dfe3-124">при установке .NET Core с помощью [скрипта установщика](./tools/dotnet-install-script.md);</span><span class="sxs-lookup"><span data-stu-id="8dfe3-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="8dfe3-125">при развертывании автономного приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-125">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="8dfe3-126">сборка продукта из исходного кода;</span><span class="sxs-lookup"><span data-stu-id="8dfe3-126">Building the product from source.</span></span>
* <span data-ttu-id="8dfe3-127">установка .NET Core из файла *.zip*,</span><span class="sxs-lookup"><span data-stu-id="8dfe3-127">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="8dfe3-128">включая серверы сборки/непрерывной интеграции/непрерывного развертывания.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-128">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="8dfe3-129">*Для Windows 8.1 и более ранних версий или Windows Server 2012 R2 и более ранних версий.* Убедитесь, что установка Windows находится в актуальном состоянии и содержит обновление [ KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), которое можно установить из Центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-129">*For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:* Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows) which can be installed through Windows Update.</span></span> <span data-ttu-id="8dfe3-130">Если это обновление не установлено, при запуске приложения .NET Core появится следующая ошибка: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-130">If you don't have this update installed, you'll see an error when you launch a .NET Core application like the following: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="8dfe3-131">Необходимые компоненты для Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8dfe3-131">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="8dfe3-132">Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-132">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="8dfe3-133">[Visual Studio 2017](#visual-studio-2017) предоставляет интегрированную среду разработки для приложений .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-133">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="8dfe3-134">Дополнительные сведения об обновлениях Visual Studio 2017 см. в [заметках о выпуске](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="8dfe3-134">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="8dfe3-135">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="8dfe3-135">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="8dfe3-136">Для разработки приложений .NET Core 2.x в Visual Studio 2017 выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-136">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="8dfe3-137">[Скачайте и установите Visual Studio 2017 версии 15.3.0 или более поздней](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).</span><span class="sxs-lookup"><span data-stu-id="8dfe3-137">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="8dfe3-139">После установки набора инструментов **Кроссплатформенная разработка .NET Core** среда Visual Studio 2017 по умолчанию использует .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-139">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="8dfe3-140">Чтобы в среде Visual Studio 2017 поддерживалась платформа .NET Core 2.x, установите пакет SDK для .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-140">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="8dfe3-141">Установите [пакет SDK для .NET Core 2.x](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="8dfe3-141">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="8dfe3-142">Перенацельте существующие или новые проекты .NET Core 1.x на .NET Core 2.x, выполнив приведенные ниже инструкции.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-142">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="8dfe3-143">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-143">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="8dfe3-144">В меню **Целевая платформа** выберите значение **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-144">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.0" в меню целевой платформы](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="8dfe3-146">После установки пакета SDK для .NET Core 2.x среда Visual Studio 2017 по умолчанию использует пакет SDK для .NET Core 2.x и поддерживает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8dfe3-146">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

* <span data-ttu-id="8dfe3-147">открытие, сборка и запуск существующих проектов .NET Core 1.x;</span><span class="sxs-lookup"><span data-stu-id="8dfe3-147">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="8dfe3-148">перенацеливание проектов .NET Core 1.x на .NET Core 2.x, сборка и запуск;</span><span class="sxs-lookup"><span data-stu-id="8dfe3-148">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
* <span data-ttu-id="8dfe3-149">создание проектов .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-149">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8dfe3-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8dfe3-150">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="8dfe3-151">Для разработки приложений .NET Core 1.x в Visual Studio [скачайте и установите Visual Studio 2017 RTM (версия 15.0.26228.4) или более позднюю версию](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).</span><span class="sxs-lookup"><span data-stu-id="8dfe3-151">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="8dfe3-153">Для разработки приложений .NET Core 1.x можно использовать среду Visual Studio 2015, но делать этого не рекомендуется по указанным ниже причинам.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-153">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="8dfe3-154">Средства .NET Core доступны в виде предварительной версии, которая не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-154">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="8dfe3-155">Проекты основаны на файлах project.json, которые являются нерекомендуемыми.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-155">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="8dfe3-156">Дополнительные сведения об изменениях формата проектов см. в этом [обзоре](./tools/cli-msbuild-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="8dfe3-156">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

> [!TIP]
> <span data-ttu-id="8dfe3-157">Чтобы проверить установленную версию Visual Studio 2017, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-157">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="8dfe3-158">В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-158">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="8dfe3-159">В диалоговом окне **О программе Microsoft Visual Studio** проверьте номер версии.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-159">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="8dfe3-160">Для приложений .NET Core 2.1, предварительная версия 1 — Visual Studio 2017 версии 15.6, предварительная версия 6 или более поздняя.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-160">For .NET Core 2.1 Preview 1 apps, Visual Studio 2017 version 15.6 Preview 6 or higher.</span></span>
>   * <span data-ttu-id="8dfe3-161">Для приложений .NET Core 2.0 — Visual Studio 2017 версии 15.3 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-161">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="8dfe3-162">Для приложений .NET Core 1.x — Visual Studio 2017 версии 15.0 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-162">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
