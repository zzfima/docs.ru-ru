---
title: Установка средства ML.NET CLI
description: Обзор и установка средства ML.NET CLI.
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 9560aa846a1aefabadbd7d4faf8bd306ba72e0de
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557860"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="d8d4c-103">Установка средства ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="d8d4c-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="d8d4c-104">Для создания качественных моделей и исходного кода ML.NET на основе предоставляемых наборов обучающих данных средство ML.NET CLI (программу командной строки) можно запускать в любой командной строке (Windows, Mac или Linux).</span><span class="sxs-lookup"><span data-stu-id="d8d4c-104">The ML.NET CLI (command-line interface) is a tool you can run on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on training datasets you provide.</span></span>

> [!NOTE]
> <span data-ttu-id="d8d4c-105">Этот раздел относится к ML.NET CLI и ML.NET AutoML, находящимся в данный момент в предварительной версии; материалы могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-105">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="d8d4c-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d8d4c-106">Pre-requisites</span></span>

- [<span data-ttu-id="d8d4c-107">Пакет SDK для .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="d8d4c-107">.NET Core 2.2 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- <span data-ttu-id="d8d4c-108">(Необязательно) [Visual Studio 2017 или 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="d8d4c-108">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="d8d4c-109">Вы можете запускать проекты, написанные на C#, из Visual Studio по нажатию F5 или с помощью `dotnet run` (.NET Core CLI).</span><span class="sxs-lookup"><span data-stu-id="d8d4c-109">You can either run the generated C# code projects with Visual Studio F5 or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="d8d4c-110">Примечание. Если после установки [пакета SDK для .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2) `dotnet tool` команда не работает, выйдите из Windows и снова войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-110">Note: If after installing [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="d8d4c-111">Установка</span><span class="sxs-lookup"><span data-stu-id="d8d4c-111">Install</span></span>

<span data-ttu-id="d8d4c-112">Средство ML.NET CLI устанавливается так же, как и любое другое глобальное средство .NET.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-112">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="d8d4c-113">Для этого используйте команду `dotnet tool install` .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-113">You use the `dotnet tool install` .NET Core CLI command.</span></span> 

<span data-ttu-id="d8d4c-114">В примере ниже показано, как установить ML.NET CLI в расположении веб-канала NuGet по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-114">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```console
> dotnet tool install -g mlnet
```

<span data-ttu-id="d8d4c-115">Если не удается установить средство (то есть оно недоступно в режиме по умолчанию веб-канала NuGet), отображаются сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-115">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="d8d4c-116">Убедитесь, что установлены флажки для нужных веб-каналов.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-116">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="d8d4c-117">Если установка выполнена успешно, отображается сообщение с командой, используемой для вызова средства, и установленной версией, аналогичное приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-117">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="d8d4c-118">Можно проверить успешность установки, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-118">You can confirm the installation was successful by typing the following command:</span></span>

```console
> mlnet
```

<span data-ttu-id="d8d4c-119">Вы увидите справку для команд, доступных для средства mlnet, например для команды auto-train.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-119">You should see the help for available commands for the mlnet tool such as the 'auto-train' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="d8d4c-120">Установка конкретного выпуска</span><span class="sxs-lookup"><span data-stu-id="d8d4c-120">Install a specific release version</span></span>

<span data-ttu-id="d8d4c-121">Если вам необходимо установить предварительную или конкретную версию средства, можно указать [платформу](../../standard/frameworks.md), используя следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-121">If you're trying to install a pre-release version or a specific version of the tool, you can specify the [framework](../../standard/frameworks.md) using the following format:</span></span>

```console
> dotnet tool install -g mlnet --framework <FRAMEWORK>
```

<span data-ttu-id="d8d4c-122">Вы также можете проверить, был ли пакет установлен правильно, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-122">You can also check if the package is properly installed by typing the following command:</span></span>

```console
> dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="d8d4c-123">Удаление пакета интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="d8d4c-123">Uninstall the CLI package</span></span>

<span data-ttu-id="d8d4c-124">Введите следующую команду, чтобы удалить пакет с локального компьютера:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-124">Type the following command to uninstall the package from your local machine:</span></span>

```console
> dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="d8d4c-125">Обновление пакета интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="d8d4c-125">Update the CLI package</span></span>

<span data-ttu-id="d8d4c-126">Введите следующую команду, чтобы обновить пакет на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-126">Type the following command to update the package from your local machine:</span></span>

```console
> dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="d8d4c-127">Настройка предложений CLI (автозавершение по нажатию TAB)</span><span class="sxs-lookup"><span data-stu-id="d8d4c-127">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="d8d4c-128">Так как средство ML.NET CLI основано на `System.CommandLine`, оно имеет встроенную поддержку нажатия клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-128">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="d8d4c-129">Пример того, как работает автоматическое завершение по нажатию клавиши TAB, см в следующей анимации:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-129">An example of how tab auto completion works is shown in the following animation:</span></span>

![изображение](./media/cli-tab-completion.gif)

<span data-ttu-id="d8d4c-131">Автозавершение клавишей TAB (варианты параметров) работает в *Windows PowerShell* и *bash для macOS и Linux*, но не будет работать в *командной строке Windows*.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-131">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="d8d4c-132">Чтобы включить его в текущей предварительной версии, конечный пользователь должен выполнить в каждой оболочке ряд однократных действий, описанных ниже.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-132">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="d8d4c-133">После этого варианты завершения будут работать для всех приложений, написанных с помощью `System.CommandLine`, например ML.NET CLI.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-133">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="d8d4c-134">На компьютере, где вы хотите включить завершение, необходимо сделать две вещи.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-134">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="d8d4c-135">Установите глобальное средство `dotnet-suggest`, запустив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-135">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```console
    > dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="d8d4c-136">Добавьте соответствующую оболочку совместимости к профилю оболочки.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-136">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="d8d4c-137">Может потребоваться создать файл профиля оболочки.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-137">You may have to create a shell profile file.</span></span> <span data-ttu-id="d8d4c-138">Скрипт оболочки совместимости перенаправит запрос завершения из оболочки в средство `dotnet-suggest`, которое делегирует его в соответствующее `System.CommandLine`-приложение.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-138">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    * <span data-ttu-id="d8d4c-139">Для bash следует добавить содержимое [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) в `~/.bash_profile`.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-139">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    * <span data-ttu-id="d8d4c-140">Для PowerShell следует добавить содержимое [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) в свой профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-140">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="d8d4c-141">Ожидаемый путь к профилю PowerShell можно получить, выполнив следующую команду в консоли:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-141">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    > echo $profile
    ``` 

<span data-ttu-id="d8d4c-142">(В других оболочках [найдите](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) или откройте [соответствующее обращение](https://github.com/dotnet/System.CommandLine/issues).)</span><span class="sxs-lookup"><span data-stu-id="d8d4c-142">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="d8d4c-143">Каталог установки</span><span class="sxs-lookup"><span data-stu-id="d8d4c-143">Installation directory</span></span>

<span data-ttu-id="d8d4c-144">ML.NET CLI можно установить в каталоге по умолчанию или в выбранном вами расположении.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-144">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="d8d4c-145">Каталоги по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="d8d4c-145">The default directories are:</span></span>

| <span data-ttu-id="d8d4c-146">Операционная система</span><span class="sxs-lookup"><span data-stu-id="d8d4c-146">OS</span></span>          | <span data-ttu-id="d8d4c-147">Путь</span><span class="sxs-lookup"><span data-stu-id="d8d4c-147">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="d8d4c-148">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="d8d4c-148">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="d8d4c-149">Windows</span><span class="sxs-lookup"><span data-stu-id="d8d4c-149">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="d8d4c-150">Эти расположения добавляются в путь пользователя при первом запуске пакета SDK, поэтому установленные в них глобальные средства можно вызывать напрямую.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-150">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="d8d4c-151">Обратите внимание, что глобальные средства входят в область конкретного пользователя, а не глобальную область компьютера.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-151">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="d8d4c-152">Таким образом, нельзя установить глобальное средство, которое будет доступно для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-152">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="d8d4c-153">Средство доступно только для тех профилей пользователей, в которых оно установлено.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-153">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="d8d4c-154">Глобальные средства также можно установить в конкретном каталоге.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-154">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="d8d4c-155">При установке в конкретном каталоге необходимо убедиться, что команда доступна, включив этот каталог в путь, вызвав команду с указанным каталогом или вызвав средство из указанного каталога.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-155">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="d8d4c-156">В этом случае .NET Core CLI не добавляет это расположение автоматически в переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="d8d4c-156">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8d4c-157">См. также</span><span class="sxs-lookup"><span data-stu-id="d8d4c-157">See also</span></span>

- [<span data-ttu-id="d8d4c-158">Руководство по началу работы со средством ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="d8d4c-158">Tutorial on 'Getting Started with ML.NET CLI tool'</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="d8d4c-159">Автоматическое обучение моделей с помощью средства ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="d8d4c-159">How to automatically train models with the ML.NET CLI tool</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="d8d4c-160">Справочное руководство по команде auto-train в ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="d8d4c-160">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md) 
- [<span data-ttu-id="d8d4c-161">Данные телеметрии в интерфейсе командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="d8d4c-161">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
