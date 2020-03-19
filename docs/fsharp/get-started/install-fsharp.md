---
title: Установка F#
description: Узнайте, как установить F-образное установить F-образное время различными способами.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401097"
---
# <a name="install-f"></a><span data-ttu-id="e08df-103">Установка F\#</span><span class="sxs-lookup"><span data-stu-id="e08df-103">Install F\#</span></span>

<span data-ttu-id="e08df-104">Вы можете установить F-образное, в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="e08df-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="e08df-105">Установка ФЗ с помощью визуальной студии</span><span class="sxs-lookup"><span data-stu-id="e08df-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="e08df-106">Если вы загружаете [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) в первый раз, он сначала установит Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="e08df-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="e08df-107">Установите соответствующее издание Visual Studio от установки.</span><span class="sxs-lookup"><span data-stu-id="e08df-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="e08df-108">Если у вас уже установлена Visual Studio, выберите **Modify** рядом с изданием, к который вы хотите добавить F-образное.</span><span class="sxs-lookup"><span data-stu-id="e08df-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="e08df-109">На странице «Рабочие нагрузки» выберите рабочую нагрузку **ASP.NET и веб-разработки,** которая включает в себя поддержку F и .NET Core для ASP.NET основных проектов.</span><span class="sxs-lookup"><span data-stu-id="e08df-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="e08df-110">Выберите **изменение** в правом нижнем углу, чтобы установить все, что вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="e08df-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="e08df-111">Затем вы можете открыть Visual Studio с F, выбрав **Launch** in Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="e08df-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="e08df-112">Установка F с визуальным кодом студии</span><span class="sxs-lookup"><span data-stu-id="e08df-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="e08df-113">Убедитесь, что у вас есть [git](https://git-scm.com/download) установлен и доступен на вашем PATH.</span><span class="sxs-lookup"><span data-stu-id="e08df-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="e08df-114">Вы можете убедиться, что он `git --version` установлен правильно, введя в команде запрос и нажатие **Enter.**</span><span class="sxs-lookup"><span data-stu-id="e08df-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="e08df-115">Установите [код .NET Core SDK](https://dotnet.microsoft.com/download) и [Visual Studio.](https://code.visualstudio.com)</span><span class="sxs-lookup"><span data-stu-id="e08df-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="e08df-116">Выберите значок расширения и ищите "Ionide":</span><span class="sxs-lookup"><span data-stu-id="e08df-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="e08df-117">Единственным плагином, необходимым для поддержки F-студии в Visual Studio Code, является [Ionide-fsharp.](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)</span><span class="sxs-lookup"><span data-stu-id="e08df-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="e08df-118">Тем не менее, вы также можете установить [Ionide-FAKE,](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) чтобы получить поддержку [FAKE](https://fake.build/) и [Ionide-Paket,](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) чтобы получить поддержку [Paket.](https://fsprojects.github.io/Paket/)</span><span class="sxs-lookup"><span data-stu-id="e08df-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="e08df-119">FAKE и Paket являются дополнительными инструментами сообщества F е для создания проектов и управления зависимостями, соответственно.</span><span class="sxs-lookup"><span data-stu-id="e08df-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="e08df-120">Установка F с Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="e08df-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="e08df-121">Фз устанавливается по умолчанию в [Visual Studio для Mac,](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)независимо от того, какую конфигурацию вы выберете.</span><span class="sxs-lookup"><span data-stu-id="e08df-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="e08df-122">После завершения установки выберите **Start Visual Studio.**</span><span class="sxs-lookup"><span data-stu-id="e08df-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="e08df-123">Вы также можете открыть Visual Studio через Finder на macOS.</span><span class="sxs-lookup"><span data-stu-id="e08df-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="e08df-124">Установка F-сервера на сервере сборки</span><span class="sxs-lookup"><span data-stu-id="e08df-124">Install F# on a build server</span></span>

<span data-ttu-id="e08df-125">Если вы используете систему .NET Core или .NET через .NET SDK, вам просто необходимо установить .NET SDK на сервер сборки.</span><span class="sxs-lookup"><span data-stu-id="e08df-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="e08df-126">В нем есть все, что вам нужно.</span><span class="sxs-lookup"><span data-stu-id="e08df-126">It has everything you need.</span></span>

<span data-ttu-id="e08df-127">Если вы используете систему .NET и **не** используете SDK .NET, то вам нужно установить [SKU Visual Studio Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) на ваш Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e08df-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="e08df-128">В установке выберите **инструменты сборки настольных компьютеров .NET,** а затем выберите компонент **компилятора F's** на правой стороне меню установки.</span><span class="sxs-lookup"><span data-stu-id="e08df-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
