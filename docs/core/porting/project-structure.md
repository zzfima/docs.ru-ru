---
title: "Организация проекта для поддержки .NET Framework и .NET Core"
description: "Эта статья поможет владельцам проектов, которые хотят скомпилировать свое решение одновременно для .NET Framework и .NET Core."
keywords: ".NET, .NET Core, .NET Framework, макет проекта, поддержка нескольких платформ"
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
ms.workload: dotnetcore
ms.openlocfilehash: 08fe18233c13410f0fb970020bce090d3345ca84
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a><span data-ttu-id="d4afb-104">Организация проекта для поддержки .NET Framework и .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4afb-104">Organizing your project to support .NET Framework and .NET Core</span></span>

<span data-ttu-id="d4afb-105">Эта статья поможет владельцам проектов, которые хотят скомпилировать свое решение одновременно для .NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d4afb-105">This article helps project owners who want to compile their solution against .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="d4afb-106">В ней описываются несколько вариантов организации проектов, которые могут помочь разработчикам достичь этой цели.</span><span class="sxs-lookup"><span data-stu-id="d4afb-106">It provides several options to organize projects to help developers achieve this goal.</span></span> <span data-ttu-id="d4afb-107">Следующий список содержит несколько типичных сценариев, которые следует принимать во внимание при выборе макета проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d4afb-107">The following list provides some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="d4afb-108">Этот список может охватывать не все необходимые случаи. Устанавливайте приоритеты в зависимости от потребностей вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="d4afb-108">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="d4afb-109">[**Объединение существующих проектов и проектов .NET Core в единые проекты**][option-csproj]</span><span class="sxs-lookup"><span data-stu-id="d4afb-109">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="d4afb-110">*Преимущества*</span><span class="sxs-lookup"><span data-stu-id="d4afb-110">*What this is good for:*</span></span>
  * <span data-ttu-id="d4afb-111">Упрощение процесса сборки благодаря компиляции одного, а не нескольких проектов, каждый из которых предназначен для отдельной версии .NET Framework или платформы.</span><span class="sxs-lookup"><span data-stu-id="d4afb-111">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="d4afb-112">Упрощение управления файлами исходного кода для проектов, предназначенных для различных платформ, благодаря тому, что вам приходится управлять только одним файлом проекта.</span><span class="sxs-lookup"><span data-stu-id="d4afb-112">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="d4afb-113">При использовании альтернативных подходов добавление и удаление файлов исходного кода требует синхронизации этих изменений с другими проектами вручную.</span><span class="sxs-lookup"><span data-stu-id="d4afb-113">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="d4afb-114">Простое создание пакета NuGet для использования.</span><span class="sxs-lookup"><span data-stu-id="d4afb-114">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="d4afb-115">Позволяет писать код для конкретной версии .NET Framework в библиотеках посредством директив компилятора.</span><span class="sxs-lookup"><span data-stu-id="d4afb-115">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="d4afb-116">*Неподдерживаемые сценарии*</span><span class="sxs-lookup"><span data-stu-id="d4afb-116">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="d4afb-117">Для открытия существующих проектов разработчики должны использовать Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d4afb-117">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="d4afb-118">Для поддержки предыдущих версий Visual Studio лучше [хранить файлы проектов в разных папках](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="d4afb-118">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="d4afb-119">[**Разделение существующих и новых проектов .NET Core**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="d4afb-119">[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="d4afb-120">*Преимущества*</span><span class="sxs-lookup"><span data-stu-id="d4afb-120">*What this is good for:*</span></span>
  * <span data-ttu-id="d4afb-121">Продолжение работы над существующими проектами для разработчиков и участников, у которых нет Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d4afb-121">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="d4afb-122">Снижение вероятности появления новых ошибок в существующих проектах, так как не требуется обработка кода.</span><span class="sxs-lookup"><span data-stu-id="d4afb-122">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="d4afb-123">Пример</span><span class="sxs-lookup"><span data-stu-id="d4afb-123">Example</span></span>

<span data-ttu-id="d4afb-124">Рассмотрим показанный ниже репозиторий.</span><span class="sxs-lookup"><span data-stu-id="d4afb-124">Consider the repository below:</span></span>

<span data-ttu-id="d4afb-125">![Существующий проект][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="d4afb-125">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="d4afb-126">[**Исходный код**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="d4afb-126">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="d4afb-127">В зависимости от ограничений и сложности существующих проектов добавить поддержку .NET Core для этого репозитория можно несколькими способами, которые описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="d4afb-127">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="d4afb-128">Замена существующих проектов на проект .NET Core, предназначенный для нескольких платформ</span><span class="sxs-lookup"><span data-stu-id="d4afb-128">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="d4afb-129">Измените файлы в репозитории, удалив все существующие файлы *\*.csproj* и создав единственный файл *\*.csproj*, предназначенный для нескольких платформ.</span><span class="sxs-lookup"><span data-stu-id="d4afb-129">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="d4afb-130">Это удобно по той причине, что один проект можно компилировать для разных платформ.</span><span class="sxs-lookup"><span data-stu-id="d4afb-130">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="d4afb-131">Это также позволяет управлять различными параметрами компиляции и зависимостями для каждой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="d4afb-131">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="d4afb-132">![Создание файла CSPROJ, предназначенного для нескольких платформ][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="d4afb-132">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="d4afb-133">[**Исходный код**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="d4afb-133">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="d4afb-134">Обратите внимание на следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="d4afb-134">Changes to note are:</span></span>
* <span data-ttu-id="d4afb-135">Замена файлов *packages.config* и *\*.csproj* на новый файл [.NET Core*\*.csproj*][example-csproj-netcore].</span><span class="sxs-lookup"><span data-stu-id="d4afb-135">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="d4afb-136">Пакеты NuGet указываются с помощью `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="d4afb-136">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="d4afb-137">Сохранение существующих проектов и создание проекта .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4afb-137">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="d4afb-138">При наличии существующих проектов, предназначенных для более старых платформ, можно оставить эти проекты без изменения и использовать проект .NET Core для новых платформ.</span><span class="sxs-lookup"><span data-stu-id="d4afb-138">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="d4afb-139">![Проект .NET Core с существующим проектом в другой папке][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="d4afb-139">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="d4afb-140">[**Исходный код**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="d4afb-140">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="d4afb-141">Обратите внимание на следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="d4afb-141">Changes to note are:</span></span>
* <span data-ttu-id="d4afb-142">Проект .NET Core и существующие проекты хранятся в разных папках.</span><span class="sxs-lookup"><span data-stu-id="d4afb-142">The .NET Core and existing projects are kept in separate folders.</span></span>
    * <span data-ttu-id="d4afb-143">Размещение проектов в разных папках позволяет обойтись без Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d4afb-143">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="d4afb-144">Вы можете создать отдельное решение, которое открывает только старые проекты.</span><span class="sxs-lookup"><span data-stu-id="d4afb-144">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4afb-145">См. также</span><span class="sxs-lookup"><span data-stu-id="d4afb-145">See Also</span></span>

<span data-ttu-id="d4afb-146">Дополнительные указания по переходу на .NET Core [документации по переходу на .NET Core][porting-doc].</span><span class="sxs-lookup"><span data-stu-id="d4afb-146">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Существующий проект"
[example-initial-project-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Создание файла CSPROJ, предназначенного для нескольких платформ"
[example-csproj-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "Проект .NET Core с существующей библиотекой PCL в другой папке"
[example-csproj-different-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
