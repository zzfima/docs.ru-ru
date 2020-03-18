---
title: Учебник. Установка и использование глобального средства .NET Core
description: Узнайте, как устанавливать и использовать средство .NET в качестве глобального.
ms.date: 02/12/2020
ms.openlocfilehash: 9f8378e50fd2544eedbbaaeffb89d67800ec6880
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156742"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="2f521-103">Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f521-103">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>

<span data-ttu-id="2f521-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="2f521-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="2f521-105">В этом учебнике вы узнаете, как установить и использовать глобальное средство.</span><span class="sxs-lookup"><span data-stu-id="2f521-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="2f521-106">Вы используете инструмент, созданный в [первом учебнике этой серии](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="2f521-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f521-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2f521-107">Prerequisites</span></span>

* <span data-ttu-id="2f521-108">Выполните действия из [первого руководства этой серии](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="2f521-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="2f521-109">Использование средства в качестве глобального</span><span class="sxs-lookup"><span data-stu-id="2f521-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="2f521-110">Установите средство из пакета, выполнив команду [dotnet tool install](dotnet-tool-install.md) в папке проекта *microsoft.botsay*:</span><span class="sxs-lookup"><span data-stu-id="2f521-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *microsoft.botsay* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="2f521-111">Параметр `--global` настраивает в .NET Core CLI установку двоичных файлов средства в расположении по умолчанию, которое автоматически добавляется в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="2f521-111">The `--global` parameter tells the .NET Core CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="2f521-112">Параметр `--add-source` настраивает временное использование каталога *./nupkg* в качестве дополнительного источника пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="2f521-112">The `--add-source` parameter tells the .NET Core CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="2f521-113">Вы присвоили пакету уникальное имя, которое будет найдено только в каталоге *./nupkg*, а не на сайте Nuget.org.</span><span class="sxs-lookup"><span data-stu-id="2f521-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span>

   <span data-ttu-id="2f521-114">В выходных данных отображается команда, используемая для вызова средства и установленной версии:</span><span class="sxs-lookup"><span data-stu-id="2f521-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="2f521-115">Вызовите средство:</span><span class="sxs-lookup"><span data-stu-id="2f521-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="2f521-116">Если эта команда не сработает, для обновления PATH может потребоваться открыть новый терминал.</span><span class="sxs-lookup"><span data-stu-id="2f521-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="2f521-117">Удалите средство, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="2f521-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="2f521-118">Использование средства в качестве глобального средства, установленного в настраиваемом расположении</span><span class="sxs-lookup"><span data-stu-id="2f521-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="2f521-119">Установите средство из пакета.</span><span class="sxs-lookup"><span data-stu-id="2f521-119">Install the tool from the package.</span></span>

   <span data-ttu-id="2f521-120">Windows:</span><span class="sxs-lookup"><span data-stu-id="2f521-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="2f521-121">В Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="2f521-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="2f521-122">Параметр `--tool-path` настраивает в .NET Core CLI установку двоичных файлов средства в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="2f521-122">The `--tool-path` parameter tells the .NET Core CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="2f521-123">Создать каталог, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="2f521-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="2f521-124">Этот каталог не добавляется автоматически в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="2f521-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="2f521-125">В выходных данных отображается команда, используемая для вызова средства и установленной версии:</span><span class="sxs-lookup"><span data-stu-id="2f521-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="2f521-126">Вызовите средство:</span><span class="sxs-lookup"><span data-stu-id="2f521-126">Invoke the tool:</span></span>

   <span data-ttu-id="2f521-127">Windows:</span><span class="sxs-lookup"><span data-stu-id="2f521-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="2f521-128">В Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="2f521-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="2f521-129">Удалите средство, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="2f521-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="2f521-130">Windows:</span><span class="sxs-lookup"><span data-stu-id="2f521-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   <span data-ttu-id="2f521-131">В Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="2f521-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a><span data-ttu-id="2f521-132">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="2f521-132">Troubleshoot</span></span>

<span data-ttu-id="2f521-133">Если при выполнении учебника появляется сообщение об ошибке, см. статью [Устранение неполадок при использовании средства .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2f521-133">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2f521-134">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="2f521-134">Next steps</span></span>

<span data-ttu-id="2f521-135">В этом руководстве вы установили и использовали средство в качестве глобального.</span><span class="sxs-lookup"><span data-stu-id="2f521-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="2f521-136">Чтобы установить и использовать то же средство в качестве локального перейдите к следующему руководству.</span><span class="sxs-lookup"><span data-stu-id="2f521-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="2f521-137">[Tutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md) (Учебник. Установка и использование локального средства .NET Core с помощью NET Core CLI.)</span><span class="sxs-lookup"><span data-stu-id="2f521-137">[Install and use local tools](local-tools-how-to-use.md)</span></span>
