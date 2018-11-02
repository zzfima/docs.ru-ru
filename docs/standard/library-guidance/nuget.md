---
title: NuGet и библиотеки .NET
description: Практические рекомендации по упаковке библиотек .NET с помощью NuGet.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185631"
---
# <a name="nuget"></a><span data-ttu-id="553e3-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="553e3-103">NuGet</span></span>

<span data-ttu-id="553e3-104">NuGet — это диспетчер пакетов для экосистемы .NET, который используется разработчиками как основное средство для поиска и получения библиотек .NET с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="553e3-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="553e3-105">Бесплатная служба [NuGet.org](https://www.nuget.org/), предоставляемая корпорацией Майкрософт для размещения пакетов NuGet, является основным узлом для общедоступных пакетов NuGet. Также поддерживается публикация в пользовательских службах NuGet типа [MyGet](https://www.myget.org/) и [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span><span class="sxs-lookup"><span data-stu-id="553e3-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="553e3-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="553e3-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="553e3-107">Создание пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="553e3-107">Create a NuGet package</span></span>

<span data-ttu-id="553e3-108">Пакет NuGet (`*.nupkg`) — это ZIP-файл со сборками .NET и связанными метаданными.</span><span class="sxs-lookup"><span data-stu-id="553e3-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="553e3-109">Пакет NuGet можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="553e3-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="553e3-110">Мы рекомендуем использовать более новый подход — создавать пакет из проекта в стиле SDK (это файл проекта, содержимое которого начинается с `<Project Sdk="Microsoft.NET.Sdk">`).</span><span class="sxs-lookup"><span data-stu-id="553e3-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="553e3-111">Сборки и целевые объекты автоматически добавляются в пакет, а метаданные, например имя пакета и номер версии, — в файл MSBuild.</span><span class="sxs-lookup"><span data-stu-id="553e3-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="553e3-112">Компиляция с помощью команды [`dotnet pack`](../../core/tools/dotnet-pack.md) создает файл `*.nupkg`, а не сборки.</span><span class="sxs-lookup"><span data-stu-id="553e3-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="553e3-113">Более старый способ создания пакета NuGet — это файл `*.nuspec` и средство командной строки `nuget.exe`.</span><span class="sxs-lookup"><span data-stu-id="553e3-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="553e3-114">Файл с расширением .nuspec предоставляет функции управления, но указывать сборки и целевые объекты для включения в пакет NuGet нужно внимательно.</span><span class="sxs-lookup"><span data-stu-id="553e3-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="553e3-115">Здесь очень легко допустить ошибку или забыть обновить файл .nuspec после внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="553e3-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="553e3-116">Важное преимущество файла .nuspec заключается в том, что он позволяет создать пакет NuGet для платформы, которая еще не поддерживает файлы проектов в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="553e3-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="553e3-117">**✔️ ДОПУСТИМО.** Вы можете использовать файл проекта в стиле SDK для создания пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="553e3-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="553e3-118">**✔️ ДОПУСТИМО.** Вы можете настроить SourceLink, чтобы добавить метаданные системы управления версиями в сборки и пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="553e3-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="553e3-119">Зависимости пакета</span><span class="sxs-lookup"><span data-stu-id="553e3-119">Package dependencies</span></span>

