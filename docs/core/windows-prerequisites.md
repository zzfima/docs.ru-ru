---
title: Необходимые компоненты для .NET Core в Windows
description: Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771952"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="546f4-103">Необходимые компоненты для .NET Core в Windows</span><span class="sxs-lookup"><span data-stu-id="546f4-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="546f4-104">В этой статье описываются поддерживаемые версии ОС, необходимые для запуска приложений .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="546f4-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="546f4-105">Поддерживаемые версии ОС, а также перечисленные ниже зависимости относятся к трем способам разработки приложений .NET Core в Windows:</span><span class="sxs-lookup"><span data-stu-id="546f4-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="546f4-106">командная строка;</span><span class="sxs-lookup"><span data-stu-id="546f4-106">Command line</span></span>](./tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="546f4-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="546f4-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [<span data-ttu-id="546f4-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="546f4-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="546f4-109">Кроме того, если вы разрабатываете приложение в Windows с помощью Visual Studio, ознакомьтесь с минимальными поддерживаемыми версиями для разработки .NET Core в разделе [Необходимые компоненты для разработки приложений .NET Core с помощью Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="546f4-109">Also, if you're developing on Windows using Visual Studio, the [Prerequisites to develop .NET Core apps with Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="546f4-110">Поддерживаемые операционные системы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="546f4-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="546f4-111">В следующих статьях содержится полный список операционных систем с указанием версий, в которых поддерживается .NET Core:</span><span class="sxs-lookup"><span data-stu-id="546f4-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="546f4-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="546f4-112">.NET Core 3.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="546f4-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="546f4-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="546f4-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="546f4-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

<span data-ttu-id="546f4-115">Дополнительные сведения и ссылки для скачивания см. на следующих страницах: [на странице скачиваемых файлов .NET](https://dotnet.microsoft.com/download) для загрузки новой версии и [на странице архива загрузок .NET](https://dotnet.microsoft.com/download/archives#dotnet-core) для более старых версий.</span><span class="sxs-lookup"><span data-stu-id="546f4-115">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="546f4-116">Зависимости .NET Core</span><span class="sxs-lookup"><span data-stu-id="546f4-116">.NET Core dependencies</span></span>

<span data-ttu-id="546f4-117">[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685) необходимо установить вручную в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="546f4-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="546f4-118">при установке .NET Core с помощью [скрипта установщика](./tools/dotnet-install-script.md);</span><span class="sxs-lookup"><span data-stu-id="546f4-118">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="546f4-119">при развертывании автономного приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="546f4-119">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="546f4-120">сборка продукта из исходного кода;</span><span class="sxs-lookup"><span data-stu-id="546f4-120">Building the product from source.</span></span>
* <span data-ttu-id="546f4-121">установка .NET Core из файла *.zip*,</span><span class="sxs-lookup"><span data-stu-id="546f4-121">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="546f4-122">включая серверы сборки/непрерывной интеграции/непрерывного развертывания.</span><span class="sxs-lookup"><span data-stu-id="546f4-122">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="546f4-123">**Для Windows 8.1 и более ранних версий или Windows Server 2012 R2 и более ранних версий:**</span><span class="sxs-lookup"><span data-stu-id="546f4-123">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="546f4-124">Убедитесь, что установленная версия Windows актуальна и содержит обновление [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), которое можно установить через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="546f4-124">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="546f4-125">Если это обновление не установлено, при запуске приложения .NET Core появится следующая ошибка: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="546f4-125">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="546f4-126">**Для Windows 7 или Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="546f4-126">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="546f4-127">Убедитесь, что помимо обновления KB2999226 также установлено обновление [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="546f4-127">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="546f4-128">Если это обновление не установлено, при запуске приложения .NET Core появится примерно следующая ошибка: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="546f4-128">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a><span data-ttu-id="546f4-129">Необходимые компоненты для разработки приложений .NET Core с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="546f4-129">Prerequisites to develop .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="546f4-130">Хотя вы можете использовать любой редактор для разработки приложений .NET Core с помощью SDK для .NET Core, Visual Studio 2017 и более поздние версии предоставляют интегрированную среду разработки для приложений .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="546f4-130">Even though you can use any editor to develop .NET Core applications using the .NET Core SDK, Visual Studio 2017 and later versions provide an integrated development environment for .NET Core apps on Windows.</span></span>

<a name="vs-mapping"></a>

<span data-ttu-id="546f4-131">Для каждой версии .NET Core имеется минимальная необходимая версия Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="546f4-131">Each .NET Core version has a minimum version of Visual Studio required.</span></span> <span data-ttu-id="546f4-132">Чтобы проверить установленную версию Visual Studio, выполните указанные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="546f4-132">To verify your Visual Studio version:</span></span>

* <span data-ttu-id="546f4-133">В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="546f4-133">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
* <span data-ttu-id="546f4-134">В диалоговом окне **О программе Microsoft Visual Studio** проверьте номер версии.</span><span class="sxs-lookup"><span data-stu-id="546f4-134">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>

<span data-ttu-id="546f4-135">В таблице ниже перечислены минимальные версии для каждого пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="546f4-135">The following table lists the minimum version for each SDK:</span></span>

| <span data-ttu-id="546f4-136">Версия пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="546f4-136">.NET Core SDK version</span></span> | <span data-ttu-id="546f4-137">Версия Visual Studio</span><span class="sxs-lookup"><span data-stu-id="546f4-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="546f4-138">3.0</span><span class="sxs-lookup"><span data-stu-id="546f4-138">3.0</span></span>                   | <span data-ttu-id="546f4-139">Visual Studio 2019 версии 16.3 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="546f4-139">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="546f4-140">2.2</span><span class="sxs-lookup"><span data-stu-id="546f4-140">2.2</span></span>                   | <span data-ttu-id="546f4-141">Visual Studio 2017 версии 15.9 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="546f4-141">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="546f4-142">2.1</span><span class="sxs-lookup"><span data-stu-id="546f4-142">2.1</span></span>                   | <span data-ttu-id="546f4-143">Visual Studio 2017 версии 15.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="546f4-143">Visual Studio 2017 version 15.7 or higher.</span></span> |
| <span data-ttu-id="546f4-144">1.x</span><span class="sxs-lookup"><span data-stu-id="546f4-144">1.x</span></span>                   | <span data-ttu-id="546f4-145">Visual Studio 2017 версии 15.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="546f4-145">Visual Studio 2017 version 15.0 or higher.</span></span> |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="546f4-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="546f4-146">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="546f4-147">Для разработки приложений .NET Core в Visual Studio 2019 с помощью пакета SDK для .NET Core 3.0 выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="546f4-147">To develop .NET Core apps in Visual Studio 2019 using the .NET Core 3.0 SDK:</span></span>

* <span data-ttu-id="546f4-148">[Скачайте и установите Visual Studio 2019 версии 16.3 или более поздней](/visualstudio/install/install-visual-studio) и выберите одну из следующих рабочих нагрузок, включающих в себя пакет SDK для .NET Core, в зависимости от типа создаваемого приложения:</span><span class="sxs-lookup"><span data-stu-id="546f4-148">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) and select one of the following workloads that includes the .NET Core SDK, depending on the kind of application you're building:</span></span>

  * <span data-ttu-id="546f4-149">рабочая нагрузка **Кроссплатформенная разработка .NET Core** в разделе **Другие наборы инструментов**;</span><span class="sxs-lookup"><span data-stu-id="546f4-149">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
  * <span data-ttu-id="546f4-150">рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Веб-разработка и облако**;</span><span class="sxs-lookup"><span data-stu-id="546f4-150">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
  * <span data-ttu-id="546f4-151">рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Разработка классических приложений .NET**.</span><span class="sxs-lookup"><span data-stu-id="546f4-151">The **NET desktop development** workload in the **Windows** section.</span></span>

<span data-ttu-id="546f4-152">На следующем рисунке показана рабочая нагрузка **Кроссплатформенная разработка .NET Core**, выбранная в пользовательском интерфейсе Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="546f4-152">The following image shows the **.NET Core cross-platform development** workload selected in the Visual Studio UI:</span></span>

![Снимок экрана установки Visual Studio 2019 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-2019-workloads.jpg)

<span data-ttu-id="546f4-154">После установки любой из этих рабочих нагрузок Visual Studio 2019 версии 16.3 использует пакет SDK для .NET Core 3.0 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="546f4-154">Visual Studio 2019 version 16.3 uses .NET Core 3.0 SDK by default after any of these workloads are installed.</span></span>

<span data-ttu-id="546f4-155">Если вы хотите использовать в существующих проектах среду выполнения .NET Core последней версии, перенацельте каждый имеющийся проект .NET Core на .NET Core 3.0, выполнив приведенные ниже инструкции.</span><span class="sxs-lookup"><span data-stu-id="546f4-155">If you want your existing projects to use the latest .NET Core runtime, retarget each existing .NET Core project to .NET Core 3.0 using the following instructions:</span></span>

* <span data-ttu-id="546f4-156">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="546f4-156">On the **Project** menu, choose **Properties**.</span></span>
* <span data-ttu-id="546f4-157">В меню **Целевая платформа** выберите значение **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="546f4-157">In the **Target framework** selection menu, set the value to **.NET Core 3.0**.</span></span>

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2019 с выбранным пунктом ".NET Core 3.0" в меню целевой платформы](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

<span data-ttu-id="546f4-159">Настроив Visual Studio для работы с пакетом SDK для .NET Core 3.0, вы можете выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="546f4-159">Once you have Visual Studio configured with .NET Core 3.0 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="546f4-160">открытие, сборка и запуск существующих проектов .NET Core 1.x и 2.x;</span><span class="sxs-lookup"><span data-stu-id="546f4-160">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="546f4-161">перенацеливание проектов .NET Core 1.x и 2.x на .NET Core 3.0, сборка и запуск;</span><span class="sxs-lookup"><span data-stu-id="546f4-161">Retarget .NET Core 1.x and 2.x projects to .NET Core 3.0, build, and run.</span></span>
* <span data-ttu-id="546f4-162">создание проектов .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="546f4-162">Create new .NET Core 3.0 projects.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="546f4-163">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="546f4-163">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="546f4-164">Для разработки приложений .NET Core в Visual Studio 2017 с помощью пакета SDK для .NET Core 2.2 выполните указанные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="546f4-164">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

* <span data-ttu-id="546f4-165">[Скачайте и установите Visual Studio 2019 версии 16.3 или более поздней](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).</span><span class="sxs-lookup"><span data-stu-id="546f4-165">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
* <span data-ttu-id="546f4-166">[Скачайте и установите Visual Studio 2017 версии 15.9.0 или более поздней версии](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).</span><span class="sxs-lookup"><span data-stu-id="546f4-166">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="546f4-168">После установки набора инструментов **Кроссплатформенная разработка .NET Core** Visual Studio обычно устанавливает предыдущую версию пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="546f4-168">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="546f4-169">Например, после установки рабочей нагрузки Visual Studio 2017 версии 15.9 использует пакет SDK для .NET Core 2.1 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="546f4-169">For example, Visual Studio 2017 version 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="546f4-170">Чтобы обновить Visual Studio для использования пакета SDK для .NET Core 2.2, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="546f4-170">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="546f4-171">Установите [пакет SDK для .NET Core 2.2](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="546f4-171">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="546f4-172">Если вы хотите использовать в своем проекте среду выполнения .NET Core последней версии, перенацельте каждый имеющийся или новый проект .NET Core на .NET Core 2.2, выполнив приведенные ниже инструкции.</span><span class="sxs-lookup"><span data-stu-id="546f4-172">If you want your project to use the latest .NET Core runtime, retarget each existing or new .NET Core project to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="546f4-173">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="546f4-173">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="546f4-174">В меню **Целевая платформа** выберите значение **.NET Core 2.2**.</span><span class="sxs-lookup"><span data-stu-id="546f4-174">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.2" в меню целевой платформы](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="546f4-176">Настроив Visual Studio для работы с пакетом SDK для .NET Core 2.2, вы можете выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="546f4-176">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="546f4-177">открытие, сборка и запуск существующих проектов .NET Core 1.x и 2.x;</span><span class="sxs-lookup"><span data-stu-id="546f4-177">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="546f4-178">перенацеливание проектов .NET Core 1.x и 2.x на .NET Core 2.2, сборка и запуск;</span><span class="sxs-lookup"><span data-stu-id="546f4-178">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="546f4-179">создание проектов .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="546f4-179">Create new .NET Core 2.2 projects.</span></span>

---
