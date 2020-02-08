---
title: Глобальные средства .NET Core
description: Обзор глобальных средств .NET Core и доступных для них команд .NET Core CLI.
author: KathleenDollard
ms.date: 05/29/2018
ms.openlocfilehash: 1531df48b7ca9c816b897d06e725ec375f6cae31
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920494"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="a2b94-103">Обзор глобальных средств .NET Core</span><span class="sxs-lookup"><span data-stu-id="a2b94-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="a2b94-104">Глобальное средство .NET Core — это специальный пакет NuGet, который содержит консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="a2b94-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="a2b94-105">Глобальное средство можно установить на компьютере в расположении по умолчанию, которое включено в переменную среды PATH, или в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="a2b94-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="a2b94-106">Процесс работы с глобальным средством .NET Core включает следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="a2b94-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="a2b94-107">поиск информации о средстве (обычно на веб-сайте или странице GitHub);</span><span class="sxs-lookup"><span data-stu-id="a2b94-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="a2b94-108">проверку автора и статистики в корневой папке веб-канала (обычно NuGet.org);</span><span class="sxs-lookup"><span data-stu-id="a2b94-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="a2b94-109">установку средства;</span><span class="sxs-lookup"><span data-stu-id="a2b94-109">Install the tool.</span></span>
* <span data-ttu-id="a2b94-110">вызов средства;</span><span class="sxs-lookup"><span data-stu-id="a2b94-110">Call the tool.</span></span>
* <span data-ttu-id="a2b94-111">обновление средства;</span><span class="sxs-lookup"><span data-stu-id="a2b94-111">Update the tool.</span></span>
* <span data-ttu-id="a2b94-112">удаление средства.</span><span class="sxs-lookup"><span data-stu-id="a2b94-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2b94-113">Глобальные средства .NET Core устанавливаются по выбранному вами пути и выполняются в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="a2b94-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="a2b94-114">Не устанавливайте глобальные средства .NET Core, если вы не доверяете автору.</span><span class="sxs-lookup"><span data-stu-id="a2b94-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="a2b94-115">Как найти глобальное средство .NET Core</span><span class="sxs-lookup"><span data-stu-id="a2b94-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="a2b94-116">В .NET Core CLI пока нет функции поиска глобальных средств.</span><span class="sxs-lookup"><span data-stu-id="a2b94-116">Currently, there isn't a Global Tool search feature in the .NET Core CLI.</span></span> <span data-ttu-id="a2b94-117">Ниже приведены некоторые рекомендации по поиску средств.</span><span class="sxs-lookup"><span data-stu-id="a2b94-117">The following are some recommendations on how to find tools:</span></span>

