---
title: Учебник. Установка и использование глобального средства .NET Core
description: Узнайте, как устанавливать и использовать средство .NET в качестве глобального.
ms.date: 02/12/2020
ms.openlocfilehash: 65047af9d8a7f2fd4c1a07f65af3a6ddbf870c5d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543824"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="b5275-103">Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="b5275-103">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>

<span data-ttu-id="b5275-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="b5275-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="b5275-105">В этом учебнике вы узнаете, как установить и использовать глобальное средство.</span><span class="sxs-lookup"><span data-stu-id="b5275-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="b5275-106">Вы используете инструмент, созданный в [первом учебнике этой серии](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="b5275-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5275-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b5275-107">Prerequisites</span></span>

* <span data-ttu-id="b5275-108">Выполните действия из [первого руководства этой серии](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="b5275-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="b5275-109">Использование средства в качестве глобального</span><span class="sxs-lookup"><span data-stu-id="b5275-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="b5275-110">Установите средство из пакета, выполнив команду [dotnet tool install](dotnet-tool-install.md) в папке проекта *botsay-\<name>* :</span><span class="sxs-lookup"><span data-stu-id="b5275-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *botsay-\<name>* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="b5275-111">Параметр `--global` настраивает в .NET Core CLI установку двоичных файлов средства в расположении по умолчанию, которое автоматически добавляется в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="b5275-111">The `--global` parameter tells the .NET Core CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="b5275-112">Параметр `--add-source` настраивает временное использование каталога *./nupkg* в качестве дополнительного источника пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="b5275-112">The `--add-source` parameter tells the .NET Core CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="b5275-113">Вы присвоили пакету уникальное имя, которое будет найдено только в каталоге *./nupkg*, а не на сайте Nuget.org.</span><span class="sxs-lookup"><span data-stu-id="b5275-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span> 

   <span data-ttu-id="b5275-114">В выходных данных отображается команда, используемая для вызова средства и установленной версии:</span><span class="sxs-lookup"><span data-stu-id="b5275-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="b5275-115">Вызовите средство:</span><span class="sxs-lookup"><span data-stu-id="b5275-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="b5275-116">Если эта команда не сработает, для обновления PATH может потребоваться открыть новый терминал.</span><span class="sxs-lookup"><span data-stu-id="b5275-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="b5275-117">Удалите средство, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="b5275-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g botsay-<name>
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="b5275-118">Использование средства в качестве глобального средства, установленного в настраиваемом расположении</span><span class="sxs-lookup"><span data-stu-id="b5275-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="b5275-119">Установите средство из пакета.</span><span class="sxs-lookup"><span data-stu-id="b5275-119">Install the tool from the package.</span></span>

   <span data-ttu-id="b5275-120">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5275-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="b5275-121">В Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="b5275-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="b5275-122">Параметр `--tool-path` настраивает в .NET Core CLI установку двоичных файлов средства в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="b5275-122">The `--tool-path` parameter tells the .NET Core CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="b5275-123">Создать каталог, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="b5275-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="b5275-124">Этот каталог не добавляется автоматически в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="b5275-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="b5275-125">В выходных данных отображается команда, используемая для вызова средства и установленной версии:</span><span class="sxs-lookup"><span data-stu-id="b5275-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="b5275-126">Вызовите средство:</span><span class="sxs-lookup"><span data-stu-id="b5275-126">Invoke the tool:</span></span>

   <span data-ttu-id="b5275-127">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5275-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="b5275-128">В Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="b5275-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="b5275-129">Удалите средство, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="b5275-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="b5275-130">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5275-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools botsay --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="b5275-131">В Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="b5275-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin botsay-<name>
   ```

## <a name="troubleshoot"></a><span data-ttu-id="b5275-132">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b5275-132">Troubleshoot</span></span>

<span data-ttu-id="b5275-133">Если при выполнении учебника появляется сообщение об ошибке, см. статью [Устранение неполадок при использовании средства .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b5275-133">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5275-134">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="b5275-134">Next steps</span></span>

<span data-ttu-id="b5275-135">В этом руководстве вы установили и использовали средство в качестве глобального.</span><span class="sxs-lookup"><span data-stu-id="b5275-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="b5275-136">Чтобы установить и использовать то же средство в качестве локального перейдите к следующему руководству.</span><span class="sxs-lookup"><span data-stu-id="b5275-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="b5275-137">[Tutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md) (Учебник. Установка и использование локального средства .NET Core с помощью NET Core CLI.)</span><span class="sxs-lookup"><span data-stu-id="b5275-137">[Install and use local tools](local-tools-how-to-use.md)</span></span>
