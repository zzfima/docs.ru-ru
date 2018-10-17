---
title: Библиотеки .NET и NuGet
description: Практические рекомендации для упаковки с NuGet для библиотеки .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374507"
---
# <a name="nuget"></a><span data-ttu-id="b456b-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="b456b-103">NuGet</span></span>

<span data-ttu-id="b456b-104">NuGet — это диспетчер пакетов для экосистемы .NET и разработчикам основной способ обнаружения и получения библиотек с открытым кодом .NET.</span><span class="sxs-lookup"><span data-stu-id="b456b-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="b456b-105">[NuGet.org](https://www.nuget.org/), это бесплатная служба, предоставляемые корпорацией Майкрософт, за размещение пакетов NuGet, является основным узлом для открытых пакетов NuGet, но можно опубликовать в пользовательских службах NuGet как [MyGet](https://www.myget.org/) и [артефакты Azure ](https://azure.microsoft.com/services/devops/artifacts/).</span><span class="sxs-lookup"><span data-stu-id="b456b-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="b456b-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="b456b-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="b456b-107">Создание пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="b456b-107">Create a NuGet package</span></span>

<span data-ttu-id="b456b-108">Пакет NuGet (`*.nupkg`) представляет собой файл zip, содержащий сборки .NET и связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="b456b-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="b456b-109">Существует два основных способа для создания пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="b456b-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="b456b-110">Является новой и рекомендуемый способ для создания пакета из стиле пакетов SDK для проекта (файл проекта, содержимое которых начинается с `<Project Sdk="Microsoft.NET.Sdk">`).</span><span class="sxs-lookup"><span data-stu-id="b456b-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="b456b-111">Сборки и целевые объекты автоматически добавляются в пакет и оставшихся метаданных добавляется в файл MSBuild, например пакета имя и номер версии.</span><span class="sxs-lookup"><span data-stu-id="b456b-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="b456b-112">Компиляция с [ `dotnet pack` ](../../core/tools/dotnet-pack.md) выходные данные команды `*.nupkg` файл, а не сборки.</span><span class="sxs-lookup"><span data-stu-id="b456b-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

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

<span data-ttu-id="b456b-113">Прежний способ создания пакета NuGet — с `*.nuspec` файл и `nuget.exe` средство командной строки.</span><span class="sxs-lookup"><span data-stu-id="b456b-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="b456b-114">Файл nuspec предоставляет контроле, но должны четко указывать, какие сборки и целевых объектов, включаемых в окончательный пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="b456b-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="b456b-115">Это легко допустить ошибку или кому-либо необходимо обновить файл nuspec, при внесении изменений.</span><span class="sxs-lookup"><span data-stu-id="b456b-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="b456b-116">Преимуществом nuspec, является его можно использовать создание пакетов NuGet для платформы, которые еще не поддерживают файла стиле пакетов SDK для проекта.</span><span class="sxs-lookup"><span data-stu-id="b456b-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="b456b-117">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** с файлом проекта стиле пакетов SDK для создание пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="b456b-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="b456b-118">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** Настройка SourceLink Добавление метаданных элемента управления источника сборки и пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="b456b-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="b456b-119">Зависимости пакета</span><span class="sxs-lookup"><span data-stu-id="b456b-119">Package dependencies</span></span>

<span data-ttu-id="b456b-120">Зависимости пакета NuGet рассматриваются подробно в [зависимости](./dependencies.md) статьи.</span><span class="sxs-lookup"><span data-stu-id="b456b-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="b456b-121">Важные метаданные пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="b456b-121">Important NuGet package metadata</span></span>

