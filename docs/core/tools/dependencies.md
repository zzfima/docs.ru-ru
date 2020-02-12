---
title: Управление зависимостями в средствах .NET Core
description: Сведения об управлении зависимостями с помощью средств .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: 916daca0240c10dc63ca96048590a426bc51d450
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965624"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="2969e-103">Управление зависимостями с помощью пакета SDK для .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="2969e-103">Manage dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="2969e-104">Помимо переноса проектов .NET Core из файла project.json в CSPROJ-файл и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, обеспечивающих отслеживание зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2969e-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="2969e-105">Для проектов .NET Core это аналогично функции, которую раньше выполнял файл project.json.</span><span class="sxs-lookup"><span data-stu-id="2969e-105">For .NET Core projects, this is similar to what project.json did.</span></span> <span data-ttu-id="2969e-106">Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet.</span><span class="sxs-lookup"><span data-stu-id="2969e-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="2969e-107">Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="2969e-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span>

<span data-ttu-id="2969e-108">В этом документе описывается новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="2969e-108">This document describes the new reference type.</span></span> <span data-ttu-id="2969e-109">Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="2969e-109">It also shows how to add a package dependency using this new reference type to your project.</span></span>

## <a name="the-new-packagereference-element"></a><span data-ttu-id="2969e-110">Новый элемент \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="2969e-110">The new \<PackageReference> element</span></span>

<span data-ttu-id="2969e-111">Элемент `<PackageReference>` имеет следующую базовую структуру:</span><span class="sxs-lookup"><span data-stu-id="2969e-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="2969e-112">Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="2969e-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="2969e-113">Ключевым является инструкция `Include`, указывающая идентификатор пакета, который нужно добавить в проект.</span><span class="sxs-lookup"><span data-stu-id="2969e-113">The key is the `Include` statement, which specifies the package ID that you wish to add to the project.</span></span> <span data-ttu-id="2969e-114">Дочерний элемент `<Version>` указывает версию, которую необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="2969e-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="2969e-115">Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="2969e-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="2969e-116">Если вы не знакомы с синтаксисом проектов и файлов, см. дополнительные сведения в [справочной документации по проектам MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="2969e-116">If you're not familiar with the project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="2969e-117">Зависимость, доступная только в конкретном целевом объекте, добавляется с использованием условий, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2969e-117">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="2969e-118">Зависимость будет допустимой только при сборке для указанного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="2969e-118">The dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="2969e-119">Элемент `$(TargetFramework)` в этом условии представляет собой задаваемое в проекте свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="2969e-119">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="2969e-120">Для наиболее распространенных приложений .NET Core это не требуется.</span><span class="sxs-lookup"><span data-stu-id="2969e-120">For most common .NET Core applications, you will not need to do this.</span></span>

## <a name="add-a-dependency-to-the-project"></a><span data-ttu-id="2969e-121">Добавление зависимости в проект</span><span class="sxs-lookup"><span data-stu-id="2969e-121">Add a dependency to the project</span></span>

<span data-ttu-id="2969e-122">Добавить зависимость в проект очень просто.</span><span class="sxs-lookup"><span data-stu-id="2969e-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="2969e-123">Ниже показано, как добавить в проект Json.NET версии `9.0.1`.</span><span class="sxs-lookup"><span data-stu-id="2969e-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="2969e-124">Это применимо и к любой другой зависимости NuGet.</span><span class="sxs-lookup"><span data-stu-id="2969e-124">Of course, it is applicable to any other NuGet dependency.</span></span>

<span data-ttu-id="2969e-125">Файл проекта содержит как минимум два узла `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="2969e-125">Your project file has two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="2969e-126">В одном из узлов уже есть элементы `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="2969e-126">One of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="2969e-127">Вы можете добавить зависимость в этот узел или создать новый — результат от этого не изменится.</span><span class="sxs-lookup"><span data-stu-id="2969e-127">You can add your new dependency to this node or create a new one; the result will be the same.</span></span>

<span data-ttu-id="2969e-128">В приведенном ниже примере используется шаблон по умолчанию, который удаляется командой `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="2969e-128">The following example uses the default template that's dropped by `dotnet new console`.</span></span> <span data-ttu-id="2969e-129">Это простое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="2969e-129">This is a simple console application.</span></span> <span data-ttu-id="2969e-130">При открытии проекта вы увидите узел `<ItemGroup>`, в котором уже есть элемент `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="2969e-130">When you open up the project, you'll find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="2969e-131">Добавьте к нему следующее:</span><span class="sxs-lookup"><span data-stu-id="2969e-131">Add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="2969e-132">После этого сохраните проект и выполните команду `dotnet restore` для установки зависимости.</span><span class="sxs-lookup"><span data-stu-id="2969e-132">After this, save the project and run the `dotnet restore` command to install the dependency.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2969e-133">Весь проект выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2969e-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="remove-a-dependency-from-the-project"></a><span data-ttu-id="2969e-134">Удаление зависимости из проекта</span><span class="sxs-lookup"><span data-stu-id="2969e-134">Remove a dependency from the project</span></span>

<span data-ttu-id="2969e-135">Чтобы удалить зависимость из файла проекта, достаточно просто удалить `<PackageReference>` из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="2969e-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
