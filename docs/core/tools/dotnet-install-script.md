---
title: Скрипты dotnet-install
description: Сведения о скриптах dotnet-install, которые служат для установки средств CLI .NET Core и общей среды выполнения.
ms.date: 01/16/2019
ms.openlocfilehash: f72e12fc415824a9c69eba6f52e3c01717cf654c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740530"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="ad185-103">Справка по скриптам dotnet-install</span><span class="sxs-lookup"><span data-stu-id="ad185-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="ad185-104">name</span><span class="sxs-lookup"><span data-stu-id="ad185-104">Name</span></span>

<span data-ttu-id="ad185-105">`dotnet-install.ps1` | `dotnet-install.sh` — скрипт, используемый для установки общей среды выполнения и средств .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="ad185-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ad185-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ad185-106">Synopsis</span></span>

<span data-ttu-id="ad185-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="ad185-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

<span data-ttu-id="ad185-108">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="ad185-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a><span data-ttu-id="ad185-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ad185-109">Description</span></span>

<span data-ttu-id="ad185-110">Скрипты `dotnet-install` используются для установки пакета SDK для .NET Core без прав администратора. Этот пакет включает общую среду выполнения и средства .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="ad185-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="ad185-111">Мы рекомендуем использовать стабильную версию, размещенную на [основном веб-сайте .NET Core](https://dot.net).</span><span class="sxs-lookup"><span data-stu-id="ad185-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="ad185-112">Прямые пути к скриптам:</span><span class="sxs-lookup"><span data-stu-id="ad185-112">The direct paths to the scripts are:</span></span>

- <span data-ttu-id="ad185-113"><https://dot.net/v1/dotnet-install.sh> (Bash, UNIX);</span><span class="sxs-lookup"><span data-stu-id="ad185-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span></span>
- <span data-ttu-id="ad185-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows).</span><span class="sxs-lookup"><span data-stu-id="ad185-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span></span>

<span data-ttu-id="ad185-115">Их основное назначение — помощь в сценариях автоматизации и при установках без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="ad185-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="ad185-116">Имеются два скрипта: один для PowerShell (работает в Windows), а второй — bash-скрипт, который работает в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="ad185-116">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="ad185-117">Оба скрипта выполняют одни и те же функции.</span><span class="sxs-lookup"><span data-stu-id="ad185-117">Both scripts have the same behavior.</span></span> <span data-ttu-id="ad185-118">Так как bash-скрипт также считывает параметры PowerShell, их можно использовать с этим скриптом в системах Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="ad185-118">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="ad185-119">Скрипты установки скачивают файл ZIP или TAR из места сборки CLI, а затем осуществляют установку в расположении по умолчанию или расположении, заданном параметром `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="ad185-119">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="ad185-120">По умолчанию скрипты установки скачивают и устанавливают пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="ad185-120">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="ad185-121">Если вы хотите получить только общую среду выполнения, укажите аргумент `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="ad185-121">If you wish to only obtain the shared runtime, specify the `--runtime` argument.</span></span>

<span data-ttu-id="ad185-122">По умолчанию скрипт добавляет место установки в переменную $PATH для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="ad185-122">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="ad185-123">Переопределите это поведение по умолчанию, указав аргумент `--no-path`.</span><span class="sxs-lookup"><span data-stu-id="ad185-123">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="ad185-124">Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="ad185-124">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="ad185-125">Вы можете установить конкретную версию с помощью аргумента `--version`.</span><span class="sxs-lookup"><span data-stu-id="ad185-125">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="ad185-126">Версию следует указывать в виде трехкомпонентного номера (например, 1.0.0-13232).</span><span class="sxs-lookup"><span data-stu-id="ad185-126">The version must be specified as a three-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="ad185-127">Если она не указана, используется версия `latest`.</span><span class="sxs-lookup"><span data-stu-id="ad185-127">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="ad185-128">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad185-128">Options</span></span>

