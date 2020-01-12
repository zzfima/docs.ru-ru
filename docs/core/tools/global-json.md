---
title: Обзор global.json
description: Узнайте, как использовать файл global.json, чтобы задать версию пакета SDK для .NET Core при выполнении команд .NET Core CLI.
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 4da703266e98b209cdd031f4ea856b4d7c83930c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714176"
---
# <a name="globaljson-overview"></a><span data-ttu-id="79e14-103">Обзор global.json</span><span class="sxs-lookup"><span data-stu-id="79e14-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="79e14-104">С помощью файла *global.json* можно определить, какая версия пакета SDK для .NET Core используется при выполнении команд .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="79e14-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="79e14-105">Выбор пакета SDK для .NET Core не зависит от указания целевой среды выполнения проекта.</span><span class="sxs-lookup"><span data-stu-id="79e14-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="79e14-106">Версия пакета SDK для .NET Core указывает, какие версии средств .NET Core CLI используются.</span><span class="sxs-lookup"><span data-stu-id="79e14-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="79e14-107">Как правило, необходимо использовать последнюю версию средств, поэтому вам нужен файл *global.json*.</span><span class="sxs-lookup"><span data-stu-id="79e14-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="79e14-108">Дополнительные сведения о том, как вместо этого указать среду выполнения, см. в разделе [Целевые платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="79e14-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="79e14-109">Пакет SDK для .NET Core ищет файл *global.json* в текущем рабочем каталоге (который не обязательно совпадает с каталогом проекта) или в одном из его родительских каталогов.</span><span class="sxs-lookup"><span data-stu-id="79e14-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="79e14-110">Схема файла global.json</span><span class="sxs-lookup"><span data-stu-id="79e14-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="79e14-111">sdk</span><span class="sxs-lookup"><span data-stu-id="79e14-111">sdk</span></span>

<span data-ttu-id="79e14-112">Тип: Object</span><span class="sxs-lookup"><span data-stu-id="79e14-112">Type: Object</span></span>

<span data-ttu-id="79e14-113">Указывает сведения о пакете SDK для .NET Core для выбора.</span><span class="sxs-lookup"><span data-stu-id="79e14-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="79e14-114">version</span><span class="sxs-lookup"><span data-stu-id="79e14-114">version</span></span>

<span data-ttu-id="79e14-115">Тип: Строка</span><span class="sxs-lookup"><span data-stu-id="79e14-115">Type: String</span></span>

<span data-ttu-id="79e14-116">Версия пакета SDK для .NET Core для использования.</span><span class="sxs-lookup"><span data-stu-id="79e14-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="79e14-117">Обратите внимание, что это поле:</span><span class="sxs-lookup"><span data-stu-id="79e14-117">Note that this field:</span></span>