<span data-ttu-id="b456b-122">Пакет NuGet поддерживает многие [свойства метаданных](/nuget/reference/nuspec).</span><span class="sxs-lookup"><span data-stu-id="b456b-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="b456b-123">В следующей таблице содержатся основные метаданные, которые должен предоставить каждый проект с открытым кодом:</span><span class="sxs-lookup"><span data-stu-id="b456b-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="b456b-124">Имя свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="b456b-124">MSBuild Property name</span></span>              | <span data-ttu-id="b456b-125">Имя Nuspec</span><span class="sxs-lookup"><span data-stu-id="b456b-125">Nuspec name</span></span>              | <span data-ttu-id="b456b-126">Описание</span><span class="sxs-lookup"><span data-stu-id="b456b-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="b456b-127">Идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="b456b-127">The package identifier.</span></span> <span data-ttu-id="b456b-128">Можно зарезервировать префикс из идентификатора, если он удовлетворяет [критерии](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="b456b-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="b456b-129">Версия пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="b456b-129">NuGet package version.</span></span> <span data-ttu-id="b456b-130">Дополнительные сведения см. в разделе [пакет NuGet версии](./versioning.md#nuget-package-version).</span><span class="sxs-lookup"><span data-stu-id="b456b-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="b456b-131">Понятный заголовок пакета.</span><span class="sxs-lookup"><span data-stu-id="b456b-131">A human-friendly title of the package.</span></span> <span data-ttu-id="b456b-132">По умолчанию используется `PackageId`.</span><span class="sxs-lookup"><span data-stu-id="b456b-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="b456b-133">Подробное описание пакета, который отображается в пользовательском Интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b456b-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="b456b-134">Разделенный запятыми список авторов пакетов, совпадающих с именами профилей на сайте nuget.org.</span><span class="sxs-lookup"><span data-stu-id="b456b-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="b456b-135">Разделенный пробелами список тегов и ключевых слов, описывающих пакет.</span><span class="sxs-lookup"><span data-stu-id="b456b-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="b456b-136">Теги используются при поиске пакетов.</span><span class="sxs-lookup"><span data-stu-id="b456b-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="b456b-137">URL-адрес изображения для использования в качестве значка для пакета.</span><span class="sxs-lookup"><span data-stu-id="b456b-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="b456b-138">URL-адрес должен использоваться протокол HTTPS, и изображение должно быть 64 x 64 и с прозрачным фоном.</span><span class="sxs-lookup"><span data-stu-id="b456b-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="b456b-139">URL-адрес для домашней страницы или источник репозитория проекта.</span><span class="sxs-lookup"><span data-stu-id="b456b-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="b456b-140">URL-адрес лицензии проекта.</span><span class="sxs-lookup"><span data-stu-id="b456b-140">A URL to the project license.</span></span> <span data-ttu-id="b456b-141">Может быть URL-адрес `LICENSE` файл в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="b456b-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="b456b-142">**Попробуйте ✔️** Выбор имени пакета NuGet с префиксом, отвечающий резервирование префикса NuGet [критерии](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="b456b-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="b456b-143">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** с помощью `LICENSE` файл в системе управления версиями как `LicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="b456b-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="b456b-144">Например [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span><span class="sxs-lookup"><span data-stu-id="b456b-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b456b-145">Объект проект без лицензии по умолчанию равно [авторские права монопольного](https://choosealicense.com/no-permission/), что делает невозможным для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="b456b-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="b456b-146">**СДЕЛАТЬ ✔️** использовать записи href HTTPS для вашего значок пакета.</span><span class="sxs-lookup"><span data-stu-id="b456b-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="b456b-147">Как NuGet.org сайтах с поддержкой HTTPS и отображении изображения отличных от HTTPS будет создавать предупреждения о смешанном содержимом.</span><span class="sxs-lookup"><span data-stu-id="b456b-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="b456b-148">**СДЕЛАТЬ ✔️** используется изображение значка пакета, 64 x 64 с прозрачным фоном для удобства просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="b456b-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="b456b-149">Пакеты предварительного выпуска</span><span class="sxs-lookup"><span data-stu-id="b456b-149">Pre-release packages</span></span>

<span data-ttu-id="b456b-150">Пакеты NuGet с суффиксом версии считаются [предварительной версии](/nuget/create-packages/prerelease-packages).</span><span class="sxs-lookup"><span data-stu-id="b456b-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="b456b-151">По умолчанию пользовательский Интерфейс диспетчера пакетов NuGet отображает стабильные выпуски, если пользователь соглашается на участие в предварительной версии пакетов, что идеально подходит для тестирования пользователя с ограниченными правами пакеты предварительного выпуска.</span><span class="sxs-lookup"><span data-stu-id="b456b-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="b456b-152">Стабильного пакета не может зависеть от предварительной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="b456b-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="b456b-153">Необходимо предоставить свои собственные пакету предварительного выпуска или зависят от более ранней версии стабильной.</span><span class="sxs-lookup"><span data-stu-id="b456b-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="b456b-154">![Зависимость предварительной версии пакета NuGet](./media/nuget/nuget-prerelease-package.png "зависимость предварительной версии пакета NuGet")</span><span class="sxs-lookup"><span data-stu-id="b456b-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="b456b-155">**СДЕЛАТЬ ✔️** публикация предварительной версии пакета при тестировании, предварительном просмотре или экспериментов.</span><span class="sxs-lookup"><span data-stu-id="b456b-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="b456b-156">**СДЕЛАТЬ ✔️** публикации стабильного пакета при его готовности чтобы другие стабильные пакеты можно сослаться на него.</span><span class="sxs-lookup"><span data-stu-id="b456b-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="b456b-157">Пакеты символов</span><span class="sxs-lookup"><span data-stu-id="b456b-157">Symbol packages</span></span>

<span data-ttu-id="b456b-158">NuGet поддерживает [формирование пакета отдельный символ](/nuget/create-packages/symbol-packages) содержащий отладочные файлы PDB-ФАЙЛ вместе с основной пакет, содержащий сборки .NET.</span><span class="sxs-lookup"><span data-stu-id="b456b-158">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing debug PDB files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="b456b-159">Пакеты символов суть они размещены на сервере символов и загружаются только с помощью средства, как Visual Studio по требованию.</span><span class="sxs-lookup"><span data-stu-id="b456b-159">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="b456b-160">В настоящее время основной общедоступного узла для символов - [SymbolSource](http://www.symbolsource.org/) -не поддерживает переносимые PDB-файлы создан в стиле пакетов SDK для проектов и пакетов символов не полезны.</span><span class="sxs-lookup"><span data-stu-id="b456b-160">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the portable PDBs created by SDK-style projects and symbol packages aren't useful.</span></span>

<span data-ttu-id="b456b-161">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** внедрение PDB-файлы в главный пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="b456b-161">**✔️ CONSIDER** embedding PDBs in the main NuGet package.</span></span>

<span data-ttu-id="b456b-162">**ИЗБЕГАЙТЕ ❌** Создание пакета символов, содержащий PDB-файлов.</span><span class="sxs-lookup"><span data-stu-id="b456b-162">**❌ AVOID** creating a symbols package containing PDBs.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b456b-163">[Назад](./strong-naming.md)
[Вперед](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="b456b-163">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
