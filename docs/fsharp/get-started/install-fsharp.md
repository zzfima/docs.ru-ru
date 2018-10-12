---
title: 'Установка F #'
description: 'Сведения об установке F # об используемой среде.'
ms.date: 08/28/2018
ms.openlocfilehash: 909e1c07ff7f6d52db77a987639d1c749146fdca
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49120938"
---
# <a name="install-f"></a><span data-ttu-id="05445-103">Установка F #</span><span class="sxs-lookup"><span data-stu-id="05445-103">Install F#</span></span> #

<span data-ttu-id="05445-104">Вы можете установить F # несколькими способами, в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="05445-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="05445-105">Установка F # с Visual Studio</span><span class="sxs-lookup"><span data-stu-id="05445-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="05445-106">Если происходит загрузка [Visual Studio](https://visualstudio.microsoft.com/) в первый раз, его вначале установит установщик Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="05445-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="05445-107">Установите соответствующие номера SKU из Visual Studio с помощью установщика.</span><span class="sxs-lookup"><span data-stu-id="05445-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="05445-108">Если вы уже установили его, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="05445-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="05445-109">Далее вы увидите список рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="05445-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="05445-110">Выберите **ASP.NET и веб-разработка** которого будет устанавливаться, поддержка F # и поддержке .NET Core для проектов ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="05445-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="05445-111">Затем щелкните **изменить** в нижнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="05445-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="05445-112">Эта команда установит все, что вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="05445-112">This will install everything you have selected.</span></span> <span data-ttu-id="05445-113">Затем можно открыть Visual Studio 2017 с поддержкой языка F #, щелкнув **запуска**.</span><span class="sxs-lookup"><span data-stu-id="05445-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="05445-114">Установка F # с Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="05445-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="05445-115">F # по умолчанию устанавливается в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/), независимо от того, какую конфигурацию вы выберите.</span><span class="sxs-lookup"><span data-stu-id="05445-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/), no matter which configuration you choose.</span></span>

<span data-ttu-id="05445-116">После завершения установки, выберите «Запустить Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="05445-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="05445-117">Его можно также запустить через Finder в macOS.</span><span class="sxs-lookup"><span data-stu-id="05445-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="05445-118">Установка F # с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="05445-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="05445-119">Необходимо иметь [репозиторий git](https://git-scm.com/download) и доступные в свой путь, чтобы сделать использование шаблонов проектов.</span><span class="sxs-lookup"><span data-stu-id="05445-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="05445-120">Убедитесь, что он установлен правильно, введя `git --version` командной строки и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="05445-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="05445-121">macOS</span><span class="sxs-lookup"><span data-stu-id="05445-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="05445-122">[Mono](http://www.mono-project.com) используется для [F # Interactive](../tutorials/fsharp-interactive/index.md) поддержки.</span><span class="sxs-lookup"><span data-stu-id="05445-122">[Mono](http://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="05445-123">Самый простой способ установить Mono в macOS — с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="05445-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="05445-124">Просто введите следующую команду в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="05445-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="05445-125">Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="05445-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="05445-126">Linux</span><span class="sxs-lookup"><span data-stu-id="05445-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="05445-127">[Mono](https://www.mono-project.com) используется для [F # Interactive](../tutorials/fsharp-interactive/index.md) поддержки.</span><span class="sxs-lookup"><span data-stu-id="05445-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="05445-128">Если вы в Debian и Ubuntu, можно использовать следующее:</span><span class="sxs-lookup"><span data-stu-id="05445-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="05445-129">Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="05445-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="05445-130">Windows</span><span class="sxs-lookup"><span data-stu-id="05445-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="05445-131">Установка [Visual Studio с поддержкой F #](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="05445-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="05445-132">При этом будут установлены все необходимые компоненты для написания, компиляции и выполнения кода на F #.</span><span class="sxs-lookup"><span data-stu-id="05445-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="05445-133">Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="05445-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="05445-134">Необходимо будет [Visual Studio Code](https://code.visualstudio.com) установлен.</span><span class="sxs-lookup"><span data-stu-id="05445-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="05445-135">Затем щелкните значок расширения и выполните поиск «Ionide»:</span><span class="sxs-lookup"><span data-stu-id="05445-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="05445-136">Только подключаемый модуль, необходимый для поддержки F # в Visual Studio Code является [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="05445-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="05445-137">Тем не менее, можно также установить [Ionide ИМИТАЦИИ](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) для получения [ИМИТИРОВАТЬ](https://fsharp.github.io/FAKE/) поддержки и [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) для получения [Paket](https://fsprojects.github.io/Paket/) поддержки.</span><span class="sxs-lookup"><span data-stu-id="05445-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="05445-138">ПОДДЕЛКИ и Paket средства Дополнительные сообщества F # для создания проектов и управление зависимостями, соответственно.</span><span class="sxs-lookup"><span data-stu-id="05445-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
