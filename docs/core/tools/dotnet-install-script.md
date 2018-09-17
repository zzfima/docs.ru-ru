---
title: Скрипты dotnet-install
description: Сведения о скриптах dotnet-install, которые служат для установки средств CLI .NET Core и общей среды выполнения.
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.openlocfilehash: 8d1c6ebb30bd45575bb61206799c9c3e5c47ff0c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45678325"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="da9ec-103">Справка по скриптам dotnet-install</span><span class="sxs-lookup"><span data-stu-id="da9ec-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="da9ec-104">name</span><span class="sxs-lookup"><span data-stu-id="da9ec-104">Name</span></span>

<span data-ttu-id="da9ec-105">`dotnet-install.ps1` | `dotnet-install.sh` — скрипт, используемый для установки общей среды выполнения и средств .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="da9ec-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="da9ec-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="da9ec-106">Synopsis</span></span>

<span data-ttu-id="da9ec-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="da9ec-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="da9ec-108">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="da9ec-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="da9ec-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="da9ec-109">Description</span></span>

<span data-ttu-id="da9ec-110">Скрипты `dotnet-install` используются для установки пакета SDK для .NET Core без прав администратора. Этот пакет включает общую среду выполнения и средства .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="da9ec-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="da9ec-111">Мы рекомендуем использовать стабильную версию, размещенную на [основном веб-сайте .NET Core](https://dot.net).</span><span class="sxs-lookup"><span data-stu-id="da9ec-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="da9ec-112">Прямые пути к скриптам:</span><span class="sxs-lookup"><span data-stu-id="da9ec-112">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="da9ec-113">https://dot.net/v1/dotnet-install.sh (Bash, UNIX);</span><span class="sxs-lookup"><span data-stu-id="da9ec-113">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="da9ec-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows).</span><span class="sxs-lookup"><span data-stu-id="da9ec-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="da9ec-115">Их основное назначение — помощь в сценариях автоматизации и при установках без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="da9ec-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="da9ec-116">Существует два скрипта. Один — скрипт PowerShell, который работает в Windows.</span><span class="sxs-lookup"><span data-stu-id="da9ec-116">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="da9ec-117">Второй — bash-скрипт, который выполняется в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="da9ec-117">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="da9ec-118">Оба скрипта выполняют одни и те же функции.</span><span class="sxs-lookup"><span data-stu-id="da9ec-118">Both scripts have the same behavior.</span></span> <span data-ttu-id="da9ec-119">Так как bash-скрипт также считывает параметры PowerShell, их можно использовать с этим скриптом в системах Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="da9ec-119">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="da9ec-120">Скрипты установки скачивают файл ZIP или TAR из места сборки CLI, а затем осуществляют установку в расположении по умолчанию или расположении, заданном параметром `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-120">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="da9ec-121">По умолчанию скрипты установки скачивают и устанавливают пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="da9ec-121">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="da9ec-122">Если вы хотите получить только общую среду выполнения, укажите аргумент `--shared-runtime`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-122">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span>

<span data-ttu-id="da9ec-123">По умолчанию скрипт добавляет место установки в переменную $PATH для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="da9ec-123">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="da9ec-124">Переопределите это поведение по умолчанию, указав аргумент `--no-path`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-124">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="da9ec-125">Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="da9ec-125">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="da9ec-126">Вы можете установить конкретную версию с помощью аргумента `--version`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-126">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="da9ec-127">Версию следует указывать в виде трехкомпонентного номера (например, 1.0.0-13232).</span><span class="sxs-lookup"><span data-stu-id="da9ec-127">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="da9ec-128">Если она не указана, используется версия `latest`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-128">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="da9ec-129">Параметры</span><span class="sxs-lookup"><span data-stu-id="da9ec-129">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="da9ec-130">Указывает исходный канал для установки.</span><span class="sxs-lookup"><span data-stu-id="da9ec-130">Specifies the source channel for the installation.</span></span> <span data-ttu-id="da9ec-131">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="da9ec-131">The possible values are:</span></span>

- <span data-ttu-id="da9ec-132">`Current` — текущий выпуск.</span><span class="sxs-lookup"><span data-stu-id="da9ec-132">`Current` - Current release</span></span>
- <span data-ttu-id="da9ec-133">`LTS` — канал долгосрочной поддержки (текущий поддерживаемый выпуск).</span><span class="sxs-lookup"><span data-stu-id="da9ec-133">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="da9ec-134">Версия из двух частей в формате X.Y, который представляет конкретный выпуск (например, `2.0` или `1.0`).</span><span class="sxs-lookup"><span data-stu-id="da9ec-134">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="da9ec-135">Имя ветви [например, `release/2.0.0`, `release/2.0.0-preview2` или `master` для последней из ветви `master` ("суперсовременные" ночные выпуски)].</span><span class="sxs-lookup"><span data-stu-id="da9ec-135">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="da9ec-136">Значение по умолчанию — `LTS`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-136">The default value is `LTS`.</span></span> <span data-ttu-id="da9ec-137">Дополнительные сведения о каналах поддержки .NET см. в документе [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) (Жизненный цикл поддержки .NET Core).</span><span class="sxs-lookup"><span data-stu-id="da9ec-137">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="da9ec-138">Представляет определенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="da9ec-138">Represents a specific build version.</span></span> <span data-ttu-id="da9ec-139">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="da9ec-139">The possible values are:</span></span>

