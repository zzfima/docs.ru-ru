---
title: Управление зависимостями в средствах .NET Core
description: Сведения об управлении зависимостями с помощью средств .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: 28280dc05e746cdef4e90870cd4cb528382c45bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787864"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="ee07c-103">Управление зависимостями с помощью пакета SDK для .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ee07c-103">Manage dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="ee07c-104">Помимо переноса проектов .NET Core из файла project.json в CSPROJ-файл и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, обеспечивающих отслеживание зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ee07c-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="ee07c-105">Для проектов .NET Core это аналогично функции, которую раньше выполнял файл project.json.</span><span class="sxs-lookup"><span data-stu-id="ee07c-105">For .NET Core projects, this is similar to what project.json did.</span></span> <span data-ttu-id="ee07c-106">Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet.</span><span class="sxs-lookup"><span data-stu-id="ee07c-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="ee07c-107">Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="ee07c-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span>

<span data-ttu-id="ee07c-108">В этом документе описывается новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="ee07c-108">This document describes the new reference type.</span></span> <span data-ttu-id="ee07c-109">Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="ee07c-109">It also shows how to add a package dependency using this new reference type to your project.</span></span>

## <a name="the-new-packagereference-element"></a><span data-ttu-id="ee07c-110">Новый элемент \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="ee07c-110">The new \<PackageReference> element</span></span>

<span data-ttu-id="ee07c-111">Элемент `<PackageReference>` имеет следующую базовую структуру:</span><span class="sxs-lookup"><span data-stu-id="ee07c-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="ee07c-112">Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="ee07c-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="ee07c-113">Ключевым является оператор `Include`, указывающий идентификатор пакета, который нужно добавить в проект.</span><span class="sxs-lookup"><span data-stu-id="ee07c-113">The key is the `Include` statement, which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="ee07c-114">Дочерний элемент `<Version>` указывает версию, которую необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="ee07c-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="ee07c-115">Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="ee07c-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="ee07c-116">Если вы не знакомы с общими понятиями синтаксиса `csproj`, используйте [справочную документацию по проекту MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) для ознакомления с ними.</span><span class="sxs-lookup"><span data-stu-id="ee07c-116">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="ee07c-117">Добавление зависимости, которая доступна только в конкретном целевом объекте, выполняется с использованием условий, аналогичных в приведенном далее примере.</span><span class="sxs-lookup"><span data-stu-id="ee07c-117">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="ee07c-118">Указанное выше означает, что зависимость будет действительной только в том случае, если для затронутого целевого объекта выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="ee07c-118">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="ee07c-119">Элемент `$(TargetFramework)` в этом условии представляет собой заданное в проекте свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ee07c-119">The `$(TargetFramework)` in the condition is an MSBuild property that is being set in the project.</span></span> <span data-ttu-id="ee07c-120">Для наиболее распространенных приложений .NET Core это не требуется.</span><span class="sxs-lookup"><span data-stu-id="ee07c-120">For most common .NET Core applications, you will not need to do this.</span></span>

## <a name="add-a-dependency-to-the-project"></a><span data-ttu-id="ee07c-121">Добавление зависимости в проект</span><span class="sxs-lookup"><span data-stu-id="ee07c-121">Add a dependency to the project</span></span>

<span data-ttu-id="ee07c-122">Добавить зависимость в проект очень просто.</span><span class="sxs-lookup"><span data-stu-id="ee07c-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="ee07c-123">Ниже показано, как добавить в проект Json.NET версии `9.0.1`.</span><span class="sxs-lookup"><span data-stu-id="ee07c-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="ee07c-124">Это применимо и к любой другой зависимости NuGet.</span><span class="sxs-lookup"><span data-stu-id="ee07c-124">Of course, it is applicable to any other NuGet dependency.</span></span>

<span data-ttu-id="ee07c-125">При открытии файла проекта вы увидите не менее двух узлов `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="ee07c-125">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="ee07c-126">Можно заметить, что на одном из узлов уже есть элементы `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="ee07c-126">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="ee07c-127">Вы можете добавить новую зависимость в этот узел или создать новый. Поступайте по своему усмотрению, так как результат от этого не изменится.</span><span class="sxs-lookup"><span data-stu-id="ee07c-127">You can add your new dependency to this node, or create a new one; it is up to you, as the result will be the same.</span></span>

<span data-ttu-id="ee07c-128">В приведенном ниже примере используется шаблон по умолчанию, который удаляется командой `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="ee07c-128">The following example uses the default template that's dropped by `dotnet new console`.</span></span> <span data-ttu-id="ee07c-129">Это простое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="ee07c-129">This is a simple console application.</span></span> <span data-ttu-id="ee07c-130">При открытии проекта вы увидите узел `<ItemGroup>`, в котором уже есть элемент `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="ee07c-130">When you open up the project, you'll find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="ee07c-131">Добавьте к нему следующее:</span><span class="sxs-lookup"><span data-stu-id="ee07c-131">Add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="ee07c-132">После этого сохраните проект и выполните команду `dotnet restore` для установки зависимости.</span><span class="sxs-lookup"><span data-stu-id="ee07c-132">After this, save the project and run the `dotnet restore` command to install the dependency.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ee07c-133">Весь проект выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ee07c-133">The full project looks like this:</span></span>

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

## <a name="remove-a-dependency-from-the-project"></a><span data-ttu-id="ee07c-134">Удаление зависимости из проекта</span><span class="sxs-lookup"><span data-stu-id="ee07c-134">Remove a dependency from the project</span></span>

<span data-ttu-id="ee07c-135">Чтобы удалить зависимость из файла проекта, достаточно просто удалить `<PackageReference>` из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="ee07c-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
