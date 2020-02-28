---
title: Средства .NET Core
description: Установка, использование, обновление и удаление средств .NET Core. Содержит сведения о глобальных средствах, средствах пути к средству и локальных средствах.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: d8ee30df3fe063fd41a85072d145b1b5eec7d0d0
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543395"
---
# <a name="how-to-manage-net-core-tools"></a><span data-ttu-id="f1cc8-104">Управление средствами .NET Core</span><span class="sxs-lookup"><span data-stu-id="f1cc8-104">How to manage .NET Core tools</span></span>

<span data-ttu-id="f1cc8-105">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f1cc8-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="f1cc8-106">Средство .NET Core — это специальный пакет NuGet, который содержит консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-106">A .NET Core tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="f1cc8-107">Средство можно установить на компьютере следующими способами.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-107">A tool can be installed on your machine in the following ways:</span></span>

* <span data-ttu-id="f1cc8-108">Как глобальное средство.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-108">As a global tool.</span></span>

  <span data-ttu-id="f1cc8-109">Двоичные файлы инструментов устанавливаются в каталог по умолчанию, который добавляется в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-109">The tool binaries are installed in a default directory that is added to the PATH environment variable.</span></span> <span data-ttu-id="f1cc8-110">Это средство можно вызвать из любого каталога на компьютере, не указывая его расположение.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-110">You can invoke the tool from any directory on the machine without specifying its location.</span></span> <span data-ttu-id="f1cc8-111">Для всех каталогов на компьютере используется одна версия средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-111">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="f1cc8-112">В качестве глобального средства в пользовательском расположении (также известном как средство пути к средству).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-112">As a global tool in a custom location (also known as a tool-path tool).</span></span>

  <span data-ttu-id="f1cc8-113">Двоичные файлы средств устанавливаются в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-113">The tool binaries are installed in a location that you specify.</span></span> <span data-ttu-id="f1cc8-114">Вы можете вызвать средство из каталога установки, предоставив каталог с именем команды или добавив каталог в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-114">You can invoke the tool from the installation directory or by providing the directory with the command name or by adding the directory to the PATH environment variable.</span></span> <span data-ttu-id="f1cc8-115">Для всех каталогов на компьютере используется одна версия средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-115">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="f1cc8-116">В качестве локального средства (применяется к пакету SDK для .NET Core 3.0 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-116">As a local tool (applies to .NET Core SDK 3.0 and later).</span></span>

  <span data-ttu-id="f1cc8-117">Двоичные файлы средств устанавливаются в каталог по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-117">The tool binaries are installed in a default directory.</span></span> <span data-ttu-id="f1cc8-118">Средство вызывается из каталога установки или любого из его подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-118">You invoke the tool from the installation directory or any of its subdirectories.</span></span> <span data-ttu-id="f1cc8-119">Разные каталоги могут использовать разные версии одного и того же средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-119">Different directories can use different versions of the same tool.</span></span>
  
  <span data-ttu-id="f1cc8-120">В .NET CLI для наблюдения за тем, какие средства устанавливаются для каталога в качестве локальных, используются файлы манифеста.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-120">The .NET CLI uses manifest files to keep track of which tools are installed as local to a directory.</span></span> <span data-ttu-id="f1cc8-121">Когда файл манифеста сохраняется в корневом каталоге репозитория исходного кода, участник может клонировать репозиторий и вызвать одну команду CLI .NET Core, которая устанавливает все средства, перечисленные в файлах манифеста.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-121">When the manifest file is saved in the root directory of a source code repository, a contributor can clone the repository and invoke a single .NET Core CLI command that installs all of the tools listed in the manifest files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1cc8-122">Средства .NET Core выполняются с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-122">.NET Core tools run in full trust.</span></span> <span data-ttu-id="f1cc8-123">Не устанавливайте средства .NET Core, если вы не доверяете автору.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-123">Do not install a .NET Core tool unless you trust the author.</span></span>

## <a name="find-a-tool"></a><span data-ttu-id="f1cc8-124">Поиск средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-124">Find a tool</span></span>

<span data-ttu-id="f1cc8-125">В настоящее время в .NET Core отсутствует функция поиска средств.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-125">Currently, .NET Core doesn't have a tool search feature.</span></span> <span data-ttu-id="f1cc8-126">Ниже приведены некоторые способы поиска средств.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-126">Here are some ways to find tools:</span></span>