- <span data-ttu-id="da9ec-140">`latest` — последняя сборка в канале (используется с параметром `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="da9ec-140">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="da9ec-141">`coherent` — последняя согласованная сборка в канале. Использует последние сочетания стабильных пакетов. (Используется с параметрами `-Channel` имени ветви.)</span><span class="sxs-lookup"><span data-stu-id="da9ec-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="da9ec-142">Версия из трех частей в формате X.Y.Z, который представляет определенную версию сборки. Заменяет параметр `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="da9ec-143">Пример: `2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="da9ec-143">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="da9ec-144">Если значение не указано, для параметра `-Version` по умолчанию используется значение `latest`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-144">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="da9ec-145">Указывает путь установки.</span><span class="sxs-lookup"><span data-stu-id="da9ec-145">Specifies the installation path.</span></span> <span data-ttu-id="da9ec-146">Если такого пути нет, создается каталог.</span><span class="sxs-lookup"><span data-stu-id="da9ec-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="da9ec-147">Значение по умолчанию — *%LocalAppData%\.dotnet*.</span><span class="sxs-lookup"><span data-stu-id="da9ec-147">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="da9ec-148">Обратите внимание, что двоичные файлы помещаются непосредственно в каталог.</span><span class="sxs-lookup"><span data-stu-id="da9ec-148">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="da9ec-149">Архитектура устанавливаемых двоичных файлов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="da9ec-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="da9ec-150">Допустимые значения: `auto`, `x64` и `x86`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-150">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="da9ec-151">Значение по умолчанию — `auto`, представляющее текущую используемую архитектуру ОС.</span><span class="sxs-lookup"><span data-stu-id="da9ec-151">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="da9ec-152">Если параметр задан, он ограничивает установку общей средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="da9ec-152">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="da9ec-153">Установка всего пакета SDK не выполняется.</span><span class="sxs-lookup"><span data-stu-id="da9ec-153">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="da9ec-154">Если значение задано, скрипт не будет выполнять установку. Вместо этого отобразится командная строка для согласованной установки запрошенной в настоящее время версии CLI .NET Core.</span><span class="sxs-lookup"><span data-stu-id="da9ec-154">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="da9ec-155">Например, если указать версию `latest`, он отображает ссылку для определенной версии, чтобы эту команду можно было детерминировано использовать в скрипте сборки.</span><span class="sxs-lookup"><span data-stu-id="da9ec-155">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="da9ec-156">Кроме того, он отображает расположение двоичного файла, если вы хотите выполнить скачивание или установку самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="da9ec-156">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="da9ec-157">Если значение задано, префикс и каталог установки не экспортируются в путь текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="da9ec-157">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="da9ec-158">По умолчанию скрипт изменит значение PATH, благодаря этому средства CLI становятся доступными сразу после установки.</span><span class="sxs-lookup"><span data-stu-id="da9ec-158">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="da9ec-159">Указывает URL-адрес для веб-канала Azure этого установщика.</span><span class="sxs-lookup"><span data-stu-id="da9ec-159">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="da9ec-160">Изменять это значение не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="da9ec-160">It isn't recommended that you change this value.</span></span> <span data-ttu-id="da9ec-161">Значение по умолчанию — `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="da9ec-161">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="da9ec-162">Если значение задано, установщик использует прокси-сервер для выполнения веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="da9ec-162">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="da9ec-163">(Доступно только для Windows.)</span><span class="sxs-lookup"><span data-stu-id="da9ec-163">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="da9ec-164">Отображение сведений о диагностике.</span><span class="sxs-lookup"><span data-stu-id="da9ec-164">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="da9ec-165">Выводит справку для скрипта.</span><span class="sxs-lookup"><span data-stu-id="da9ec-165">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="da9ec-166">Примеры</span><span class="sxs-lookup"><span data-stu-id="da9ec-166">Examples</span></span>

<span data-ttu-id="da9ec-167">Установка последней версии с долгосрочной поддержкой (LTS) в расположение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="da9ec-167">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="da9ec-168">Windows:</span><span class="sxs-lookup"><span data-stu-id="da9ec-168">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="da9ec-169">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="da9ec-169">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="da9ec-170">Установка последней версии из канала версии 2.0 в указанное расположение:</span><span class="sxs-lookup"><span data-stu-id="da9ec-170">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="da9ec-171">Windows:</span><span class="sxs-lookup"><span data-stu-id="da9ec-171">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="da9ec-172">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="da9ec-172">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="da9ec-173">Установка общей среды выполнения версии 1.1.0:</span><span class="sxs-lookup"><span data-stu-id="da9ec-173">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="da9ec-174">Windows:</span><span class="sxs-lookup"><span data-stu-id="da9ec-174">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="da9ec-175">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="da9ec-175">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="da9ec-176">Получите скрипт и установите однострочные примеры для интерфейса командной строки .NET Core:</span><span class="sxs-lookup"><span data-stu-id="da9ec-176">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="da9ec-177">Windows:</span><span class="sxs-lookup"><span data-stu-id="da9ec-177">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="da9ec-178">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="da9ec-178">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="da9ec-179">См. также</span><span class="sxs-lookup"><span data-stu-id="da9ec-179">See also</span></span>

* [<span data-ttu-id="da9ec-180">Выпуски .NET Core</span><span class="sxs-lookup"><span data-stu-id="da9ec-180">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
* [<span data-ttu-id="da9ec-181">Архив загрузки пакета SDK и среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="da9ec-181">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
