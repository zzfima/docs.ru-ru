---
title: Организация проекта для поддержки .NET Framework и .NET Core
description: Эта статья поможет владельцам проектов, которые хотят скомпилировать свое решение одновременно для .NET Framework и .NET Core.
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.openlocfilehash: f8ca0d08c9e3802c71d53c831592ee4388ab5512
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512270"
---
# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a><span data-ttu-id="35522-103">Организация проекта для поддержки .NET Framework и .NET Core</span><span class="sxs-lookup"><span data-stu-id="35522-103">Organizing your project to support .NET Framework and .NET Core</span></span>

<span data-ttu-id="35522-104">Эта статья поможет владельцам проектов, которые хотят скомпилировать свое решение одновременно для .NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="35522-104">This article helps project owners who want to compile their solution against .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="35522-105">В ней описываются несколько вариантов организации проектов, которые могут помочь разработчикам достичь этой цели.</span><span class="sxs-lookup"><span data-stu-id="35522-105">It provides several options to organize projects to help developers achieve this goal.</span></span> <span data-ttu-id="35522-106">Следующий список содержит несколько типичных сценариев, которые следует принимать во внимание при выборе макета проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="35522-106">The following list provides some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="35522-107">Этот список может охватывать не все необходимые случаи. Устанавливайте приоритеты в зависимости от потребностей вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="35522-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="35522-108">[**Объединение существующих проектов и проектов .NET Core в единые проекты**][option-csproj]</span><span class="sxs-lookup"><span data-stu-id="35522-108">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="35522-109">*Преимущества*</span><span class="sxs-lookup"><span data-stu-id="35522-109">*What this is good for:*</span></span>
  * <span data-ttu-id="35522-110">Упрощение процесса сборки благодаря компиляции одного, а не нескольких проектов, каждый из которых предназначен для отдельной версии .NET Framework или платформы.</span><span class="sxs-lookup"><span data-stu-id="35522-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="35522-111">Упрощение управления файлами исходного кода для проектов, предназначенных для различных платформ, благодаря тому, что вам приходится управлять только одним файлом проекта.</span><span class="sxs-lookup"><span data-stu-id="35522-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="35522-112">При использовании альтернативных подходов добавление и удаление файлов исходного кода требует синхронизации этих изменений с другими проектами вручную.</span><span class="sxs-lookup"><span data-stu-id="35522-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="35522-113">Простое создание пакета NuGet для использования.</span><span class="sxs-lookup"><span data-stu-id="35522-113">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="35522-114">Позволяет писать код для конкретной версии .NET Framework в библиотеках посредством директив компилятора.</span><span class="sxs-lookup"><span data-stu-id="35522-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="35522-115">*Неподдерживаемые сценарии*</span><span class="sxs-lookup"><span data-stu-id="35522-115">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="35522-116">Для открытия существующих проектов разработчики должны использовать Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="35522-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="35522-117">Для поддержки предыдущих версий Visual Studio лучше [хранить файлы проектов в разных папках](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="35522-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="35522-118">[**Разделение существующих и новых проектов .NET Core**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="35522-118">[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="35522-119">*Преимущества*</span><span class="sxs-lookup"><span data-stu-id="35522-119">*What this is good for:*</span></span>
  * <span data-ttu-id="35522-120">Продолжение работы над существующими проектами для разработчиков и участников, у которых нет Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="35522-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="35522-121">Снижение вероятности появления новых ошибок в существующих проектах, так как не требуется обработка кода.</span><span class="sxs-lookup"><span data-stu-id="35522-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="35522-122">Пример</span><span class="sxs-lookup"><span data-stu-id="35522-122">Example</span></span>

<span data-ttu-id="35522-123">Рассмотрим показанный ниже репозиторий.</span><span class="sxs-lookup"><span data-stu-id="35522-123">Consider the repository below:</span></span>

<span data-ttu-id="35522-124">![Существующий проект][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="35522-124">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="35522-125">[**Исходный код**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="35522-125">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="35522-126">В зависимости от ограничений и сложности существующих проектов добавить поддержку .NET Core для этого репозитория можно несколькими способами, которые описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="35522-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="35522-127">Замена существующих проектов на проект .NET Core, предназначенный для нескольких платформ</span><span class="sxs-lookup"><span data-stu-id="35522-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="35522-128">Измените файлы в репозитории, удалив все существующие файлы *\*.csproj* и создав единственный файл *\*.csproj*, предназначенный для нескольких платформ.</span><span class="sxs-lookup"><span data-stu-id="35522-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="35522-129">Это удобно по той причине, что один проект можно компилировать для разных платформ.</span><span class="sxs-lookup"><span data-stu-id="35522-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="35522-130">Это также позволяет управлять различными параметрами компиляции и зависимостями для каждой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="35522-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="35522-131">![Создание файла CSPROJ, предназначенного для нескольких платформ][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="35522-131">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="35522-132">[**Исходный код**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="35522-132">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="35522-133">Обратите внимание на следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="35522-133">Changes to note are:</span></span>

* <span data-ttu-id="35522-134">Замена файлов *packages.config* и *\*.csproj* на новый файл [.NET Core*\*.csproj*][example-csproj-netcore].</span><span class="sxs-lookup"><span data-stu-id="35522-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="35522-135">Пакеты NuGet указываются с помощью `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="35522-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="35522-136">Сохранение существующих проектов и создание проекта .NET Core</span><span class="sxs-lookup"><span data-stu-id="35522-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="35522-137">При наличии существующих проектов, предназначенных для более старых платформ, можно оставить эти проекты без изменения и использовать проект .NET Core для новых платформ.</span><span class="sxs-lookup"><span data-stu-id="35522-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="35522-138">![Проект .NET Core с существующим проектом в другой папке][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="35522-138">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="35522-139">[**Исходный код**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="35522-139">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="35522-140">Обратите внимание на следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="35522-140">Changes to note are:</span></span>

* <span data-ttu-id="35522-141">Проект .NET Core и существующие проекты хранятся в разных папках.</span><span class="sxs-lookup"><span data-stu-id="35522-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  * <span data-ttu-id="35522-142">Размещение проектов в разных папках позволяет обойтись без Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="35522-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="35522-143">Вы можете создать отдельное решение, которое открывает только старые проекты.</span><span class="sxs-lookup"><span data-stu-id="35522-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="35522-144">См. также</span><span class="sxs-lookup"><span data-stu-id="35522-144">See Also</span></span>

* <span data-ttu-id="35522-145">Дополнительные указания по переходу на .NET Core [документации по переходу на .NET Core][porting-doc].</span><span class="sxs-lookup"><span data-stu-id="35522-145">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Существующий проект"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Создание файла CSPROJ, предназначенного для нескольких платформ"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "Проект .NET Core с существующей библиотекой PCL в другой папке"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
