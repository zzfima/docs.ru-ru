---
title: Скрипты dotnet-install
description: Сведения о скриптах dotnet-install, которые служат для установки пакета SDK для .NET Core и общей среды выполнения
ms.date: 01/23/2020
ms.openlocfilehash: 76055627c6b2016396209c9594dba36e56eb841c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920573"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="a1a0b-103">Справка по скриптам dotnet-install</span><span class="sxs-lookup"><span data-stu-id="a1a0b-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="a1a0b-104">name</span><span class="sxs-lookup"><span data-stu-id="a1a0b-104">Name</span></span>

<span data-ttu-id="a1a0b-105">`dotnet-install.ps1` | `dotnet-install.sh` — скрипт, используемый для установки общей среды выполнения и пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a1a0b-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a1a0b-106">Synopsis</span></span>

<span data-ttu-id="a1a0b-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

<span data-ttu-id="a1a0b-108">Linux или macOS</span><span class="sxs-lookup"><span data-stu-id="a1a0b-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a><span data-ttu-id="a1a0b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a1a0b-109">Description</span></span>

<span data-ttu-id="a1a0b-110">Скрипты `dotnet-install` используются для установки пакета SDK для .NET Core без прав администратора. Этот пакет включает общую среду выполнения и .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="a1a0b-111">Мы рекомендуем использовать стабильную версию скриптов.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="a1a0b-112">Bash (Linux или macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="a1a0b-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="a1a0b-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="a1a0b-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="a1a0b-114">Их основное назначение — помощь в сценариях автоматизации и при установках без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="a1a0b-115">Имеются два скрипта: один для PowerShell (работает в Windows), а второй — bash-скрипт, который работает в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="a1a0b-116">Оба скрипта выполняют одни и те же функции.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="a1a0b-117">Так как bash-скрипт также считывает параметры PowerShell, их можно использовать с этим скриптом в системах Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="a1a0b-118">Скрипты установки скачивают файл ZIP или TAR из места сборки CLI, а затем осуществляют установку в расположении по умолчанию или расположении, заданном параметром `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="a1a0b-119">По умолчанию скрипты установки скачивают и устанавливают пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="a1a0b-120">Если вы хотите получить только общую среду выполнения, укажите аргумент `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="a1a0b-121">По умолчанию скрипт добавляет место установки в переменную $PATH для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="a1a0b-122">Переопределите это поведение по умолчанию, указав аргумент `-NoPath|--no-path`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="a1a0b-123">Перед запуском скрипта установите все необходимые [зависимости](../install/dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="a1a0b-124">Вы можете установить конкретную версию с помощью аргумента `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="a1a0b-125">Версию следует указывать в виде трехкомпонентного номера (например, `2.1.0`).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="a1a0b-126">Если она не указана, используется версия `latest`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="a1a0b-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1a0b-127">Options</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="a1a0b-128">Указывает исходный канал для установки.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-128">Specifies the source channel for the installation.</span></span> <span data-ttu-id="a1a0b-129">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-129">The possible values are:</span></span>

  - <span data-ttu-id="a1a0b-130">`Current` — самый последний выпуск.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-130">`Current` - Most current release.</span></span>
  - <span data-ttu-id="a1a0b-131">`LTS` — канал долгосрочной поддержки (самый последний поддерживаемый выпуск).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-131">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="a1a0b-132">Версия из двух частей в формате X.Y, который представляет конкретный выпуск (например, `2.1` или `3.0`).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-132">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="a1a0b-133">Имя ветви, например `release/3.1.1xx` или `master` (для ночных выпусков).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-133">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="a1a0b-134">Используйте этот параметр для установки версии из канала предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-134">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="a1a0b-135">Используйте имя канала, указанное в разделе [Установщики и двоичные файлы](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-135">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="a1a0b-136">Значение по умолчанию — `LTS`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-136">The default value is `LTS`.</span></span> <span data-ttu-id="a1a0b-137">Дополнительные сведения о каналах поддержки .NET см. на странице о [политике поддержки .NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="a1a0b-138">Представляет определенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-138">Represents a specific build version.</span></span> <span data-ttu-id="a1a0b-139">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-139">The possible values are:</span></span>

  - <span data-ttu-id="a1a0b-140">`latest` — последняя сборка в канале (используется с параметром `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="a1a0b-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="a1a0b-141">`coherent` — последняя согласованная сборка в канале. Использует последние сочетания стабильных пакетов. (Используется с параметрами `-Channel` имени ветви.)</span><span class="sxs-lookup"><span data-stu-id="a1a0b-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="a1a0b-142">Версия из трех частей в формате X.Y.Z, который представляет определенную версию сборки. Заменяет параметр `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="a1a0b-143">Например, `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="a1a0b-144">Если не указано, `-Version` по умолчанию принимает значение `latest`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="a1a0b-145">Указывает путь к файлу [global.json](global-json.md), который будет использоваться для определения версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-145">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="a1a0b-146">В файле *global.json* должно быть значение для `sdk:version`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-146">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="a1a0b-147">Указывает путь установки.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-147">Specifies the installation path.</span></span> <span data-ttu-id="a1a0b-148">Если такого пути нет, создается каталог.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-148">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="a1a0b-149">Значение по умолчанию — *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-149">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="a1a0b-150">Двоичные файлы помещаются непосредственно в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-150">Binaries are placed directly in this directory.</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="a1a0b-151">Архитектура устанавливаемых двоичных файлов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-151">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="a1a0b-152">Допустимые значения: `<auto>`, `amd64`, `x64`, `x86`, `arm64` и `arm`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-152">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="a1a0b-153">Значение по умолчанию — `<auto>`, представляющее текущую используемую архитектуру ОС.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-153">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="a1a0b-154">Этот параметр является устаревшим и может быть удален в будущей версии скрипта.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-154">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="a1a0b-155">Вместо этого рекомендуется использовать параметр `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-155">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="a1a0b-156">Устанавливаются только двоичные файлы общей среды выполнения; в противном случае устанавливается весь пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-156">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="a1a0b-157">Этот параметр эквивалентен указанию `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-157">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="a1a0b-158">Устанавливается только общая среда выполнения, а не весь пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-158">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="a1a0b-159">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-159">The possible values are:</span></span>

  - <span data-ttu-id="a1a0b-160">`dotnet` — общая среда выполнения `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-160">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="a1a0b-161">`aspnetcore` — общая среда выполнения `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-161">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="a1a0b-162">`windowsdesktop` — общая среда выполнения `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-162">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="a1a0b-163">Если задано, скрипт не будет выполнять установку.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-163">If set, the script won't perform the installation.</span></span> <span data-ttu-id="a1a0b-164">Вместо этого отобразится командная строка для согласованной установки запрошенной в настоящее время версии .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-164">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="a1a0b-165">Например, если указать версию `latest`, он отображает ссылку для определенной версии, чтобы эту команду можно было детерминировано использовать в скрипте сборки.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-165">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="a1a0b-166">Кроме того, он отображает расположение двоичного файла, если вы хотите выполнить скачивание или установку самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-166">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="a1a0b-167">Если значение задано, папка установки не экспортируется в путь текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-167">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="a1a0b-168">По умолчанию скрипт изменит значение PATH, благодаря чему .NET Core CLI становится доступным сразу после установки.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-168">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="a1a0b-169">Отображает сведения о диагностике.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-169">Displays diagnostics information.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="a1a0b-170">Указывает URL-адрес для веб-канала Azure этого установщика.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-170">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="a1a0b-171">Изменять это значение не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-171">We recommended that you don't change this value.</span></span> <span data-ttu-id="a1a0b-172">Значение по умолчанию — `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-172">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="a1a0b-173">Позволяет изменять URL-адрес некэшированного веб-канала, используемого этим установщиком.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-173">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="a1a0b-174">Изменять это значение не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-174">We recommended that you don't change this value.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="a1a0b-175">Отключает загрузку из [сети доставки содержимого Microsoft Azure (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) и напрямую использует некэшированный веб-канал.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="a1a0b-176">Используется в качестве строки запроса для добавления в веб-канал Azure.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-176">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="a1a0b-177">Позволяет изменять URL-адрес для использования учетных записей хранилища BLOB-объектов, не являющихся общедоступными.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-177">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--runtime-id`**

  <span data-ttu-id="a1a0b-178">Указывает [идентификатор среды выполнения](../rid-catalog.md), для которого устанавливаются средства.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-178">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="a1a0b-179">Используйте значение `linux-x64` для переносимых файлов Linux.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-179">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="a1a0b-180">(Допустимо только для Linux и macOS.)</span><span class="sxs-lookup"><span data-stu-id="a1a0b-180">(Only valid for Linux/macOS)</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="a1a0b-181">Если значение задано, установщик использует прокси-сервер для выполнения веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-181">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="a1a0b-182">(Доступно только для Windows.)</span><span class="sxs-lookup"><span data-stu-id="a1a0b-182">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="a1a0b-183">Если задано, установщик использует учетные данные текущего пользователя при использовании адреса прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-183">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="a1a0b-184">(Доступно только для Windows.)</span><span class="sxs-lookup"><span data-stu-id="a1a0b-184">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="a1a0b-185">Пропускает установку файлов без версии, таких как *dotnet.exe*, если они уже существуют.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-185">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="a1a0b-186">Выводит справку для скрипта.</span><span class="sxs-lookup"><span data-stu-id="a1a0b-186">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="a1a0b-187">Примеры</span><span class="sxs-lookup"><span data-stu-id="a1a0b-187">Examples</span></span>

- <span data-ttu-id="a1a0b-188">Установка последней версии с долгосрочной поддержкой (LTS) в расположение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="a1a0b-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="a1a0b-190">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="a1a0b-191">Установка последней версии из канала версии 3.1 в указанное расположение</span><span class="sxs-lookup"><span data-stu-id="a1a0b-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="a1a0b-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="a1a0b-193">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="a1a0b-194">Установка общей среды выполнения версии 3.0.0</span><span class="sxs-lookup"><span data-stu-id="a1a0b-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="a1a0b-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="a1a0b-196">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="a1a0b-197">Получите и установите скрипт версии 2.1.2 за корпоративным прокси-сервером (только для Windows):</span><span class="sxs-lookup"><span data-stu-id="a1a0b-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="a1a0b-198">Получите скрипт и установите однострочные примеры для интерфейса командной строки .NET Core:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="a1a0b-199">Windows:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="a1a0b-200">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="a1a0b-200">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="a1a0b-201">См. также</span><span class="sxs-lookup"><span data-stu-id="a1a0b-201">See also</span></span>

- [<span data-ttu-id="a1a0b-202">Выпуски .NET Core</span><span class="sxs-lookup"><span data-stu-id="a1a0b-202">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="a1a0b-203">Архив загрузки пакета SDK и среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="a1a0b-203">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
