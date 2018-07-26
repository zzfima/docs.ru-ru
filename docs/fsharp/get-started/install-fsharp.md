---
title: 'Установка F #'
description: 'Сведения об установке F # об используемой среде.'
ms.date: 07/03/2018
ms.openlocfilehash: 142265a95e1d3ee1603a89f650a24c6a45709181
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37878853"
---
# <a name="install-f"></a><span data-ttu-id="f6664-103">Установка F #</span><span class="sxs-lookup"><span data-stu-id="f6664-103">Install F#</span></span> #

<span data-ttu-id="f6664-104">Вы можете установить F # несколькими способами, в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="f6664-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="f6664-105">Установка F # с Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f6664-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="f6664-106">Если происходит загрузка [Visual Studio](https://visualstudio.microsoft.com/) в первый раз, его вначале установит установщик Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f6664-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="f6664-107">Установите соответствующие номера SKU из Visual Studio с помощью установщика.</span><span class="sxs-lookup"><span data-stu-id="f6664-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="f6664-108">Если вы уже установили его, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f6664-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="f6664-109">Далее вы увидите список рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="f6664-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="f6664-110">Выберите **ASP.NET и веб-разработка**, что позволит установить поддержка F #, поддержка .NET Core и проекты F # поддержка ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6664-110">Select **ASP.NET and web development**, which will install F# support, .NET Core support, and F# support for ASP.NET Core projects.</span></span>

<span data-ttu-id="f6664-111">Затем щелкните **изменить** в нижнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="f6664-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="f6664-112">Эта команда установит все, что вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="f6664-112">This will install everything you have selected.</span></span> <span data-ttu-id="f6664-113">Затем можно открыть Visual Studio 2017 с поддержкой языка F #, щелкнув **запуска**.</span><span class="sxs-lookup"><span data-stu-id="f6664-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="f6664-114">Установка F # с Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="f6664-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="f6664-115">F # по умолчанию устанавливается в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/), независимо от того, какая конфигурация выбрана.</span><span class="sxs-lookup"><span data-stu-id="f6664-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/), no matter what configuration you choose.</span></span>

<span data-ttu-id="f6664-116">После завершения установки, выберите «Запустить Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="f6664-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="f6664-117">Его можно также запустить через Finder в macOS.</span><span class="sxs-lookup"><span data-stu-id="f6664-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="f6664-118">Установка F # с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f6664-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="f6664-119">Необходимо иметь [репозиторий git](https://git-scm.com/download) и доступные в свой путь, чтобы сделать использование шаблонов проектов в Ionide.</span><span class="sxs-lookup"><span data-stu-id="f6664-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span> <span data-ttu-id="f6664-120">Убедитесь, что он установлен правильно, введя `git --version` командной строки и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="f6664-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="f6664-121">macOS</span><span class="sxs-lookup"><span data-stu-id="f6664-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="f6664-122">Использует Ionide [Mono](http://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="f6664-122">Ionide uses [Mono](http://www.mono-project.com).</span></span> <span data-ttu-id="f6664-123">Самый простой способ установить Mono в macOS — с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="f6664-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="f6664-124">Просто введите следующую команду в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="f6664-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="f6664-125">Необходимо также установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="f6664-125">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="f6664-126">Linux</span><span class="sxs-lookup"><span data-stu-id="f6664-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="f6664-127">В Linux, также использует Ionide [Mono](https://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="f6664-127">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="f6664-128">Если вы в Debian и Ubuntu, можно использовать следующее:</span><span class="sxs-lookup"><span data-stu-id="f6664-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="f6664-129">Необходимо также установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="f6664-129">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="f6664-130">Windows</span><span class="sxs-lookup"><span data-stu-id="f6664-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="f6664-131">Если вы используете Windows, необходимо [установить Visual Studio с поддержкой F #](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f6664-131">If you're on Windows, you must [install Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="f6664-132">При этом будут установлены все необходимые компоненты для написания, компиляции и выполнения кода на F #.</span><span class="sxs-lookup"><span data-stu-id="f6664-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="f6664-133">Необходимо также установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="f6664-133">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="f6664-134">Необходимо будет [Visual Studio Code](https://code.visualstudio.com) установлен.</span><span class="sxs-lookup"><span data-stu-id="f6664-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="f6664-135">Затем щелкните значок расширения и выполните поиск «Ionide»:</span><span class="sxs-lookup"><span data-stu-id="f6664-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="f6664-136">Только подключаемый модуль, необходимый для поддержки F # в Visual Studio Code является [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="f6664-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="f6664-137">Тем не менее, можно также установить [Ionide ИМИТАЦИИ](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) для получения [ИМИТИРОВАТЬ](https://fsharp.github.io/FAKE/) поддержки и [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) для получения [Paket](https://fsprojects.github.io/Paket/) поддержки.</span><span class="sxs-lookup"><span data-stu-id="f6664-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="f6664-138">ПОДДЕЛКИ и Paket средства Дополнительные сообщества F # для создания проектов и управление зависимостями, соответственно.</span><span class="sxs-lookup"><span data-stu-id="f6664-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>