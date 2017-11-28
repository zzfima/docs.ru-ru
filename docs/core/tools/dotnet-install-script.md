---
title: "Скрипты dotnet-install"
description: "Сведения о скриптах dotnet-install, которые служат для установки средств CLI .NET Core и общей среды выполнения."
keywords: "dotnet-install, скрипты dotnet-install, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.openlocfilehash: 2f15f37016fe824d76b501e4793e0b28bbdbe167
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="0cd38-104">Справка по скриптам dotnet-install</span><span class="sxs-lookup"><span data-stu-id="0cd38-104">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="0cd38-105">Имя</span><span class="sxs-lookup"><span data-stu-id="0cd38-105">Name</span></span>

<span data-ttu-id="0cd38-106">`dotnet-install.ps1` | `dotnet-install.sh` — скрипт, используемый для установки общей среды выполнения и средств .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="0cd38-106">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0cd38-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0cd38-107">Synopsis</span></span>

<span data-ttu-id="0cd38-108">Windows:</span><span class="sxs-lookup"><span data-stu-id="0cd38-108">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="0cd38-109">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="0cd38-109">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="0cd38-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0cd38-110">Description</span></span>

<span data-ttu-id="0cd38-111">Скрипты `dotnet-install` используются для установки пакета SDK для .NET Core без прав администратора. Этот пакет включает общую среду выполнения и средства .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="0cd38-111">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="0cd38-112">Мы рекомендуем использовать стабильную версию, размещенную на [основном веб-сайте .NET Core](https://dot.net).</span><span class="sxs-lookup"><span data-stu-id="0cd38-112">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="0cd38-113">Прямые пути к скриптам:</span><span class="sxs-lookup"><span data-stu-id="0cd38-113">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="0cd38-114">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="0cd38-114">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="0cd38-115">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="0cd38-115">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="0cd38-116">Их основное назначение — помощь в сценариях автоматизации и при установках без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="0cd38-116">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="0cd38-117">Существует два скрипта. Один — скрипт PowerShell, который работает в Windows.</span><span class="sxs-lookup"><span data-stu-id="0cd38-117">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="0cd38-118">Второй — bash-скрипт, который выполняется в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="0cd38-118">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="0cd38-119">Оба скрипта выполняют одни и те же функции.</span><span class="sxs-lookup"><span data-stu-id="0cd38-119">Both scripts have the same behavior.</span></span> <span data-ttu-id="0cd38-120">Так как bash-скрипт также считывает параметры PowerShell, их можно использовать с этим скриптом в системах Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="0cd38-120">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span> 

<span data-ttu-id="0cd38-121">Скрипты установки скачивают файл ZIP или TAR из места сборки CLI, а затем осуществляют установку в расположении по умолчанию или расположении, заданном параметром `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-121">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="0cd38-122">По умолчанию скрипты установки скачивают и устанавливают пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="0cd38-122">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="0cd38-123">Если вы хотите получить только общую среду выполнения, укажите аргумент `--shared-runtime`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-123">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span> 

<span data-ttu-id="0cd38-124">По умолчанию скрипт добавляет место установки в переменную $PATH для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="0cd38-124">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="0cd38-125">Переопределите это поведение по умолчанию, указав аргумент `--no-path`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-125">Override this default behavior by specifying the `--no-path` argument.</span></span> 

<span data-ttu-id="0cd38-126">Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="0cd38-126">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="0cd38-127">Вы можете установить конкретную версию с помощью аргумента `--version`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-127">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="0cd38-128">Версию следует указывать в виде трехкомпонентного номера (например, 1.0.0-13232).</span><span class="sxs-lookup"><span data-stu-id="0cd38-128">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="0cd38-129">Если она не указана, используется версия `latest`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-129">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="0cd38-130">Параметры</span><span class="sxs-lookup"><span data-stu-id="0cd38-130">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="0cd38-131">Указывает исходный канал для установки.</span><span class="sxs-lookup"><span data-stu-id="0cd38-131">Specifies the source channel for the installation.</span></span> <span data-ttu-id="0cd38-132">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0cd38-132">The possible values are:</span></span>

- <span data-ttu-id="0cd38-133">`Current` — текущий выпуск.</span><span class="sxs-lookup"><span data-stu-id="0cd38-133">`Current` - Current release</span></span>
- <span data-ttu-id="0cd38-134">`LTS` — канал долгосрочной поддержки (текущий поддерживаемый выпуск).</span><span class="sxs-lookup"><span data-stu-id="0cd38-134">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="0cd38-135">Версия из двух частей в формате X.Y, который представляет конкретный выпуск (например, `2.0` или `1.0`).</span><span class="sxs-lookup"><span data-stu-id="0cd38-135">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="0cd38-136">Имя ветви [например, `release/2.0.0`, `release/2.0.0-preview2` или `master` для последней из ветви `master` ("суперсовременные" ночные выпуски)].</span><span class="sxs-lookup"><span data-stu-id="0cd38-136">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="0cd38-137">Значение по умолчанию — `LTS`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-137">The default value is `LTS`.</span></span> <span data-ttu-id="0cd38-138">Дополнительные сведения о каналах поддержки .NET см. в документе [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) (Жизненный цикл поддержки .NET Core).</span><span class="sxs-lookup"><span data-stu-id="0cd38-138">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="0cd38-139">Представляет определенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="0cd38-139">Represents a specific build version.</span></span> <span data-ttu-id="0cd38-140">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0cd38-140">The possible values are:</span></span>

- <span data-ttu-id="0cd38-141">`latest` — последняя сборка в канале (используется с параметром `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="0cd38-141">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="0cd38-142">`coherent` — последняя согласованная сборка в канале. Использует последние сочетания стабильных пакетов. (Используется с параметрами `-Channel` имени ветви.)</span><span class="sxs-lookup"><span data-stu-id="0cd38-142">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="0cd38-143">Версия из трех частей в формате X.Y.Z, который представляет определенную версию сборки. Заменяет параметр `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-143">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="0cd38-144">Пример: `2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="0cd38-144">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="0cd38-145">Если значение не указано, для параметра `-Version` по умолчанию используется значение `latest`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-145">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="0cd38-146">Указывает путь установки.</span><span class="sxs-lookup"><span data-stu-id="0cd38-146">Specifies the installation path.</span></span> <span data-ttu-id="0cd38-147">Если такого пути нет, создается каталог.</span><span class="sxs-lookup"><span data-stu-id="0cd38-147">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="0cd38-148">Значение по умолчанию — *%LocalAppData%\.dotnet*.</span><span class="sxs-lookup"><span data-stu-id="0cd38-148">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="0cd38-149">Обратите внимание, что двоичные файлы помещаются непосредственно в каталог.</span><span class="sxs-lookup"><span data-stu-id="0cd38-149">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="0cd38-150">Архитектура устанавливаемых двоичных файлов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0cd38-150">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="0cd38-151">Допустимые значения: `auto`, `x64` и `x86`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-151">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="0cd38-152">Значение по умолчанию — `auto`, представляющее текущую используемую архитектуру ОС.</span><span class="sxs-lookup"><span data-stu-id="0cd38-152">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="0cd38-153">Если параметр задан, он ограничивает установку общей средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="0cd38-153">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="0cd38-154">Установка всего пакета SDK не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0cd38-154">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="0cd38-155">Если значение задано, скрипт не будет выполнять установку. Вместо этого отобразится командная строка для согласованной установки запрошенной в настоящее время версии CLI .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0cd38-155">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="0cd38-156">Например, если указать версию `latest`, он отображает ссылку для определенной версии, чтобы эту команду можно было детерминировано использовать в скрипте сборки.</span><span class="sxs-lookup"><span data-stu-id="0cd38-156">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="0cd38-157">Кроме того, он отображает расположение двоичного файла, если вы хотите выполнить скачивание или установку самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="0cd38-157">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="0cd38-158">Если значение задано, префикс и каталог установки не экспортируются в путь текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="0cd38-158">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="0cd38-159">По умолчанию скрипт изменит значение PATH, благодаря этому средства CLI становятся доступными сразу после установки.</span><span class="sxs-lookup"><span data-stu-id="0cd38-159">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="0cd38-160">Указывает URL-адрес для веб-канала Azure этого установщика.</span><span class="sxs-lookup"><span data-stu-id="0cd38-160">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="0cd38-161">Изменять это значение не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="0cd38-161">It isn't recommended that you change this value.</span></span> <span data-ttu-id="0cd38-162">Значение по умолчанию — `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="0cd38-162">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="0cd38-163">Если значение задано, установщик использует прокси-сервер для выполнения веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="0cd38-163">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="0cd38-164">(Доступно только для Windows.)</span><span class="sxs-lookup"><span data-stu-id="0cd38-164">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="0cd38-165">Отображение сведений о диагностике.</span><span class="sxs-lookup"><span data-stu-id="0cd38-165">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="0cd38-166">Выводит справку для скрипта.</span><span class="sxs-lookup"><span data-stu-id="0cd38-166">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="0cd38-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="0cd38-167">Examples</span></span>

<span data-ttu-id="0cd38-168">Установка последней версии с долгосрочной поддержкой (LTS) в расположение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="0cd38-168">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="0cd38-169">Windows:</span><span class="sxs-lookup"><span data-stu-id="0cd38-169">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="0cd38-170">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="0cd38-170">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="0cd38-171">Установка последней версии из канала версии 2.0 в указанное расположение:</span><span class="sxs-lookup"><span data-stu-id="0cd38-171">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="0cd38-172">Windows:</span><span class="sxs-lookup"><span data-stu-id="0cd38-172">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="0cd38-173">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="0cd38-173">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="0cd38-174">Установка общей среды выполнения версии 1.1.0:</span><span class="sxs-lookup"><span data-stu-id="0cd38-174">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="0cd38-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="0cd38-175">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="0cd38-176">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="0cd38-176">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="0cd38-177">Получите скрипт и установите однострочные примеры для интерфейса командной строки .NET Core:</span><span class="sxs-lookup"><span data-stu-id="0cd38-177">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="0cd38-178">Windows:</span><span class="sxs-lookup"><span data-stu-id="0cd38-178">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="0cd38-179">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="0cd38-179">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="0cd38-180">См. также</span><span class="sxs-lookup"><span data-stu-id="0cd38-180">See also</span></span>

<span data-ttu-id="0cd38-181">[Выпуски .NET Core](https://github.com/dotnet/core/releases) </span><span class="sxs-lookup"><span data-stu-id="0cd38-181">[.NET Core releases](https://github.com/dotnet/core/releases) </span></span>  
[<span data-ttu-id="0cd38-182">Архив загрузки пакета SDK и среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="0cd38-182">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
