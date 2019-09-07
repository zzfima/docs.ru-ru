---
title: Установка F#
description: Узнайте, как установить F# на основе среды.
ms.date: 09/05/2019
ms.openlocfilehash: 18b660ff640904119d63f57405752a14f7673e0c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400717"
---
# <a name="install-f"></a><span data-ttu-id="ba0eb-103">Установка F\#</span><span class="sxs-lookup"><span data-stu-id="ba0eb-103">Install F\#</span></span>

<span data-ttu-id="ba0eb-104">В зависимости от F# среды можно установить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="ba0eb-105">Установка F# с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ba0eb-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="ba0eb-106">Если вы скачиваете [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) впервые, сначала будет установлена программа Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="ba0eb-107">Установите соответствующий SKU Visual Studio из установщика.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="ba0eb-108">Если вы уже установили его, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="ba0eb-109">Далее вы увидите список рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="ba0eb-110">Выберите **ASP.NET и веб-разработку** , которые F# будут устанавливать поддержку и поддержку .net Core для проектов ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="ba0eb-111">Затем в нижней правой части щелкните **изменить** .</span><span class="sxs-lookup"><span data-stu-id="ba0eb-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="ba0eb-112">Будет выполнена установка всех выбранных элементов.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-112">This will install everything you have selected.</span></span> <span data-ttu-id="ba0eb-113">Затем можно открыть Visual Studio 2017 с F# поддержкой языка, нажав кнопку **запустить**.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="ba0eb-114">Установка F# с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="ba0eb-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="ba0eb-115">F#устанавливается по умолчанию в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), независимо от выбранной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="ba0eb-116">После завершения установки нажмите кнопку "запустить Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="ba0eb-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="ba0eb-117">Его также можно запустить с помощью средства поиска в macOS.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="ba0eb-118">Установка F# с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ba0eb-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="ba0eb-119">Необходимо установить и сделать [Git](https://git-scm.com/download) доступным на пути, чтобы использовать шаблоны проектов.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="ba0eb-120">Чтобы проверить правильность установки, введите `git --version` в командной строке и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="ba0eb-121">macOS</span><span class="sxs-lookup"><span data-stu-id="ba0eb-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="ba0eb-122">[Mono](https://www.mono-project.com) используется для [ F# интерактивной](../tutorials/fsharp-interactive/index.md) поддержки.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="ba0eb-123">Самый простой способ установить Mono на macOS — через Homebrew.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="ba0eb-124">Просто введите следующий текст в терминал:</span><span class="sxs-lookup"><span data-stu-id="ba0eb-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="ba0eb-125">Также установите [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="ba0eb-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="ba0eb-126">Linux</span><span class="sxs-lookup"><span data-stu-id="ba0eb-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="ba0eb-127">[Mono](https://www.mono-project.com) используется для [ F# интерактивной](../tutorials/fsharp-interactive/index.md) поддержки.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="ba0eb-128">Если вы используете Debian или Ubuntu, вы можете использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ba0eb-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="ba0eb-129">Также установите [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="ba0eb-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="ba0eb-130">Windows</span><span class="sxs-lookup"><span data-stu-id="ba0eb-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="ba0eb-131">Установите [Visual Studio с F# поддержкой](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ba0eb-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="ba0eb-132">При этом устанавливаются все необходимые компоненты для записи, компиляции и выполнения F# кода.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="ba0eb-133">Также установите [пакет SDK для .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="ba0eb-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="ba0eb-134">После этого потребуется [Visual Studio Code](https://code.visualstudio.com) установить.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="ba0eb-135">Затем щелкните значок расширения и выполните поиск по запросу "Ionide":</span><span class="sxs-lookup"><span data-stu-id="ba0eb-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="ba0eb-136">Единственным подключаемым модулем F# , необходимым для поддержки в Visual Studio Code, является [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="ba0eb-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="ba0eb-137">Однако можно также установить [Ionide-ПОДдельные](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) , чтобы получить [поддельную](https://fsharp.github.io/FAKE/) поддержку и [Ionide-пакет](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) , чтобы получить поддержку [пакет](https://fsprojects.github.io/Paket/) .</span><span class="sxs-lookup"><span data-stu-id="ba0eb-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="ba0eb-138">Поддельные и пакет — F# это дополнительные инструменты сообщества для создания проектов и управления зависимостями соответственно.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="ba0eb-139">Установка F# на сервере сборки</span><span class="sxs-lookup"><span data-stu-id="ba0eb-139">Install F# on a Build Server</span></span>

<span data-ttu-id="ba0eb-140">Если вы используете .NET Core или .NET Framework с помощью пакета SDK для .NET, необходимо просто установить пакет SDK для .NET на сервере сборки.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-140">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="ba0eb-141">Он содержит все необходимое.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-141">It has everything you need.</span></span>

<span data-ttu-id="ba0eb-142">Если вы используете .NET Framework и вы **не** используете пакет SDK для .NET, необходимо установить [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) на сервере Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-142">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="ba0eb-143">В установщике выберите **.NET Desktop Build Tools** , а затем выберите компонент  **F# компилятора** в правой части меню установщика.</span><span class="sxs-lookup"><span data-stu-id="ba0eb-143">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
