---
title: Устранение неполадок при использовании средства .NET Core
description: Ознакомьтесь с распространенными проблемами, возникающими при использовании средств .NET Core, и возможными решениями.
author: kdollard
ms.date: 02/14/2020
ms.openlocfilehash: ed6243f802c4d3ce56a742916a1a28676e3cd876
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146454"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="213d0-103">Устранение неполадок при использовании средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="213d0-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="213d0-104">При попытке установить или запустить глобальное или локальное средство .NET Core могут возникнуть проблемы.</span><span class="sxs-lookup"><span data-stu-id="213d0-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="213d0-105">В этой статье описываются их типичные первопричины и возможные решения.</span><span class="sxs-lookup"><span data-stu-id="213d0-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="213d0-106">Установленное средство .NET Core не запускается</span><span class="sxs-lookup"><span data-stu-id="213d0-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="213d0-107">Если средство .NET Core не запускается, наиболее вероятной причиной является одна из следующих.</span><span class="sxs-lookup"><span data-stu-id="213d0-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="213d0-108">Исполняемый файл средства не найден.</span><span class="sxs-lookup"><span data-stu-id="213d0-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="213d0-109">Не найдена правильная версия среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="213d0-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="213d0-110">Исполняемый файл не найден</span><span class="sxs-lookup"><span data-stu-id="213d0-110">Executable file not found</span></span>

<span data-ttu-id="213d0-111">Если исполняемый файл не найден, появляется примерно следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="213d0-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="213d0-112">Имя исполняемого файла определяет то, как вызывается средство.</span><span class="sxs-lookup"><span data-stu-id="213d0-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="213d0-113">Формат описывается в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="213d0-113">The following table describes the format:</span></span>

| <span data-ttu-id="213d0-114">Формат имени исполняемого файла</span><span class="sxs-lookup"><span data-stu-id="213d0-114">Executable name format</span></span>  | <span data-ttu-id="213d0-115">Формат вызова</span><span class="sxs-lookup"><span data-stu-id="213d0-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="213d0-116">Глобальные средства</span><span class="sxs-lookup"><span data-stu-id="213d0-116">Global tools</span></span>

  <span data-ttu-id="213d0-117">Глобальные средства можно установить в каталоге по умолчанию или в выбранном вами расположении.</span><span class="sxs-lookup"><span data-stu-id="213d0-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="213d0-118">Каталоги по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="213d0-118">The default directories are:</span></span>

  | <span data-ttu-id="213d0-119">Операционная система</span><span class="sxs-lookup"><span data-stu-id="213d0-119">OS</span></span>          | <span data-ttu-id="213d0-120">Path</span><span class="sxs-lookup"><span data-stu-id="213d0-120">Path</span></span>                          |
  |-------------|-------------------------------|
  | <span data-ttu-id="213d0-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="213d0-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
  | <span data-ttu-id="213d0-122">Windows</span><span class="sxs-lookup"><span data-stu-id="213d0-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

  <span data-ttu-id="213d0-123">Если вы пытаетесь запустить глобальное средство, убедитесь в том, что переменная среды `PATH` на компьютере содержит путь, по которому установлено глобальное средство, и что исполняемый файл находится по этому пути.</span><span class="sxs-lookup"><span data-stu-id="213d0-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

  <span data-ttu-id="213d0-124">Интерфейс .NET Core CLI пытается добавить расположение по умолчанию в переменную среды PATH при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="213d0-124">The .NET Core CLI tries to add the default location to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="213d0-125">Однако есть определенные ситуации, когда расположение не удается добавить в переменную PATH автоматически:</span><span class="sxs-lookup"><span data-stu-id="213d0-125">However, there are some scenarios where the location might not be added to PATH automatically:</span></span>

  * <span data-ttu-id="213d0-126">используется ОС Linux, и пакет SDK для .NET Core установлен с помощью файлов *.tar.gz*, а не apt-get или rpm;</span><span class="sxs-lookup"><span data-stu-id="213d0-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="213d0-127">используется ОС macOS 10.15 "Catalina" или более поздней версии;</span><span class="sxs-lookup"><span data-stu-id="213d0-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="213d0-128">используется ОС macOS 10.14 "Mojave" или более ранней версии, и пакет SDK для .NET Core установлен с помощью файлов *.tar.gz*, а не *.pkg*;</span><span class="sxs-lookup"><span data-stu-id="213d0-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="213d0-129">установлен пакет SDK для .NET Core 3.0, и переменной среды `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` присвоено значение `false`;</span><span class="sxs-lookup"><span data-stu-id="213d0-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="213d0-130">установлен пакет SDK для пакет SDK.NET Core 2.2 или более ранней версии, и переменной среды `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` присвоено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="213d0-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="213d0-131">В таких сценариях, а также если указан параметр `--tool-path`, в переменную среды `PATH` на вашем компьютере не будет автоматически добавляться путь, по которому было установлено глобальное средство.</span><span class="sxs-lookup"><span data-stu-id="213d0-131">In these scenarios or if you specified the `--tool-path` option, the `PATH` environment variable on your machine doesn't automatically contain the path where you installed the global tool.</span></span> <span data-ttu-id="213d0-132">В этом случае необходимо добавить в переменную среды `PATH` расположение этого средства (например, `$HOME/.dotnet/tools`) с использованием любого метода обновления переменных среды, предусмотренного в вашей оболочке.</span><span class="sxs-lookup"><span data-stu-id="213d0-132">In that case, append the tool location (for example, `$HOME/.dotnet/tools`) to the `PATH` environment variable by using whatever method your shell provides for updating environment variables.</span></span> <span data-ttu-id="213d0-133">Дополнительные сведения см. в статье [Обзор глобальных средств .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="213d0-133">For more information, see [.NET Core tools](global-tools.md).</span></span>