* <span data-ttu-id="a2b94-118">Глобальные средства .NET Core можно найти в [NuGet](https://www.nuget.org).</span><span class="sxs-lookup"><span data-stu-id="a2b94-118">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="a2b94-119">При этом NuGet пока не позволяет выполнять поиск конкретных глобальных средств .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2b94-119">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>
* <span data-ttu-id="a2b94-120">Вы можете найти рекомендации средств в записях блога или в репозитории GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="a2b94-120">You may find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="a2b94-121">Кроме того, в репозитории GitHub [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) вам доступен исходный код для глобальных средств, созданных командой разработчиков ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a2b94-121">You can see the source code for the Global Tools created by the ASP.NET team at the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) GitHub repository.</span></span>
* <span data-ttu-id="a2b94-122">Дополнительные сведения о средствах диагностики см. в разделе [Глобальные средства диагностики dotnet в .NET Core](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span><span class="sxs-lookup"><span data-stu-id="a2b94-122">You can learn about diagnostic tools at [.NET Core dotnet diagnostic Global Tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="a2b94-123">Проверка автора и статистики</span><span class="sxs-lookup"><span data-stu-id="a2b94-123">Check the author and statistics</span></span>

<span data-ttu-id="a2b94-124">Поскольку глобальные средства .NET Core выполняются в режиме полного доверия и обычно устанавливаются по заданному вами пути, они имеют большие привилегии.</span><span class="sxs-lookup"><span data-stu-id="a2b94-124">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="a2b94-125">Не скачивайте средства авторов, которым вы не доверяете.</span><span class="sxs-lookup"><span data-stu-id="a2b94-125">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="a2b94-126">Если средство размещается в NuGet, вы можете проверить автора и статистику, выполнив поиск средства.</span><span class="sxs-lookup"><span data-stu-id="a2b94-126">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="a2b94-127">Установка глобального средства</span><span class="sxs-lookup"><span data-stu-id="a2b94-127">Install a Global Tool</span></span>

<span data-ttu-id="a2b94-128">Чтобы установить глобальное средство, используйте команду .NET Core CLI [dotnet tool install](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="a2b94-128">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="a2b94-129">В примере ниже показано, как установить глобальное средство в расположении по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a2b94-129">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="a2b94-130">Если не удается установить средство, отображаются сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a2b94-130">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="a2b94-131">Убедитесь, что установлены флажки для нужных веб-каналов.</span><span class="sxs-lookup"><span data-stu-id="a2b94-131">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="a2b94-132">Если вам необходимо установить предварительную или конкретную версию средства, можно указать номер версии, используя следующий формат:</span><span class="sxs-lookup"><span data-stu-id="a2b94-132">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="a2b94-133">Если установка выполнена успешно, отображается сообщение с командой, используемой для вызова средства, и установленной версией, аналогичное приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="a2b94-133">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="a2b94-134">Глобальные средства можно установить в каталоге по умолчанию или в выбранном вами расположении.</span><span class="sxs-lookup"><span data-stu-id="a2b94-134">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="a2b94-135">Каталоги по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a2b94-135">The default directories are:</span></span>

| <span data-ttu-id="a2b94-136">Операционная система</span><span class="sxs-lookup"><span data-stu-id="a2b94-136">OS</span></span>          | <span data-ttu-id="a2b94-137">Path</span><span class="sxs-lookup"><span data-stu-id="a2b94-137">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="a2b94-138">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="a2b94-138">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="a2b94-139">Windows</span><span class="sxs-lookup"><span data-stu-id="a2b94-139">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="a2b94-140">Эти расположения добавляются в путь пользователя при первом запуске пакета SDK, поэтому установленные в них глобальные средства можно вызывать напрямую.</span><span class="sxs-lookup"><span data-stu-id="a2b94-140">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="a2b94-141">Обратите внимание, что глобальные средства входят в область конкретного пользователя, а не глобальную область компьютера.</span><span class="sxs-lookup"><span data-stu-id="a2b94-141">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="a2b94-142">Таким образом, нельзя установить глобальное средство, которое будет доступно для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="a2b94-142">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="a2b94-143">Средство доступно только для тех профилей пользователей, в которых оно установлено.</span><span class="sxs-lookup"><span data-stu-id="a2b94-143">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="a2b94-144">Глобальные средства также можно установить в конкретном каталоге.</span><span class="sxs-lookup"><span data-stu-id="a2b94-144">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="a2b94-145">При установке в конкретном каталоге необходимо убедиться, что команда доступна, включив этот каталог в путь, вызвав команду с указанным каталогом или вызвав средство из указанного каталога.</span><span class="sxs-lookup"><span data-stu-id="a2b94-145">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="a2b94-146">В этом случае .NET Core CLI не добавляет это расположение автоматически в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="a2b94-146">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="a2b94-147">Работа со средством</span><span class="sxs-lookup"><span data-stu-id="a2b94-147">Use the tool</span></span>

<span data-ttu-id="a2b94-148">После установки средства его можно вызывать с помощью команды.</span><span class="sxs-lookup"><span data-stu-id="a2b94-148">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="a2b94-149">Обратите внимание, что команда может отличаться от имени пакета.</span><span class="sxs-lookup"><span data-stu-id="a2b94-149">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="a2b94-150">Если команда — `dotnetsay`, она вызывается с помощью:</span><span class="sxs-lookup"><span data-stu-id="a2b94-150">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="a2b94-151">Если автор средства предусмотрел его отображение в контексте запроса `dotnet`, оно может вызываться как `dotnet <command>`, например:</span><span class="sxs-lookup"><span data-stu-id="a2b94-151">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="a2b94-152">Чтобы узнать, какие средства входят в установленный пакет глобального средства, можно перечислить установленные пакеты с помощью команды [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="a2b94-152">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="a2b94-153">Вы также можете найти инструкции по использованию на веб-сайте средства или выполнив одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="a2b94-153">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a><span data-ttu-id="a2b94-154">Другие команды интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="a2b94-154">Other CLI commands</span></span>

<span data-ttu-id="a2b94-155">Пакет SDK для .NET Core содержит другие команды, которые поддерживают глобальные средства .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2b94-155">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="a2b94-156">Все команды `dotnet tool` можно использовать с одним из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a2b94-156">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="a2b94-157">`--global` или `-g` указывает, что команда применяется к глобальному средству уровня пользователя;</span><span class="sxs-lookup"><span data-stu-id="a2b94-157">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="a2b94-158">`--tool-path` задает пользовательское расположение для глобальных средств.</span><span class="sxs-lookup"><span data-stu-id="a2b94-158">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="a2b94-159">Чтобы узнать, какие команды доступны для глобальных средств, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a2b94-159">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="a2b94-160">Обновление глобального средства подразумевает его удаление и установку последней стабильной версии.</span><span class="sxs-lookup"><span data-stu-id="a2b94-160">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="a2b94-161">Чтобы обновить глобальное средство, используйте команду [dotnet tool update](dotnet-tool-update.md):</span><span class="sxs-lookup"><span data-stu-id="a2b94-161">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="a2b94-162">Удалите глобальное средство с помощью команды [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="a2b94-162">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="a2b94-163">Чтобы отобразить все глобальные средства, установленные на компьютере (вместе со сведениями о версиях и командах), используйте команду [dotnet tool list](dotnet-tool-list.md):</span><span class="sxs-lookup"><span data-stu-id="a2b94-163">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a><span data-ttu-id="a2b94-164">См. также</span><span class="sxs-lookup"><span data-stu-id="a2b94-164">See also</span></span>

* [<span data-ttu-id="a2b94-165">Устранение неполадок при использовании средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="a2b94-165">Troubleshoot .NET Core tool usage issues</span></span>](troubleshoot-usage-issues.md)
