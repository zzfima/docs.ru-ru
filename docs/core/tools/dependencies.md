---
title: Управление зависимостями в средствах .NET Core
description: Сведения об управлении зависимостями с помощью средств .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: e14fa42534d807e2a0fcce1dabe747c18c5166b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733373"
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="72c74-103">Управление зависимостями с помощью пакета SDK для .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72c74-103">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="72c74-104">Помимо переноса проектов .NET Core из файла project.json в CSPROJ-файл и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, обеспечивающих отслеживание зависимостей.</span><span class="sxs-lookup"><span data-stu-id="72c74-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="72c74-105">Для проектов .NET Core это аналогично тому, что раньше выполнял файл project.json.</span><span class="sxs-lookup"><span data-stu-id="72c74-105">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="72c74-106">Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet.</span><span class="sxs-lookup"><span data-stu-id="72c74-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="72c74-107">Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="72c74-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="72c74-108">В этом документе описывается новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="72c74-108">This document describes the new reference type.</span></span> <span data-ttu-id="72c74-109">Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="72c74-109">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="72c74-110">Новый элемент \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="72c74-110">The new \<PackageReference> element</span></span>
<span data-ttu-id="72c74-111">Элемент `<PackageReference>` имеет следующую базовую структуру:</span><span class="sxs-lookup"><span data-stu-id="72c74-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="72c74-112">Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="72c74-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="72c74-113">Ключевым является оператор `Include`, указывающий идентификатор пакета, который нужно добавить в проект.</span><span class="sxs-lookup"><span data-stu-id="72c74-113">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="72c74-114">Дочерний элемент `<Version>` указывает версию, которую необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="72c74-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="72c74-115">Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="72c74-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="72c74-116">Если вы не знакомы с общими понятиями синтаксиса `csproj`, используйте [справочную документацию по проекту MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) для ознакомления с ними.</span><span class="sxs-lookup"><span data-stu-id="72c74-116">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="72c74-117">Добавление зависимости, которая доступна только в конкретном целевом объекте, выполняется с использованием условий, аналогичных в приведенном далее примере.</span><span class="sxs-lookup"><span data-stu-id="72c74-117">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="72c74-118">Указанное выше означает, что зависимость будет действительной только в том случае, если для затронутого целевого объекта выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="72c74-118">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="72c74-119">Элемент `$(TargetFramework)` в этом условии представляет собой заданное в проекте свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="72c74-119">The `$(TargetFramework)` in the condition is an MSBuild property that is being set in the project.</span></span> <span data-ttu-id="72c74-120">Для наиболее распространенных приложений .NET Core это не требуется.</span><span class="sxs-lookup"><span data-stu-id="72c74-120">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="72c74-121">Добавление зависимости в проект</span><span class="sxs-lookup"><span data-stu-id="72c74-121">Adding a dependency to your project</span></span>
<span data-ttu-id="72c74-122">Добавить зависимость в проект очень просто.</span><span class="sxs-lookup"><span data-stu-id="72c74-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="72c74-123">Ниже показано, как добавить в проект Json.NET версии `9.0.1`.</span><span class="sxs-lookup"><span data-stu-id="72c74-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="72c74-124">Это применимо и к любой другой зависимости NuGet.</span><span class="sxs-lookup"><span data-stu-id="72c74-124">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="72c74-125">При открытии файла проекта вы увидите не менее двух узлов `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="72c74-125">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="72c74-126">Можно заметить, что на одном из узлов уже есть элементы `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="72c74-126">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="72c74-127">Вы можете добавить новую зависимость на этот узел или создать новый — поступайте по своему усмотрению, так как результат от этого не изменится.</span><span class="sxs-lookup"><span data-stu-id="72c74-127">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="72c74-128">В этом примере мы будем использовать шаблон по умолчанию, добавленный `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="72c74-128">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="72c74-129">Это простое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="72c74-129">This is a simple console application.</span></span> <span data-ttu-id="72c74-130">При открытии проекта мы сначала видим узел `<ItemGroup>` и существующий на нем элемент `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="72c74-130">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="72c74-131">Затем мы добавляем к нему следующее:</span><span class="sxs-lookup"><span data-stu-id="72c74-131">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="72c74-132">После этого мы сохраняем проект и выполняем команду `dotnet restore` для установки зависимости.</span><span class="sxs-lookup"><span data-stu-id="72c74-132">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="72c74-133">Весь проект выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="72c74-133">The full project looks like this:</span></span>

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

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="72c74-134">Удаление зависимости из проекта</span><span class="sxs-lookup"><span data-stu-id="72c74-134">Removing a dependency from the project</span></span>
<span data-ttu-id="72c74-135">Чтобы удалить зависимость из файла проекта, достаточно просто удалить `<PackageReference>` из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="72c74-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