* <span data-ttu-id="213d0-134">Локальные средства</span><span class="sxs-lookup"><span data-stu-id="213d0-134">Local tools</span></span>

  <span data-ttu-id="213d0-135">Если вы пытаетесь запустить локальное средство, убедитесь в наличии файла манифеста с именем *dotnet-tools.json* в текущем каталоге или в любом из его родительских каталогов.</span><span class="sxs-lookup"><span data-stu-id="213d0-135">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="213d0-136">Этот файл также может находиться в папке *.config* где угодно в иерархии папок проекта, а не в корневой папке.</span><span class="sxs-lookup"><span data-stu-id="213d0-136">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="213d0-137">Если файл *dotnet-tools.json* существует, откройте его и проверьте наличие средства, которое вы пытаетесь запустить.</span><span class="sxs-lookup"><span data-stu-id="213d0-137">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="213d0-138">Если в файле нет записи для `"isRoot": true`, также проверьте наличие дополнительных файлов манифестов средств выше в иерархии файлов.</span><span class="sxs-lookup"><span data-stu-id="213d0-138">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="213d0-139">Если вы пытаетесь запустить средство .NET Core, которое было установлено по указанному пути, необходимо включить этот путь при использовании средства.</span><span class="sxs-lookup"><span data-stu-id="213d0-139">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="213d0-140">Пример средства, установленного по определенному пути:</span><span class="sxs-lookup"><span data-stu-id="213d0-140">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="213d0-141">Среда выполнения не найдена</span><span class="sxs-lookup"><span data-stu-id="213d0-141">Runtime not found</span></span>