- <span data-ttu-id="79e14-118">Не поддерживает глобализацию, то есть необходимо указать полный номер версии.</span><span class="sxs-lookup"><span data-stu-id="79e14-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="79e14-119">Не поддерживает диапазон версий.</span><span class="sxs-lookup"><span data-stu-id="79e14-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="79e14-120">В следующем примере показано содержимое файла *global.json*.</span><span class="sxs-lookup"><span data-stu-id="79e14-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="79e14-121">global.json и .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="79e14-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="79e14-122">Полезно знать, какие версии доступны, чтобы задать нужную в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="79e14-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="79e14-123">Полный список поддерживаемых доступных пакетов SDK вы найдете на странице [скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="79e14-123">You can find the full list of supported available SDKs at the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span> <span data-ttu-id="79e14-124">Начиная с пакета SDK для .NET Core 2.1 можно выполнить следующую команду, чтобы проверить, какие версии пакета SDK уже установлены на вашем компьютере:</span><span class="sxs-lookup"><span data-stu-id="79e14-124">Starting with .NET Core 2.1 SDK, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="79e14-125">Чтобы установить дополнительные версии пакета SDK для .NET Core на компьютере, посетите страницу [скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="79e14-125">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="79e14-126">Вы можете создать новый файл *global.json* в текущем каталоге, выполнив команду [dotnet new](dotnet-new.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="79e14-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a><span data-ttu-id="79e14-127">Правила сопоставления</span><span class="sxs-lookup"><span data-stu-id="79e14-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="79e14-128">Правила сопоставления регулируются apphost, который является частью среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="79e14-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="79e14-129">Если у вас параллельно установлено несколько сред выполнения, используется последняя версия узла.</span><span class="sxs-lookup"><span data-stu-id="79e14-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="79e14-130">Начиная с .NET Core 2.0 при определении версии пакета SDK для использования применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="79e14-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="79e14-131">Если файл *global.json* не найден или в файле *global.json* не указана версия пакета SDK, используется последняя установленная версия пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="79e14-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="79e14-132">Последняя версия пакета SDK может быть обычным или предварительным выпуском — выбирается самый большой номер версии.</span><span class="sxs-lookup"><span data-stu-id="79e14-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="79e14-133">Если в файле *global.json* указана версия пакета SDK:</span><span class="sxs-lookup"><span data-stu-id="79e14-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="79e14-134">Если указанная версия пакета SDK найдена на компьютере, используется именно эта версия.</span><span class="sxs-lookup"><span data-stu-id="79e14-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="79e14-135">Если указанная версия пакета SDK не найдена на компьютере, используется последняя установленная **версия исправления** этой версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="79e14-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="79e14-136">Последняя установленная **версия исправления** пакета SDK может быть обычным или предварительным выпуском — используется самый большой номер версии.</span><span class="sxs-lookup"><span data-stu-id="79e14-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="79e14-137">В .NET Core 2.1 и более поздних версиях **версии исправления** ниже указанной **версии исправления** не учитываются при выборе пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="79e14-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="79e14-138">Если указанная версия пакета SDK и соответствующая **версия исправления** пакета SDK не найдена, выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="79e14-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="79e14-139">В настоящее время версия пакета SDK состоит из следующих частей:</span><span class="sxs-lookup"><span data-stu-id="79e14-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="79e14-140">**Главный выпуск** пакета SDK для .NET Core обозначен первой цифрой (`x`) в последней части номера (`xyz`) для версии пакета SDK 2.1.100 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="79e14-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="79e14-141">Как правило, пакет SDK для .NET Core имеет более короткий цикл выпуска, чем .NET Core.</span><span class="sxs-lookup"><span data-stu-id="79e14-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="79e14-142">**Версия исправления** обозначена двумя последними цифрами (`yz`) в последней части номера (`xyz`) для версии пакета SDK 2.1.100 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="79e14-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="79e14-143">Например, если вы указываете `2.1.300` в качестве версии пакета SDK, ищется пакет SDK до версии `2.1.399`, но `2.1.400` не считается версией исправления для `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="79e14-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="79e14-144">Версии пакета SDK для .NET Core с `2.1.100` по `2.1.201` были выпущены во время перехода между схемами номеров версий и некорректно обрабатывают нотацию `xyz`.</span><span class="sxs-lookup"><span data-stu-id="79e14-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="79e14-145">Если вы указываете эти версии в файле *global.json*, мы рекомендуем убедиться, что указанные версии установлены на целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="79e14-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="79e14-146">С пакетом SDK для .NET Core 1.x, когда вы указывали версию и точное соответствие не находилось, использовалась последняя установленная версия пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="79e14-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="79e14-147">Последняя версия пакета SDK может быть обычным или предварительным выпуском — выбирается самый большой номер версии.</span><span class="sxs-lookup"><span data-stu-id="79e14-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="79e14-148">Устранение неполадок с оповещениями сборки</span><span class="sxs-lookup"><span data-stu-id="79e14-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="79e14-149">Вы работаете с предварительной версией пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="79e14-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="79e14-150">Версию пакета SDK можно указать в файле global.json в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="79e14-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="79e14-151">Дополнительные сведения см. на странице <https://go.microsoft.com/fwlink/?linkid=869452></span><span class="sxs-lookup"><span data-stu-id="79e14-151">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="79e14-152">Это предупреждение означает, что проект компилируется с помощью предварительной версии пакета SDK для .NET Core, как описано в разделе [Правила сопоставления](#matching-rules).</span><span class="sxs-lookup"><span data-stu-id="79e14-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="79e14-153">Версии пакета SDK для .NET Core имеют гарантированное качество.</span><span class="sxs-lookup"><span data-stu-id="79e14-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="79e14-154">Но если вы не хотите использовать предварительную версию, добавьте файл *global.json* в структуру иерархии проекта, чтобы указать нужную версию пакета SDK, и с помощью `dotnet --list-sdks` убедитесь, что эта версия установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="79e14-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="79e14-155">Чтобы использовать новую версию после ее выпуска, удалите файл *global.json* или внесите в него изменения.</span><span class="sxs-lookup"><span data-stu-id="79e14-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="79e14-156">Запускаемый проект '{startupProject}' нацелен на версию платформы '.NETCoreApp' '{targetFrameworkVersion}'.</span><span class="sxs-lookup"><span data-stu-id="79e14-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="79e14-157">Эта версия средств командной строки .NET Entity Framework Core поддерживает только версию 2.0 или более позднюю.</span><span class="sxs-lookup"><span data-stu-id="79e14-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="79e14-158">Сведения об использовании более старой версии средств см. в разделе <https://go.microsoft.com/fwlink/?linkid=871254></span><span class="sxs-lookup"><span data-stu-id="79e14-158">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="79e14-159">Начиная с пакета SDK для .NET Core 2.1 (версия 2.1.300) поддерживается команда `dotnet ef`.</span><span class="sxs-lookup"><span data-stu-id="79e14-159">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="79e14-160">Это предупреждение означает, что проект предназначен для EF Core 1.0 или 1.1, которые несовместимы с пакетом SDK для .NET Core 2.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="79e14-160">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="79e14-161">Чтобы скомпилировать проект, установите пакет SDK для .NET Core 2.0 (версия 2.1.201) или более ранней версии на своем компьютере и определите необходимую версию пакета SDK с помощью файла *global.json*.</span><span class="sxs-lookup"><span data-stu-id="79e14-161">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="79e14-162">Дополнительные сведения о команде `dotnet ef` см. в разделе [Утилиты командной строки для EF Core .NET](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="79e14-162">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="79e14-163">См. также</span><span class="sxs-lookup"><span data-stu-id="79e14-163">See also</span></span>

- [<span data-ttu-id="79e14-164">Как разрешаются пакеты SDK проекта</span><span class="sxs-lookup"><span data-stu-id="79e14-164">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
