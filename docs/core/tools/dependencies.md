---
title: "Управление зависимостями в средствах .NET Core"
description: "Сведения об управлении зависимостями с помощью средств .NET Core."
keywords: "CLI, расширяемость, пользовательские команды, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
ms.workload: dotnetcore
ms.openlocfilehash: a064ae72a077583cfb544309700555ebd9d398a6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="b9d50-104">Управление зависимостями с помощью пакета SDK для .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b9d50-104">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="b9d50-105">Помимо переноса проектов .NET Core из файла project.json в CSPROJ-файл и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, обеспечивающих отслеживание зависимостей.</span><span class="sxs-lookup"><span data-stu-id="b9d50-105">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="b9d50-106">Для проектов .NET Core это аналогично тому, что раньше выполнял файл project.json.</span><span class="sxs-lookup"><span data-stu-id="b9d50-106">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="b9d50-107">Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet.</span><span class="sxs-lookup"><span data-stu-id="b9d50-107">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="b9d50-108">Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="b9d50-108">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="b9d50-109">В этом документе описывается новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="b9d50-109">This document describes the new reference type.</span></span> <span data-ttu-id="b9d50-110">Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="b9d50-110">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="b9d50-111">Новый элемент \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="b9d50-111">The new \<PackageReference> element</span></span>
<span data-ttu-id="b9d50-112">Элемент `<PackageReference>` имеет следующую базовую структуру:</span><span class="sxs-lookup"><span data-stu-id="b9d50-112">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="b9d50-113">Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="b9d50-113">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="b9d50-114">Ключевым является оператор `Include`, указывающий идентификатор пакета, который нужно добавить в проект.</span><span class="sxs-lookup"><span data-stu-id="b9d50-114">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="b9d50-115">Дочерний элемент `<Version>` указывает версию, которую необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="b9d50-115">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="b9d50-116">Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="b9d50-116">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="b9d50-117">Если вы не знакомы с общими понятиями синтаксиса `csproj`, используйте [справочную документацию по проекту MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) для ознакомления с ними.</span><span class="sxs-lookup"><span data-stu-id="b9d50-117">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="b9d50-118">Добавление зависимости, которая доступна только в конкретном целевом объекте, выполняется с использованием условий, аналогичных в приведенном далее примере.</span><span class="sxs-lookup"><span data-stu-id="b9d50-118">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

<span data-ttu-id="b9d50-119">Указанное выше означает, что зависимость будет действительной только в том случае, если для затронутого целевого объекта выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="b9d50-119">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="b9d50-120">Элемент `$(TargetFramework)` в этом условии представляет собой заданное в проекте свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="b9d50-120">The `$(TargetFramework)` in the condition is a MSBuild property that is being set in the project.</span></span> <span data-ttu-id="b9d50-121">Для наиболее распространенных приложений .NET Core это не требуется.</span><span class="sxs-lookup"><span data-stu-id="b9d50-121">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="b9d50-122">Добавление зависимости в проект</span><span class="sxs-lookup"><span data-stu-id="b9d50-122">Adding a dependency to your project</span></span>
<span data-ttu-id="b9d50-123">Добавить зависимость в проект очень просто.</span><span class="sxs-lookup"><span data-stu-id="b9d50-123">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="b9d50-124">Ниже показано, как добавить в проект Json.NET версии `9.0.1`.</span><span class="sxs-lookup"><span data-stu-id="b9d50-124">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="b9d50-125">Это применимо и к любой другой зависимости NuGet.</span><span class="sxs-lookup"><span data-stu-id="b9d50-125">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="b9d50-126">При открытии файла проекта вы увидите не менее двух узлов `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="b9d50-126">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="b9d50-127">Можно заметить, что на одном из узлов уже есть элементы `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="b9d50-127">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="b9d50-128">Вы можете добавить новую зависимость на этот узел или создать новый — поступайте по своему усмотрению, так как результат от этого не изменится.</span><span class="sxs-lookup"><span data-stu-id="b9d50-128">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="b9d50-129">В этом примере мы будем использовать шаблон по умолчанию, добавленный `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="b9d50-129">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="b9d50-130">Это простое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="b9d50-130">This is a simple console application.</span></span> <span data-ttu-id="b9d50-131">При открытии проекта мы сначала видим узел `<ItemGroup>` и существующий на нем элемент `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="b9d50-131">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="b9d50-132">Затем мы добавляем к нему следующее:</span><span class="sxs-lookup"><span data-stu-id="b9d50-132">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
<span data-ttu-id="b9d50-133">После этого мы сохраняем проект и выполняем команду `dotnet restore` для установки зависимости.</span><span class="sxs-lookup"><span data-stu-id="b9d50-133">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="b9d50-134">Весь проект выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b9d50-134">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="b9d50-135">Удаление зависимости из проекта</span><span class="sxs-lookup"><span data-stu-id="b9d50-135">Removing a dependency from the project</span></span>
<span data-ttu-id="b9d50-136">Чтобы удалить зависимость из файла проекта, достаточно просто удалить `<PackageReference>` из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="b9d50-136">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