<span data-ttu-id="213d0-142">Средства .NET Core — это [приложения, зависящие от платформы](../deploying/index.md#publish-runtime-dependent), то есть от среды выполнения .NET Core, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="213d0-142">.NET Core tools are [framework-dependent applications](../deploying/index.md#publish-runtime-dependent), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="213d0-143">Если ожидаемая среда выполнения не найдена, они следуют обычным правилам наката среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="213d0-143">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="213d0-144">Накат выполняется к последнему номеру выпуска исправления указанной основной и дополнительной версии.</span><span class="sxs-lookup"><span data-stu-id="213d0-144">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="213d0-145">Если соответствующая среда выполнения с соответствующими номерами основной и дополнительной версий отсутствует, используется следующий последний дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="213d0-145">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="213d0-146">Накат не выполняется между предварительными версиями среды выполнения или между предварительной версией и версией выпуска.</span><span class="sxs-lookup"><span data-stu-id="213d0-146">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="213d0-147">Таким образом, средства .NET Core, созданные с помощью предварительных версий, должны быть перестроены и повторно опубликованы автором, а затем переустановлены.</span><span class="sxs-lookup"><span data-stu-id="213d0-147">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="213d0-148">Накат не выполняется по умолчанию в двух распространенных сценариях:</span><span class="sxs-lookup"><span data-stu-id="213d0-148">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="213d0-149">доступны только более ранние версии среды выполнения;</span><span class="sxs-lookup"><span data-stu-id="213d0-149">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="213d0-150">при накате выбираются только более поздние версии среды выполнения;</span><span class="sxs-lookup"><span data-stu-id="213d0-150">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="213d0-151">доступны только более поздние основные версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="213d0-151">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="213d0-152">При накате границы основной версии не пересекаются.</span><span class="sxs-lookup"><span data-stu-id="213d0-152">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="213d0-153">Если приложению не удается найти подходящую среду выполнения, оно не запускается и сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="213d0-153">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="213d0-154">Узнать, какие среды выполнения .NET Core установлены на компьютере, можно с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="213d0-154">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="213d0-155">Если вы считаете, что средство должно поддерживать версию среды выполнения, установленную в настоящее время, обратитесь к автору средства и узнайте, может ли он обновить номер версии или перенацелить средство на несколько версий.</span><span class="sxs-lookup"><span data-stu-id="213d0-155">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="213d0-156">После того как автор перекомпилирует и повторно опубликует пакет средства в NuGet с обновленным номером версии, вы можете обновить свою копию.</span><span class="sxs-lookup"><span data-stu-id="213d0-156">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="213d0-157">Пока же этого не произошло, проще всего установить версию среды выполнения, совместимую со средством, которое вы пытаетесь запустить.</span><span class="sxs-lookup"><span data-stu-id="213d0-157">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="213d0-158">Чтобы скачать определенную версию среды выполнения .NET Core, перейдите на [страницу скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="213d0-158">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="213d0-159">Если пакет SDK для .NET Core устанавливается в месте, отличном от расположения по умолчанию, необходимо присвоить переменной среды `DOTNET_ROOT` каталог, содержащий исполняемый файл `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="213d0-159">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="213d0-160">Не удается установить средство .NET Core</span><span class="sxs-lookup"><span data-stu-id="213d0-160">.NET Core tool installation fails</span></span>

<span data-ttu-id="213d0-161">Установка глобального или локального средства .NET Core может завершиться сбоем по ряду причин.</span><span class="sxs-lookup"><span data-stu-id="213d0-161">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="213d0-162">Если при установке средства происходит сбой, появляется примерно следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="213d0-162">When the tool installation fails, you'll see a message similar to the following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="213d0-163">Помимо предыдущего сообщения, пользователю также выводятся сообщения NuGet, помогающие диагностировать эти сбои.</span><span class="sxs-lookup"><span data-stu-id="213d0-163">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="213d0-164">Сообщение NuGet может помочь определить причину проблемы.</span><span class="sxs-lookup"><span data-stu-id="213d0-164">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="213d0-165">Изменение имен пакетов</span><span class="sxs-lookup"><span data-stu-id="213d0-165">Package naming enforcement</span></span>

<span data-ttu-id="213d0-166">Корпорация Майкрософт изменила правила в отношении идентификаторов пакетов для средств, из-за чего некоторые средства теперь невозможно найти по прежним именам.</span><span class="sxs-lookup"><span data-stu-id="213d0-166">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="213d0-167">Согласно новым правилам имена средств Майкрософт должны иметь префикс "Microsoft.".</span><span class="sxs-lookup"><span data-stu-id="213d0-167">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="213d0-168">Этот префикс зарезервирован и может использоваться только для пакетов, подписанных с помощью авторизованного сертификата Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="213d0-168">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="213d0-169">Во время перехода некоторые средства Майкрософт будут иметь старую форму идентификатора пакета, а другие — новую форму:</span><span class="sxs-lookup"><span data-stu-id="213d0-169">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="213d0-170">По мере обновления идентификаторов пакетов необходимо будет перейти на новый идентификатор, чтобы получить последние обновления.</span><span class="sxs-lookup"><span data-stu-id="213d0-170">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="213d0-171">Пакеты с упрощенными именами средств станут нерекомендуемыми.</span><span class="sxs-lookup"><span data-stu-id="213d0-171">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="213d0-172">Предварительные выпуски</span><span class="sxs-lookup"><span data-stu-id="213d0-172">Preview releases</span></span>

* <span data-ttu-id="213d0-173">Вы пытаетесь установить предварительный выпуск и не использовали параметр `--version` для указания версии.</span><span class="sxs-lookup"><span data-stu-id="213d0-173">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="213d0-174">Если средство .NET Core находится на стадии предварительной версии, это должно быть указано в части имени.</span><span class="sxs-lookup"><span data-stu-id="213d0-174">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="213d0-175">Указывать предварительную версию полностью не нужно.</span><span class="sxs-lookup"><span data-stu-id="213d0-175">You don't need to include the entire preview.</span></span> <span data-ttu-id="213d0-176">Если номера версий имеют ожидаемый формат, можно использовать нечто подобное:</span><span class="sxs-lookup"><span data-stu-id="213d0-176">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="213d0-177">Пакет не является средством .NET Core</span><span class="sxs-lookup"><span data-stu-id="213d0-177">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="213d0-178">Пакет NuGet с таким именем найден, но не является средством .NET Core.</span><span class="sxs-lookup"><span data-stu-id="213d0-178">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="213d0-179">При попытке установить пакет NuGet, который является обычным пакетом NuGet, а не средством .NET Core, вы увидите такое сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="213d0-179">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="213d0-180">NU1212: недопустимое сочетание проекта и пакета для `<ToolName>`.</span><span class="sxs-lookup"><span data-stu-id="213d0-180">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="213d0-181">Стиль проекта DotnetToolReference допускает только ссылки типа DotnetTool.</span><span class="sxs-lookup"><span data-stu-id="213d0-181">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="213d0-182">Веб-канал NuGet недоступен</span><span class="sxs-lookup"><span data-stu-id="213d0-182">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="213d0-183">Не удается получить доступ к требуемому веб-каналу NuGet, возможно, из-за проблемы с подключением к Интернету.</span><span class="sxs-lookup"><span data-stu-id="213d0-183">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="213d0-184">Для установки средства требуется доступ к веб-каналу NuGet, содержащему пакет средства.</span><span class="sxs-lookup"><span data-stu-id="213d0-184">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="213d0-185">Установка завершается сбоем, если этот веб-канал недоступен.</span><span class="sxs-lookup"><span data-stu-id="213d0-185">It fails if the feed isn't available.</span></span> <span data-ttu-id="213d0-186">Вы можете изменить веб-каналы с помощью `nuget.config`, запросить определенный файл `nuget.config` или указать дополнительные веб-каналы с помощью параметра `--add-source`.</span><span class="sxs-lookup"><span data-stu-id="213d0-186">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="213d0-187">По умолчанию NuGet выдает ошибку для каждого веб-канала, к которому не удается подключиться.</span><span class="sxs-lookup"><span data-stu-id="213d0-187">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="213d0-188">Флаг `--ignore-failed-sources` позволяет пропускать недоступные источники.</span><span class="sxs-lookup"><span data-stu-id="213d0-188">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="213d0-189">Неправильный идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="213d0-189">Package ID incorrect</span></span>

* <span data-ttu-id="213d0-190">Вы неправильно ввели имя средства.</span><span class="sxs-lookup"><span data-stu-id="213d0-190">You mistyped the name of the tool.</span></span>

<span data-ttu-id="213d0-191">Распространенной причиной ошибок является неправильное имя средства.</span><span class="sxs-lookup"><span data-stu-id="213d0-191">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="213d0-192">Такое может случаться из-за ошибок при вводе или из-за того, что средство было перемещено либо устарело.</span><span class="sxs-lookup"><span data-stu-id="213d0-192">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="213d0-193">Если средство размещено на сайте NuGet.org, один из способов гарантировать правильность имени — выполнить поиск средства на сайте NuGet.org и скопировать команду установки.</span><span class="sxs-lookup"><span data-stu-id="213d0-193">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="213d0-194">См. также</span><span class="sxs-lookup"><span data-stu-id="213d0-194">See also</span></span>

* [<span data-ttu-id="213d0-195">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="213d0-195">.NET Core tools</span></span>](global-tools.md)