<span data-ttu-id="553e3-120">См. сведения о [зависимостях пакета NuGet](./dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="553e3-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="553e3-121">Важные метаданные пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="553e3-121">Important NuGet package metadata</span></span>

<span data-ttu-id="553e3-122">Пакет NuGet поддерживает многие [свойства метаданных](/nuget/reference/nuspec).</span><span class="sxs-lookup"><span data-stu-id="553e3-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="553e3-123">В следующей таблице собраны основные метаданные, которые должен предоставить каждый проект с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="553e3-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="553e3-124">Имя свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="553e3-124">MSBuild Property name</span></span>              | <span data-ttu-id="553e3-125">Имя Nuspec</span><span class="sxs-lookup"><span data-stu-id="553e3-125">Nuspec name</span></span>              | <span data-ttu-id="553e3-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="553e3-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="553e3-127">Идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="553e3-127">The package identifier.</span></span> <span data-ttu-id="553e3-128">Можно зарезервировать префикс из идентификатора, если он удовлетворяет [критериям](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="553e3-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="553e3-129">Версия пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="553e3-129">NuGet package version.</span></span> <span data-ttu-id="553e3-130">См. сведения о [версии пакета NuGet](./versioning.md#nuget-package-version).</span><span class="sxs-lookup"><span data-stu-id="553e3-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="553e3-131">Понятный заголовок пакета.</span><span class="sxs-lookup"><span data-stu-id="553e3-131">A human-friendly title of the package.</span></span> <span data-ttu-id="553e3-132">По умолчанию используется значение `PackageId`.</span><span class="sxs-lookup"><span data-stu-id="553e3-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="553e3-133">Подробное описание пакета для отображения в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="553e3-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="553e3-134">Разделенный запятыми список авторов пакета, обозначенных именами профилей на сайте nuget.org.</span><span class="sxs-lookup"><span data-stu-id="553e3-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="553e3-135">Разделенный пробелами список тегов и ключевых слов для описания пакета.</span><span class="sxs-lookup"><span data-stu-id="553e3-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="553e3-136">Теги используются при поиске пакетов.</span><span class="sxs-lookup"><span data-stu-id="553e3-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="553e3-137">URL-адрес изображения, которое будет использоваться как значок для пакета.</span><span class="sxs-lookup"><span data-stu-id="553e3-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="553e3-138">Это должен быть URL-адрес (HTTPS), указывающий на изображение размером 64×64 с прозрачным фоном.</span><span class="sxs-lookup"><span data-stu-id="553e3-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="553e3-139">URL-адрес домашней страницы или репозитория проекта.</span><span class="sxs-lookup"><span data-stu-id="553e3-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="553e3-140">URL-адрес текста лицензии проекта.</span><span class="sxs-lookup"><span data-stu-id="553e3-140">A URL to the project license.</span></span> <span data-ttu-id="553e3-141">Этот URL-адрес может указывать на файл `LICENSE` в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="553e3-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="553e3-142">**✔️ ДОПУСТИМО.** Вы можете выбрать имя пакета NuGet с префиксом, который соответствует [критериям](/nuget/reference/id-prefix-reservation) для резервирования префикса NuGet.</span><span class="sxs-lookup"><span data-stu-id="553e3-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="553e3-143">**✔️ ДОПУСТИМО.** Вы можете использовать файл `LICENSE` в системе управления версиями в качестве `LicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="553e3-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="553e3-144">Например, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span><span class="sxs-lookup"><span data-stu-id="553e3-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="553e3-145">Проект без лицензии по умолчанию получает статус [монопольного авторского права](https://choosealicense.com/no-permission/), то есть не может использоваться другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="553e3-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="553e3-146">**✔️ РЕКОМЕНДУЕТСЯ.**  Используйте атрибут href для определения HTTPS-ссылки, указывающей на значок пакета.</span><span class="sxs-lookup"><span data-stu-id="553e3-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="553e3-147">NuGet.org и другие аналогичные сайты работают с поддержкой HTTPS, поэтому при отображении изображения с другим протоколом появится предупреждение о смешанном типе содержимого.</span><span class="sxs-lookup"><span data-stu-id="553e3-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="553e3-148">**✔️ РЕКОМЕНДУЕТСЯ.** Используйте для значка пакета изображение размером 64×64 с прозрачным фоном, чтобы обеспечить оптимальную видимость.</span><span class="sxs-lookup"><span data-stu-id="553e3-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="553e3-149">Пакеты предварительного выпуска</span><span class="sxs-lookup"><span data-stu-id="553e3-149">Pre-release packages</span></span>

<span data-ttu-id="553e3-150">Пакеты NuGet с суффиксом версии получают статус [предварительной версии](/nuget/create-packages/prerelease-packages).</span><span class="sxs-lookup"><span data-stu-id="553e3-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="553e3-151">По умолчанию в пользовательском интерфейсе диспетчера пакетов NuGet отображаются только стабильные выпуски, если пользователь не согласился использовать пакеты предварительной версии. Благодаря такой политике пакеты предварительной версии предоставляются для тестирования ограниченному числу пользователей.</span><span class="sxs-lookup"><span data-stu-id="553e3-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="553e3-152">В пакетах стабильных выпусков нельзя указывать зависимости от пакетов предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="553e3-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="553e3-153">В таком случае переведите используемый пакет в режим предварительной версии или укажите зависимость от более ранней стабильной версии.</span><span class="sxs-lookup"><span data-stu-id="553e3-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="553e3-154">![Зависимость пакета NuGet в предварительной версии](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span><span class="sxs-lookup"><span data-stu-id="553e3-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="553e3-155">**✔️ РЕКОМЕНДУЕТСЯ.** Публикуйте пакет в режиме предварительной версии для тестирования, предварительного просмотра или экспериментов.</span><span class="sxs-lookup"><span data-stu-id="553e3-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="553e3-156">**✔️ РЕКОМЕНДУЕТСЯ.** Публикуйте стабильный выпуск пакета, когда он будет полностью готов, чтобы другие стабильные могли содержать ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="553e3-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="553e3-157">Пакеты символов</span><span class="sxs-lookup"><span data-stu-id="553e3-157">Symbol packages</span></span>

<span data-ttu-id="553e3-158">Файлы символов (`*.pdb`) создаются компилятором платформы .NET одновременно со сборками.</span><span class="sxs-lookup"><span data-stu-id="553e3-158">Symbol files (`*.pdb`) are produced by the .NET compiler alongside assemblies.</span></span> <span data-ttu-id="553e3-159">Файлы символов сопоставляют расположения выполнения с исходным кодом, что позволяет выполнить пошаговое выполнение с использованием отладчика.</span><span class="sxs-lookup"><span data-stu-id="553e3-159">Symbol files map execution locations to the original source code so you can step through source code as it is running using a debugger.</span></span> <span data-ttu-id="553e3-160">NuGet позволяет [создавать отдельные пакеты символов](/nuget/create-packages/symbol-packages) с файлами символов одновременно с основным пакетом сборок для .NET.</span><span class="sxs-lookup"><span data-stu-id="553e3-160">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing symbol files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="553e3-161">Предполагается, что пакеты символов будут размещаться на сервере символов и скачиваться по требованию только специальными средствами, такими как Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="553e3-161">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="553e3-162">Сейчас самая популярная платформа для символов [SymbolSource](http://www.symbolsource.org/) не поддерживает новый формат [переносимых файлов символов](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`), которые создаются из проектов в стиле SDK, и пакеты символов использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="553e3-162">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the new [portable symbol files](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span> <span data-ttu-id="553e3-163">Пока не появится рекомендуемый узел для размещения пакетов символов, можно внедрять файлы символов в основной пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="553e3-163">Until there is a recommended host for symbol packages, symbol files can be embedded in the main NuGet package.</span></span> <span data-ttu-id="553e3-164">Если вы создаете пакет NuGet из проекта в стиле SDK, файлы символов в него можно внедрить с помощью свойства `AllowedOutputExtensionsInPackageBuildOutputFolder`:</span><span class="sxs-lookup"><span data-stu-id="553e3-164">If you are building your NuGet package using an SDK-style project you can embed symbol files by setting the `AllowedOutputExtensionsInPackageBuildOutputFolder` property:</span></span> 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="553e3-165">**✔️ ДОПУСТИМО.** Вы можете внедрять файлы символов в основной пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="553e3-165">**✔️ CONSIDER** embedding symbol files in the main NuGet package.</span></span>

<span data-ttu-id="553e3-166">**❌ НЕЖЕЛАТЕЛЬНО.** Не создавайте пакет символов с файлами символов.</span><span class="sxs-lookup"><span data-stu-id="553e3-166">**❌ AVOID** creating a symbols package containing symbol files.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="553e3-167">[Назад](./strong-naming.md)
[Вперед](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="553e3-167">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
