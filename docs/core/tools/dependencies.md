---
title: Управление зависимостями в .NET Core
description: Сведения об управлении зависимостями проекта для приложения .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157249"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="4bf08-103">Управление зависимостями в приложениях .NET Core</span><span class="sxs-lookup"><span data-stu-id="4bf08-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="4bf08-104">Эта статья описывает, как добавлять и удалять зависимости путем изменения файла проекта или с помощью интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="4bf08-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="4bf08-105">Элемент \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="4bf08-105">The \<PackageReference> element</span></span>

<span data-ttu-id="4bf08-106">Элемент файла проекта `<PackageReference>` имеет следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="4bf08-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="4bf08-107">Атрибут `Include` указывает идентификатор пакета, добавляемого в проект.</span><span class="sxs-lookup"><span data-stu-id="4bf08-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="4bf08-108">Атрибут `Version` указывает версию, которую необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="4bf08-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="4bf08-109">Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="4bf08-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="4bf08-110">Если вы не знакомы с синтаксисом файла проекта, см. дополнительные сведения в [справочной документации по проектам MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="4bf08-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="4bf08-111">Зависимость, доступная только в конкретном целевом объекте, добавляется с использованием условий, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4bf08-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="4bf08-112">Зависимость в предыдущем примере будет допустимой только при сборке для указанного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="4bf08-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="4bf08-113">Элемент `$(TargetFramework)` в этом условии представляет собой задаваемое в проекте свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4bf08-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="4bf08-114">Для наиболее распространенных приложений .NET Core это не требуется.</span><span class="sxs-lookup"><span data-stu-id="4bf08-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="4bf08-115">Добавление зависимости путем изменения файла проекта</span><span class="sxs-lookup"><span data-stu-id="4bf08-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="4bf08-116">Чтобы добавить зависимость, добавьте элемент `<PackageReference>` внутрь элемента `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="4bf08-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="4bf08-117">Можно добавить существующий элемент `<ItemGroup>` или создать новый.</span><span class="sxs-lookup"><span data-stu-id="4bf08-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="4bf08-118">В следующем примере используется проект консольного приложения по умолчанию, созданный с помощью `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="4bf08-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="4bf08-119">Добавление зависимости с помощью интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="4bf08-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="4bf08-120">Чтобы добавить зависимость, выполните команду [dotnet add package](dotnet-add-package.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4bf08-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="4bf08-121">Удаление зависимости путем изменения файла проекта</span><span class="sxs-lookup"><span data-stu-id="4bf08-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="4bf08-122">Чтобы удалить зависимость, удалите ее элемент `<PackageReference>` из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="4bf08-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="4bf08-123">Удаление зависимости с помощью интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="4bf08-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="4bf08-124">Чтобы удалить зависимость, выполните команду [dotnet remove package](dotnet-remove-package.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4bf08-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="4bf08-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4bf08-125">See also</span></span>

* [<span data-ttu-id="4bf08-126">Пакеты NuGet в файлах проекта</span><span class="sxs-lookup"><span data-stu-id="4bf08-126">NuGet packages in project files</span></span>](../project-sdk/msbuild-props.md#nuget-packages)
* <span data-ttu-id="4bf08-127">[Команда dotnet list package](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="4bf08-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
