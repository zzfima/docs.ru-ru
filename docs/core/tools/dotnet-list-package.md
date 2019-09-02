---
title: Команда dotnet add package
description: Команду dotnet list package удобно использовать для получения списка ссылок на пакеты для проекта или решения.
ms.date: 06/26/2019
ms.openlocfilehash: 48eef0ccc6acf2bbd6c1acf748870882d2480ce5
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168020"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="ddc7e-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="ddc7e-103">dotnet list package</span></span>

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a><span data-ttu-id="ddc7e-104">name</span><span class="sxs-lookup"><span data-stu-id="ddc7e-104">Name</span></span>

<span data-ttu-id="ddc7e-105">`dotnet list package` — перечисляет ссылки на пакет для проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-105">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ddc7e-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ddc7e-106">Synopsis</span></span>

```console
dotnet list [<PROJECT>|<SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--interactive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ddc7e-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ddc7e-107">Description</span></span>

<span data-ttu-id="ddc7e-108">Команду `dotnet list package` удобно использовать для получения списка всех ссылок на пакеты NuGet для определенного проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-108">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="ddc7e-109">Сначала нужно создать проект, чтобы получить ресурсы, необходимые для обработки этой командой.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-109">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="ddc7e-110">В следующем примере показаны выходные данные команды `dotnet list package` для проекта [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):</span><span class="sxs-lookup"><span data-stu-id="ddc7e-110">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="ddc7e-111">В столбце **Requested** приводится ссылка на версию пакета, указанную в файле проекта. Это может быть и диапазон версий.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-111">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="ddc7e-112">В столбце **Resolved** указана версия, которая сейчас используется в проекте. Это значение всегда является одиночным.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-112">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="ddc7e-113">Символ `(A)`, отображающийся рядом с именами пакетов, обозначает [неявные ссылки на пакеты](csproj.md#implicit-package-references). Такие ссылки получены из параметров проекта (тип `Sdk`, свойство `<TargetFramework>` или `<TargetFrameworks>` и т. д.)</span><span class="sxs-lookup"><span data-stu-id="ddc7e-113">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="ddc7e-114">Используйте параметр `--outdated`, чтобы узнать, доступны ли новые версии пакетов, которые вы используете в проектах.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-114">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="ddc7e-115">По умолчанию параметр `--outdated` выводит список последних стабильных версий пакетов, если разрешенная версия не является предварительной версией.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-115">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="ddc7e-116">Чтобы при отображении списка новых версий отображались и предварительные версии, укажите параметр `--include-prerelease`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-116">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="ddc7e-117">Ниже приведены выходные данные команды `dotnet list package --outdated --include-prerelease` для тоже же проекта, как и в предыдущем примере:</span><span class="sxs-lookup"><span data-stu-id="ddc7e-117">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

<span data-ttu-id="ddc7e-118">Чтобы узнать, есть ли у проекта транзитивные зависимости, воспользуйтесь параметром `--include-transitive`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-118">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="ddc7e-119">Транзитивные зависимости возникают при добавлении пакета в проект, который в свою очередь зависит от другого пакета.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-119">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="ddc7e-120">В следующем примере показаны выходные данные выполнения команды `dotnet list package --include-transitive` для проекта [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), в которых отображаются пакеты верхнего уровня и пакеты, от которых они зависят:</span><span class="sxs-lookup"><span data-stu-id="ddc7e-120">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a><span data-ttu-id="ddc7e-121">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ddc7e-121">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="ddc7e-122">Файл проекта или решения для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-122">The project or solution file to operate on.</span></span> <span data-ttu-id="ddc7e-123">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="ddc7e-124">Если найдено несколько решений или проектов, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-124">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="ddc7e-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="ddc7e-125">Options</span></span>

* **`--config <SOURCE>`**

  <span data-ttu-id="ddc7e-126">Источники NuGet, используемые при поиске более новых версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-126">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="ddc7e-127">Требует указать параметр `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-127">Requires the `--outdated` option.</span></span>

* **`--framework <FRAMEWORK>`**

  <span data-ttu-id="ddc7e-128">Отображает только пакеты для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ddc7e-128">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="ddc7e-129">Чтобы указать несколько платформ, задайте параметр несколько раз.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-129">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="ddc7e-130">Например, `--framework netcoreapp2.2 --framework netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-130">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="ddc7e-131">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-131">Prints out a short help for the command.</span></span>

* **`--highest-minor`**

  <span data-ttu-id="ddc7e-132">Учитывает только пакеты с соответствующим номером основной версии при поиске более новых версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-132">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="ddc7e-133">Требует указать параметр `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-133">Requires the `--outdated` option.</span></span>

* **`--highest-patch`**

  <span data-ttu-id="ddc7e-134">Учитывает только пакеты с соответствующими номерами основной и дополнительной версий при поиске более новых версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-134">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="ddc7e-135">Требует указать параметр `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-135">Requires the `--outdated` option.</span></span>

* **`--include-prerelease`**

  <span data-ttu-id="ddc7e-136">Учитывает пакеты с предварительными версиями при поиске более новых версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-136">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="ddc7e-137">Требует указать параметр `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-137">Requires the `--outdated` option.</span></span>

* **`--include-transitive`**

  <span data-ttu-id="ddc7e-138">Выводит список транзитивных пакетов, кроме пакетов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-138">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="ddc7e-139">Указав этот параметр, вы получите список пакетов, от которых зависят пакеты верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-139">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

* **`--interactive`**

  <span data-ttu-id="ddc7e-140">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-140">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="ddc7e-141">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-141">For example, to complete authentication.</span></span> <span data-ttu-id="ddc7e-142">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-142">Available since .NET Core 3.0 SDK.</span></span>

* **`--outdated`**

  <span data-ttu-id="ddc7e-143">Позволяет получить список пакетов, для которых доступны более новые версии.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-143">Lists packages that have newer versions available.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="ddc7e-144">Источники NuGet, используемые при поиске более новых версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-144">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="ddc7e-145">Требует указать параметр `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="ddc7e-145">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="ddc7e-146">Примеры</span><span class="sxs-lookup"><span data-stu-id="ddc7e-146">Examples</span></span>

* <span data-ttu-id="ddc7e-147">Вывод списка ссылок на пакеты определенного проекта:</span><span class="sxs-lookup"><span data-stu-id="ddc7e-147">List package references of a specific project:</span></span>

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* <span data-ttu-id="ddc7e-148">Вывод списка ссылок на пакеты, для которых доступны более новые версии, включая предварительные версии:</span><span class="sxs-lookup"><span data-stu-id="ddc7e-148">List package references that have newer versions available, including prerelease versions:</span></span>

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* <span data-ttu-id="ddc7e-149">Вывод списка ссылок на пакеты для определенной целевой платформы:</span><span class="sxs-lookup"><span data-stu-id="ddc7e-149">List package references for a specific target framework:</span></span>

  ```console
  dotnet list package --framework netcoreapp3.0
  ```