- **`-Channel <CHANNEL>`**

  <span data-ttu-id="ad185-129">Указывает исходный канал для установки.</span><span class="sxs-lookup"><span data-stu-id="ad185-129">Specifies the source channel for the installation.</span></span> <span data-ttu-id="ad185-130">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ad185-130">The possible values are:</span></span>

  - <span data-ttu-id="ad185-131">`Current` — самый последний выпуск.</span><span class="sxs-lookup"><span data-stu-id="ad185-131">`Current` - Most current release.</span></span>
  - <span data-ttu-id="ad185-132">`LTS` — канал долгосрочной поддержки (самый последний поддерживаемый выпуск).</span><span class="sxs-lookup"><span data-stu-id="ad185-132">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="ad185-133">Версия из двух частей в формате X.Y, который представляет конкретный выпуск (например, `2.0` или `1.0`).</span><span class="sxs-lookup"><span data-stu-id="ad185-133">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`).</span></span>
  - <span data-ttu-id="ad185-134">Имя ветви.</span><span class="sxs-lookup"><span data-stu-id="ad185-134">Branch name.</span></span> <span data-ttu-id="ad185-135">Например, `release/2.0.0`, `release/2.0.0-preview2` или `master` (для ночных выпусков).</span><span class="sxs-lookup"><span data-stu-id="ad185-135">For example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` (for nightly releases).</span></span>

  <span data-ttu-id="ad185-136">Значение по умолчанию — `LTS`.</span><span class="sxs-lookup"><span data-stu-id="ad185-136">The default value is `LTS`.</span></span> <span data-ttu-id="ad185-137">Дополнительные сведения о каналах поддержки .NET см. на странице о [политике поддержки .NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="ad185-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version <VERSION>`**

  <span data-ttu-id="ad185-138">Представляет определенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="ad185-138">Represents a specific build version.</span></span> <span data-ttu-id="ad185-139">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ad185-139">The possible values are:</span></span>

  - <span data-ttu-id="ad185-140">`latest` — последняя сборка в канале (используется с параметром `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="ad185-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="ad185-141">`coherent` — последняя согласованная сборка в канале. Использует последние сочетания стабильных пакетов. (Используется с параметрами `-Channel` имени ветви.)</span><span class="sxs-lookup"><span data-stu-id="ad185-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="ad185-142">Версия из трех частей в формате X.Y.Z, который представляет определенную версию сборки. Заменяет параметр `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="ad185-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="ad185-143">Например, `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="ad185-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="ad185-144">Если не указано, `-Version` по умолчанию принимает значение `latest`.</span><span class="sxs-lookup"><span data-stu-id="ad185-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-InstallDir <DIRECTORY>`**

  <span data-ttu-id="ad185-145">Указывает путь установки.</span><span class="sxs-lookup"><span data-stu-id="ad185-145">Specifies the installation path.</span></span> <span data-ttu-id="ad185-146">Если такого пути нет, создается каталог.</span><span class="sxs-lookup"><span data-stu-id="ad185-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="ad185-147">Значение по умолчанию — *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="ad185-147">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="ad185-148">Двоичные файлы помещаются непосредственно в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="ad185-148">Binaries are placed directly in this directory.</span></span>

- **`-Architecture <ARCHITECTURE>`**

  <span data-ttu-id="ad185-149">Архитектура устанавливаемых двоичных файлов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad185-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="ad185-150">Допустимые значения: `<auto>`, `amd64`, `x64`, `x86`, `arm64` и `arm`.</span><span class="sxs-lookup"><span data-stu-id="ad185-150">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="ad185-151">Значение по умолчанию — `<auto>`, представляющее текущую используемую архитектуру ОС.</span><span class="sxs-lookup"><span data-stu-id="ad185-151">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime`**

  > [!NOTE]
  > <span data-ttu-id="ad185-152">Этот параметр является устаревшим и может быть удален в будущей версии скрипта.</span><span class="sxs-lookup"><span data-stu-id="ad185-152">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="ad185-153">Вместо этого рекомендуется использовать параметр `Runtime`.</span><span class="sxs-lookup"><span data-stu-id="ad185-153">The recommended alternative is the `Runtime` option.</span></span>

  <span data-ttu-id="ad185-154">Устанавливаются только двоичные файлы общей среды выполнения; в противном случае устанавливается весь пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="ad185-154">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="ad185-155">Это эквивалентно указанию `-Runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="ad185-155">This is equivalent to specifying `-Runtime dotnet`.</span></span>

- **`-Runtime <RUNTIME>`**

  <span data-ttu-id="ad185-156">Устанавливается только общая среда выполнения, а не весь пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="ad185-156">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="ad185-157">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ad185-157">The possible values are:</span></span>

  - <span data-ttu-id="ad185-158">`dotnet` — общая среда выполнения `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="ad185-158">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="ad185-159">`aspnetcore` — общая среда выполнения `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="ad185-159">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>

- **`-DryRun`**

  <span data-ttu-id="ad185-160">Если задано, скрипт не будет выполнять установку.</span><span class="sxs-lookup"><span data-stu-id="ad185-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="ad185-161">Вместо этого отобразится командная строка для согласованной установки запрошенной в настоящее время версии .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="ad185-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="ad185-162">Например, если указать версию `latest`, он отображает ссылку для определенной версии, чтобы эту команду можно было детерминировано использовать в скрипте сборки.</span><span class="sxs-lookup"><span data-stu-id="ad185-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="ad185-163">Кроме того, он отображает расположение двоичного файла, если вы хотите выполнить скачивание или установку самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="ad185-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath`**

  <span data-ttu-id="ad185-164">Если значение задано, папка установки не экспортируется в путь текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="ad185-164">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="ad185-165">По умолчанию скрипт изменит значение PATH, благодаря этому средства CLI становятся доступными сразу после установки.</span><span class="sxs-lookup"><span data-stu-id="ad185-165">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose`**

  <span data-ttu-id="ad185-166">Отображает сведения о диагностике.</span><span class="sxs-lookup"><span data-stu-id="ad185-166">Displays diagnostics information.</span></span>

- **`-AzureFeed`**

  <span data-ttu-id="ad185-167">Указывает URL-адрес для веб-канала Azure этого установщика.</span><span class="sxs-lookup"><span data-stu-id="ad185-167">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="ad185-168">Изменять это значение не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="ad185-168">We recommended that you don't change this value.</span></span> <span data-ttu-id="ad185-169">Значение по умолчанию — `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="ad185-169">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed`**

  <span data-ttu-id="ad185-170">Позволяет изменять URL-адрес некэшированного веб-канала, используемого этим установщиком.</span><span class="sxs-lookup"><span data-stu-id="ad185-170">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="ad185-171">Изменять это значение не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="ad185-171">We recommended that you don't change this value.</span></span>

- **`-NoCdn`**

  <span data-ttu-id="ad185-172">Отключает загрузку из [сети доставки содержимого Microsoft Azure (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) и напрямую использует некэшированный веб-канал.</span><span class="sxs-lookup"><span data-stu-id="ad185-172">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential`**

  <span data-ttu-id="ad185-173">Используется в качестве строки запроса для добавления в веб-канал Azure.</span><span class="sxs-lookup"><span data-stu-id="ad185-173">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="ad185-174">Позволяет изменять URL-адрес для использования учетных записей хранилища BLOB-объектов, не являющихся общедоступными.</span><span class="sxs-lookup"><span data-stu-id="ad185-174">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="ad185-175">Если значение задано, установщик использует прокси-сервер для выполнения веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="ad185-175">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="ad185-176">(Доступно только для Windows.)</span><span class="sxs-lookup"><span data-stu-id="ad185-176">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="ad185-177">Если задано, установщик использует учетные данные текущего пользователя при использовании адреса прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ad185-177">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="ad185-178">(Доступно только для Windows.)</span><span class="sxs-lookup"><span data-stu-id="ad185-178">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles`**

  <span data-ttu-id="ad185-179">Пропускает установку файлов без версии, таких как *dotnet.exe*, если они уже существуют.</span><span class="sxs-lookup"><span data-stu-id="ad185-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help`**

  <span data-ttu-id="ad185-180">Выводит справку для скрипта.</span><span class="sxs-lookup"><span data-stu-id="ad185-180">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="ad185-181">Примеры</span><span class="sxs-lookup"><span data-stu-id="ad185-181">Examples</span></span>

- <span data-ttu-id="ad185-182">Установка последней версии с долгосрочной поддержкой (LTS) в расположение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ad185-182">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="ad185-183">Windows:</span><span class="sxs-lookup"><span data-stu-id="ad185-183">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="ad185-184">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="ad185-184">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="ad185-185">Установка последней версии из канала версии 2.0 в указанное расположение:</span><span class="sxs-lookup"><span data-stu-id="ad185-185">Install the latest version from 2.0 channel to the specified location:</span></span>

  <span data-ttu-id="ad185-186">Windows:</span><span class="sxs-lookup"><span data-stu-id="ad185-186">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  <span data-ttu-id="ad185-187">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="ad185-187">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- <span data-ttu-id="ad185-188">Установка общей среды выполнения версии 1.1.0:</span><span class="sxs-lookup"><span data-stu-id="ad185-188">Install the 1.1.0 version of the shared runtime:</span></span>

  <span data-ttu-id="ad185-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="ad185-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  <span data-ttu-id="ad185-190">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="ad185-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- <span data-ttu-id="ad185-191">Получите и установите скрипт версии 2.1.2 за корпоративным прокси-сервером (только для Windows):</span><span class="sxs-lookup"><span data-stu-id="ad185-191">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="ad185-192">Получите скрипт и установите однострочные примеры для интерфейса командной строки .NET Core:</span><span class="sxs-lookup"><span data-stu-id="ad185-192">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="ad185-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="ad185-193">Windows:</span></span>

  ```powershell
  @powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="ad185-194">Mac OS и Linux:</span><span class="sxs-lookup"><span data-stu-id="ad185-194">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="ad185-195">См. также</span><span class="sxs-lookup"><span data-stu-id="ad185-195">See also</span></span>

- [<span data-ttu-id="ad185-196">Выпуски .NET Core</span><span class="sxs-lookup"><span data-stu-id="ad185-196">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="ad185-197">Архив загрузки пакета SDK и среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="ad185-197">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