* <span data-ttu-id="f1cc8-127">См. список средств в репозитории GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-127">See the list of tools in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="f1cc8-128">Используйте для поиска средств .NET [ToolGet](https://www.toolget.net/).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-128">Use [ToolGet](https://www.toolget.net/) to search for .NET tools.</span></span>
* <span data-ttu-id="f1cc8-129">См. исходный код для средств, созданных командой разработчиков ASP.NET Core в [каталоге средств репозитория GitHub dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-129">See the source code for the tools created by the ASP.NET Core team in the [Tools directory of the dotnet/aspnetcore GitHub repository](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span></span>
* <span data-ttu-id="f1cc8-130">Дополнительные сведения о средствах диагностики см. в разделе [Глобальные средства диагностики dotnet в .NET Core](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-130">Learn about diagnostic tools at [.NET Core dotnet diagnostic tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>
* <span data-ttu-id="f1cc8-131">Найдите веб-сайт [NuGet](https://www.nuget.org).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-131">Search the [NuGet](https://www.nuget.org) website.</span></span> <span data-ttu-id="f1cc8-132">Однако у сайта NuGet еще нет функции, которая позволяет искать только пакеты средств.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-132">However, the NuGet site doesn't yet have a feature that lets you search only for tool packages.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="f1cc8-133">Проверка автора и статистики</span><span class="sxs-lookup"><span data-stu-id="f1cc8-133">Check the author and statistics</span></span>

<span data-ttu-id="f1cc8-134">Поскольку средства .NET Core работают в режиме полного доверия, а глобальные средства добавляются в переменную среды PATH, они могут быть очень мощными.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-134">Since .NET Core tools run in full trust, and global tools are added to the PATH environment variable, they can be very powerful.</span></span> <span data-ttu-id="f1cc8-135">Не скачивайте средства авторов, которым вы не доверяете.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-135">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="f1cc8-136">Если средство размещается в NuGet, вы можете проверить автора и статистику, выполнив поиск средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-136">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="f1cc8-137">Установка глобального средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-137">Install a global tool</span></span>

<span data-ttu-id="f1cc8-138">Чтобы установить средство в качестве глобального средства, используйте `-g` или опцию `--global` [установки средства dotnet](dotnet-tool-install.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-138">To install a tool as a global tool, use the `-g` or `--global` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following example:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="f1cc8-139">В выходных данных отображается команда, используемая для вызова средства и установленной версии, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-139">The output shows the command used to invoke the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

<span data-ttu-id="f1cc8-140">Расположение двоичных файлов средства по умолчанию зависит от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-140">The default location for a tool's binaries depends on the operating system:</span></span>

| <span data-ttu-id="f1cc8-141">Операционная система</span><span class="sxs-lookup"><span data-stu-id="f1cc8-141">OS</span></span>          | <span data-ttu-id="f1cc8-142">Path</span><span class="sxs-lookup"><span data-stu-id="f1cc8-142">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="f1cc8-143">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="f1cc8-143">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="f1cc8-144">Windows</span><span class="sxs-lookup"><span data-stu-id="f1cc8-144">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="f1cc8-145">Это расположение добавляется к пути пользователя при первом запуске пакета SDK, поэтому глобальные средства можно вызывать из любого каталога, не указывая расположение средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-145">This location is added to the user's path when the SDK is first run, so global tools can be invoked from any directory without specifying the tool location.</span></span>

<span data-ttu-id="f1cc8-146">Доступ к средству зависит от конкретного пользователя, а не от глобального компьютера.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-146">Tool access is user-specific, not machine global.</span></span> <span data-ttu-id="f1cc8-147">Глобальное средство доступно только для пользователя, установившего средство.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-147">A global tool is only available to the user that installed the tool.</span></span>

### <a name="install-a-global-tool-in-a-custom-location"></a><span data-ttu-id="f1cc8-148">Установка глобального средства в пользовательском расположении</span><span class="sxs-lookup"><span data-stu-id="f1cc8-148">Install a global tool in a custom location</span></span>

<span data-ttu-id="f1cc8-149">Чтобы установить средство в качестве глобального средства в пользовательском расположении, используйте опцию `--tool-path` [установки средства dotnet](dotnet-tool-install.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-149">To install a tool as a global tool in a custom location, use the `--tool-path` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following examples.</span></span>

<span data-ttu-id="f1cc8-150">Windows:</span><span class="sxs-lookup"><span data-stu-id="f1cc8-150">On Windows:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

<span data-ttu-id="f1cc8-151">В Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-151">On Linux or macOS:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

<span data-ttu-id="f1cc8-152">Пакет SDK для .NET Core не добавляет это расположение автоматически в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-152">The .NET Core SDK doesn't add this location automatically to the PATH environment variable.</span></span> <span data-ttu-id="f1cc8-153">Чтобы [вызвать средство пути к средству](#invoke-a-tool-path-tool), необходимо убедиться, что команда доступна с помощью одного из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-153">To [invoke a tool-path tool](#invoke-a-tool-path-tool), you have to make sure the command is available by using one of the following methods:</span></span>

* <span data-ttu-id="f1cc8-154">Добавьте каталог установки в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-154">Add the installation directory to the PATH environment variable.</span></span>
* <span data-ttu-id="f1cc8-155">При вызове средства следует указать полный путь к нему.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-155">Specify the full path to the tool when you invoke it.</span></span>
* <span data-ttu-id="f1cc8-156">Вызовите средство из каталога установки.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-156">Invoke the tool from within the installation directory.</span></span>

## <a name="install-a-local-tool"></a><span data-ttu-id="f1cc8-157">Установка локального средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-157">Install a local tool</span></span>

<span data-ttu-id="f1cc8-158">**Применимо к пакету SDK для .NET Core 3.0 и более поздних версий.**</span><span class="sxs-lookup"><span data-stu-id="f1cc8-158">**Applies to .NET Core 3.0 SDK and later.**</span></span>

<span data-ttu-id="f1cc8-159">Чтобы установить средство только для локального доступа (для текущего каталога и подкаталогов), его необходимо добавить в файл манифеста средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-159">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a tool manifest file.</span></span> <span data-ttu-id="f1cc8-160">Чтобы создать файл манифеста средства, выполните команду `dotnet new tool-manifest`:</span><span class="sxs-lookup"><span data-stu-id="f1cc8-160">To create a tool manifest file, run the `dotnet new tool-manifest` command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="f1cc8-161">Эта команда создает файл манифеста с именем *dotnet-tools.json* в каталоге *.config*.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-161">This command creates a manifest file named *dotnet-tools.json* under the *.config* directory.</span></span> <span data-ttu-id="f1cc8-162">Для добавления локального средства в файл манифеста используйте команду [dotnet tool install](dotnet-tool-install.md) и **omit** опции `--global` и `--tool-path`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-162">To add a local tool to the manifest file, use the [dotnet tool install](dotnet-tool-install.md) command and **omit** the `--global` and `--tool-path` options, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay
```

<span data-ttu-id="f1cc8-163">Вывод команды показывает, в каком файле манифеста находится только что установленное средство, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-163">The command output shows which manifest file the newly installed tool is in, similar to the following example:</span></span>

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

<span data-ttu-id="f1cc8-164">В следующем примере показан файл манифеста с двумя установленными локальными средствами.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-164">The following example shows a manifest file with two local tools installed:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

<span data-ttu-id="f1cc8-165">Обычно вы добавляете локальное средство в корневой каталог репозитория.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-165">You typically add a local tool to the root directory of the repository.</span></span> <span data-ttu-id="f1cc8-166">После записи файла манифеста в репозиторий после изменения, разработчики, извлекающие код из репозитория, получают последний файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-166">After you check in the manifest file to the repository, developers who check out code from the repository get the latest manifest file.</span></span> <span data-ttu-id="f1cc8-167">Чтобы установить все средства, перечисленные в файле манифеста, они запускают команду `dotnet tool restore`:</span><span class="sxs-lookup"><span data-stu-id="f1cc8-167">To install all of the tools listed in the manifest file, they run the `dotnet tool restore` command:</span></span>

```dotnetcli
dotnet tool restore
```

<span data-ttu-id="f1cc8-168">Вывод показывает, какие инструменты восстановлены:</span><span class="sxs-lookup"><span data-stu-id="f1cc8-168">The output indicates which tools were restored:</span></span>

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a><span data-ttu-id="f1cc8-169">Установка конкретной версии средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-169">Install a specific tool version</span></span>

<span data-ttu-id="f1cc8-170">Чтобы установить предварительную или конкретную версию средства, укажите номер версии, используя параметр `--version`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f1cc8-170">To install a pre-release version or a specific version of a tool, specify the version number by using the `--version` option, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a><span data-ttu-id="f1cc8-171">Использование средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-171">Use a tool</span></span>

<span data-ttu-id="f1cc8-172">Команда, которую вы используете для вызова средства, может отличаться от названия пакета, который вы устанавливаете.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-172">The command that you use to invoke a tool may be different from the name of the package that you install.</span></span> <span data-ttu-id="f1cc8-173">Чтобы отобразить все средства, установленные на компьютере для текущего пользователя, используйте команду [dotnet tool list](dotnet-tool-list.md):</span><span class="sxs-lookup"><span data-stu-id="f1cc8-173">To display all of the tools currently installed on the machine for the current user, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list
```

<span data-ttu-id="f1cc8-174">На выходе показаны версия и команда каждого средства, аналогично следующему примеру.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-174">The output shows each tool's version and command, similar to the following example:</span></span>

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

<span data-ttu-id="f1cc8-175">Как показано в этом примере, список показывает локальные средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-175">As shown in this example, the list shows local tools.</span></span> <span data-ttu-id="f1cc8-176">Для просмотра глобальных средств используйте параметр `--global`, а для просмотра средства пути к средствам — `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-176">To see global tools, use the `--global` option, and to see tool-path tools, use the `--tool-path` option.</span></span>

### <a name="invoke-a-global-tool"></a><span data-ttu-id="f1cc8-177">Вызов глобального инструмента</span><span class="sxs-lookup"><span data-stu-id="f1cc8-177">Invoke a global tool</span></span>

<span data-ttu-id="f1cc8-178">Для глобальных средств используйте команду средства самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-178">For global tools, use the tool command by itself.</span></span> <span data-ttu-id="f1cc8-179">Например, если команда `dotnetsay` или `dotnet-doc`, это то, что вы используете для вызова команды.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-179">For example, if the command is `dotnetsay` or `dotnet-doc`, that's what you use to invoke the command:</span></span>

```console
dotnetsay
dotnet-doc
```

<span data-ttu-id="f1cc8-180">Если команда начинается с префикса `dotnet-`, альтернативный способ вызова средства — использование команды `dotnet` и опускание префикса команды средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-180">If the command begins with the prefix `dotnet-`, an alternative way to invoke the tool is to use the `dotnet` command and omit the tool command prefix.</span></span> <span data-ttu-id="f1cc8-181">Например, если команда `dotnet-doc`, то средство вызывает следующая команда.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-181">For example, if the command is `dotnet-doc`, the following command invokes the tool:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="f1cc8-182">Однако в следующем сценарии для вызова глобального средства нельзя использовать команду `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="f1cc8-182">However, in the following scenario you can't use the `dotnet` command to invoke a global tool:</span></span>

* <span data-ttu-id="f1cc8-183">Глобальное и локальное средство имеют одну и ту же команду с префиксом `dotnet-`.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-183">A global tool and a local tool have the same command prefixed by `dotnet-`.</span></span>
* <span data-ttu-id="f1cc8-184">Вы хотите вызвать глобальное средство из каталога, находящегося в области действия локального средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-184">You want to invoke the global tool from a directory that is in scope for the local tool.</span></span>

<span data-ttu-id="f1cc8-185">В этом сценарии локальное средство вызывают `dotnet doc` и `dotnet dotnet-doc`.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-185">In this scenario, `dotnet doc` and `dotnet dotnet-doc` invoke the local tool.</span></span> <span data-ttu-id="f1cc8-186">Чтобы вызвать глобальное средство, используйте команду самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-186">To invoke the global tool, use the command by itself:</span></span>

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a><span data-ttu-id="f1cc8-187">Вызов средства пути к средству</span><span class="sxs-lookup"><span data-stu-id="f1cc8-187">Invoke a tool-path tool</span></span>

<span data-ttu-id="f1cc8-188">Для вызова глобального средства, которое устанавливается с помощью опции `tool-path`, убедитесь, что команда доступна, как объяснялось [ранее в этой статье](#install-a-global-tool-in-a-custom-location).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-188">To invoke a global tool that is installed by using the `tool-path` option, make sure the command is available, as explained [earlier in this article](#install-a-global-tool-in-a-custom-location).</span></span>

### <a name="invoke-a-local-tool"></a><span data-ttu-id="f1cc8-189">Вызов локального средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-189">Invoke a local tool</span></span>

<span data-ttu-id="f1cc8-190">Для вызова локального средства необходимо использовать команду `dotnet` из каталога установки.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-190">To invoke a local tool, you have to use the `dotnet` command from within the installation directory.</span></span> <span data-ttu-id="f1cc8-191">Вы можете использовать длинную (`dotnet tool run <COMMAND_NAME>`) или короткую (`dotnet <COMMAND_NAME>`) форму, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-191">You can use the long form (`dotnet tool run <COMMAND_NAME>`) or the short form (`dotnet <COMMAND_NAME>`), as shown in the following examples:</span></span>

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

<span data-ttu-id="f1cc8-192">Если команда имеет префикс `dotnet-`, вы можете включить или исключить префикс при вызове средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-192">If the command is prefixed by `dotnet-`, you can include or omit the prefix when you invoke the tool.</span></span> <span data-ttu-id="f1cc8-193">Например, если команда `dotnet-doc`, то локальное средство вызовет любой из следующих примеров.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-193">For example, if the command is `dotnet-doc`, any of the following examples invokes the local tool:</span></span>

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a><span data-ttu-id="f1cc8-194">Обновление средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-194">Update a tool</span></span>

<span data-ttu-id="f1cc8-195">Обновление средства подразумевает его удаление и установку последней стабильной версии.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-195">Updating a tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="f1cc8-196">Для обновления средства используйте команду [dotnet tool update](dotnet-tool-update.md) с той же опцией, что и при установке средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-196">To update a tool, use the [dotnet tool update](dotnet-tool-update.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

<span data-ttu-id="f1cc8-197">Для локального средства пакет SDK находит первый файл манифеста, который содержит идентификатор пакета, выполнив поиск в текущем и родительском каталоге.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-197">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span> <span data-ttu-id="f1cc8-198">Если такой идентификатор пакета отсутствует в любом файле манифеста, пакет SDK добавляет новую запись в ближайший файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-198">If there is no such package ID in any manifest file, the SDK adds a new entry to the closest manifest file.</span></span>

## <a name="uninstall-a-tool"></a><span data-ttu-id="f1cc8-199">Удаление средства</span><span class="sxs-lookup"><span data-stu-id="f1cc8-199">Uninstall a tool</span></span>

<span data-ttu-id="f1cc8-200">Удалите инструмент с помощью команды [dotnet tool uninstall](dotnet-tool-uninstall.md) с той же опцией, которую вы использовали для установки средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-200">Remove a tool by using the [dotnet tool uninstall](dotnet-tool-uninstall.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path<packagename>
dotnet tool uninstall <packagename>
```

<span data-ttu-id="f1cc8-201">Для локального средства пакет SDK находит первый файл манифеста, который содержит идентификатор пакета, выполнив поиск в текущем и родительском каталоге.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-201">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span>

## <a name="get-help-and-troubleshoot"></a><span data-ttu-id="f1cc8-202">Получение справки и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f1cc8-202">Get help and troubleshoot</span></span>

<span data-ttu-id="f1cc8-203">Чтобы получить список доступных команд `dotnet tool`, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-203">To get a list of available `dotnet tool` commands, enter the following command:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="f1cc8-204">Чтобы получить инструкции по использованию средства, введите одну из следующих команд или посетите веб-сайт средства.</span><span class="sxs-lookup"><span data-stu-id="f1cc8-204">To get tool usage instructions, enter one of the following commands or see the tool's website:</span></span>

```dotnetcli
<command> --help
dotnet <command> --help
```

<span data-ttu-id="f1cc8-205">Если средство не удается установить или запустить, см. статью [Устранение неполадок при использовании средства .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f1cc8-205">If a tool fails to install or run, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>
