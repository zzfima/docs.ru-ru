---
title: УстановкаF#
description: Дополнительные сведения об установке F# об используемой среде.
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331979"
---
# <a name="install-f"></a><span data-ttu-id="56c6a-103">Установка F\#</span><span class="sxs-lookup"><span data-stu-id="56c6a-103">Install F\#</span></span>

<span data-ttu-id="56c6a-104">Вы можете установить F# несколькими способами, в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="56c6a-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="56c6a-105">Установка F# с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="56c6a-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="56c6a-106">Если происходит загрузка [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) в первый раз, его вначале установит установщик Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="56c6a-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="56c6a-107">Установите соответствующие номера SKU из Visual Studio с помощью установщика.</span><span class="sxs-lookup"><span data-stu-id="56c6a-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="56c6a-108">Если вы уже установили его, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="56c6a-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="56c6a-109">Далее вы увидите список рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="56c6a-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="56c6a-110">Выберите **ASP.NET и веб-разработка** каких будут установлены F# поддержки и .NET Core поддерживает для проектов ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="56c6a-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="56c6a-111">Затем щелкните **изменить** в нижнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="56c6a-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="56c6a-112">Эта команда установит все, что вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="56c6a-112">This will install everything you have selected.</span></span> <span data-ttu-id="56c6a-113">Затем можно открыть Visual Studio 2017 с F# языковой поддержки, нажав кнопку **запуска**.</span><span class="sxs-lookup"><span data-stu-id="56c6a-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="56c6a-114">Установка F# с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="56c6a-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="56c6a-115">F#устанавливается по умолчанию в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), независимо от того, какую конфигурацию вы выберите.</span><span class="sxs-lookup"><span data-stu-id="56c6a-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="56c6a-116">После завершения установки, выберите «Запустить Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="56c6a-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="56c6a-117">Его можно также запустить через Finder в macOS.</span><span class="sxs-lookup"><span data-stu-id="56c6a-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="56c6a-118">Установка F# с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="56c6a-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="56c6a-119">Необходимо иметь [репозиторий git](https://git-scm.com/download) и доступные в свой путь, чтобы сделать использование шаблонов проектов.</span><span class="sxs-lookup"><span data-stu-id="56c6a-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="56c6a-120">Убедитесь, что он установлен правильно, введя `git --version` командной строки и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="56c6a-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### [<a name="macos"></a><span data-ttu-id="56c6a-121">macOS</span><span class="sxs-lookup"><span data-stu-id="56c6a-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="56c6a-122">[Mono](https://www.mono-project.com) используется для [ F# интерактивные](../tutorials/fsharp-interactive/index.md) поддержки.</span><span class="sxs-lookup"><span data-stu-id="56c6a-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="56c6a-123">Самый простой способ установить Mono в macOS — с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="56c6a-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="56c6a-124">Просто введите следующую команду в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="56c6a-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="56c6a-125">Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="56c6a-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### [<a name="linux"></a><span data-ttu-id="56c6a-126">Linux</span><span class="sxs-lookup"><span data-stu-id="56c6a-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="56c6a-127">[Mono](https://www.mono-project.com) используется для [ F# интерактивные](../tutorials/fsharp-interactive/index.md) поддержки.</span><span class="sxs-lookup"><span data-stu-id="56c6a-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="56c6a-128">Если вы в Debian и Ubuntu, можно использовать следующее:</span><span class="sxs-lookup"><span data-stu-id="56c6a-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="56c6a-129">Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="56c6a-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### [<a name="windows"></a><span data-ttu-id="56c6a-130">Windows</span><span class="sxs-lookup"><span data-stu-id="56c6a-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="56c6a-131">Установка [Visual Studio с F# поддерживает](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="56c6a-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="56c6a-132">При этом будут установлены все необходимые компоненты для написания, компиляции и выполнения F# кода.</span><span class="sxs-lookup"><span data-stu-id="56c6a-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="56c6a-133">Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="56c6a-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="56c6a-134">Необходимо будет [Visual Studio Code](https://code.visualstudio.com) установлен.</span><span class="sxs-lookup"><span data-stu-id="56c6a-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="56c6a-135">Затем щелкните значок расширения и выполните поиск «Ionide»:</span><span class="sxs-lookup"><span data-stu-id="56c6a-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="56c6a-136">Только необходимые для подключаемого модуля F# является поддержка в Visual Studio Code [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="56c6a-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="56c6a-137">Тем не менее, можно также установить [Ionide ИМИТАЦИИ](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) для получения [ИМИТИРОВАТЬ](https://fsharp.github.io/FAKE/) поддержки и [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) для получения [Paket](https://fsprojects.github.io/Paket/) поддержки.</span><span class="sxs-lookup"><span data-stu-id="56c6a-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="56c6a-138">ПОДДЕЛКИ и Paket приведены дополнительные F# инструменты сообщества для построения проектов и управление зависимостями, соответственно.</span><span class="sxs-lookup"><span data-stu-id="56c6a-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
