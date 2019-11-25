---
title: Организация проектов для .NET Framework и .NET Core
description: Эта статья поможет владельцам проектов, которые хотят скомпилировать свое решение одновременно для .NET Framework и .NET Core.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 701aa64be8d6c712ef635411ad6c226a3c3ab8ed
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522980"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="68b50-103">Организация проекта для параллельной поддержки .NET Framework и .NET Core</span><span class="sxs-lookup"><span data-stu-id="68b50-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="68b50-104">Узнайте, как создать решение, которое выполняет параллельную сборку для .NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68b50-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="68b50-105">Изучите несколько вариантов организации проектов, которые могут помочь вам достичь этой цели.</span><span class="sxs-lookup"><span data-stu-id="68b50-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="68b50-106">Ниже приводится несколько типичных сценариев, которые следует принять во внимание при выборе способа компоновки проекта с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68b50-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="68b50-107">Этот список может охватывать не все необходимые случаи. Устанавливайте приоритеты в зависимости от потребностей вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="68b50-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

- [<span data-ttu-id="68b50-108">**Объединение существующих проектов и проектов .NET Core в единые проекты**</span><span class="sxs-lookup"><span data-stu-id="68b50-108">**Combine existing projects and .NET Core projects into single projects**</span></span>](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  <span data-ttu-id="68b50-109">*Преимущества*</span><span class="sxs-lookup"><span data-stu-id="68b50-109">*What this is good for:*</span></span>
  - <span data-ttu-id="68b50-110">Упрощение процесса сборки благодаря компиляции одного, а не нескольких проектов, каждый из которых предназначен для отдельной версии .NET Framework или платформы.</span><span class="sxs-lookup"><span data-stu-id="68b50-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  - <span data-ttu-id="68b50-111">Упрощение управления файлами исходного кода для проектов, предназначенных для различных платформ, благодаря тому, что вам приходится управлять только одним файлом проекта.</span><span class="sxs-lookup"><span data-stu-id="68b50-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="68b50-112">При использовании альтернативных подходов добавление и удаление файлов исходного кода требует синхронизации этих изменений с другими проектами вручную.</span><span class="sxs-lookup"><span data-stu-id="68b50-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  - <span data-ttu-id="68b50-113">Простое создание пакета NuGet для использования.</span><span class="sxs-lookup"><span data-stu-id="68b50-113">Easily generating a NuGet package for consumption.</span></span>
  - <span data-ttu-id="68b50-114">Позволяет писать код для конкретной версии .NET Framework в библиотеках посредством директив компилятора.</span><span class="sxs-lookup"><span data-stu-id="68b50-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="68b50-115">*Неподдерживаемые сценарии*</span><span class="sxs-lookup"><span data-stu-id="68b50-115">*Unsupported scenarios:*</span></span>
  - <span data-ttu-id="68b50-116">Для открытия существующих проектов разработчики должны использовать Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="68b50-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="68b50-117">Для поддержки предыдущих версий Visual Studio лучше [хранить файлы проектов в разных папках](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="68b50-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

- <a name="support-vs"></a><span data-ttu-id="68b50-118">[**Разделение существующих и новых проектов .NET Core**](#keep-existing-projects-and-create-a-net-core-project)</span><span class="sxs-lookup"><span data-stu-id="68b50-118">[**Keep existing projects and new .NET Core projects separate**](#keep-existing-projects-and-create-a-net-core-project)</span></span>

  <span data-ttu-id="68b50-119">*Преимущества*</span><span class="sxs-lookup"><span data-stu-id="68b50-119">*What this is good for:*</span></span>
  - <span data-ttu-id="68b50-120">Продолжение работы над существующими проектами для разработчиков и участников, у которых нет Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="68b50-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  - <span data-ttu-id="68b50-121">Снижение вероятности появления новых ошибок в существующих проектах, так как не требуется обработка кода.</span><span class="sxs-lookup"><span data-stu-id="68b50-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="68b50-122">Пример</span><span class="sxs-lookup"><span data-stu-id="68b50-122">Example</span></span>

<span data-ttu-id="68b50-123">Рассмотрим показанный ниже репозиторий.</span><span class="sxs-lookup"><span data-stu-id="68b50-123">Consider the repository below:</span></span>

![Существующий проект](./media/project-structure/existing-project-structure.png)

[<span data-ttu-id="68b50-125">**Исходный код**</span><span class="sxs-lookup"><span data-stu-id="68b50-125">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

<span data-ttu-id="68b50-126">В зависимости от ограничений и сложности существующих проектов добавить поддержку .NET Core для этого репозитория можно несколькими способами, которые описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="68b50-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="68b50-127">Замена существующих проектов на проект .NET Core, предназначенный для нескольких платформ</span><span class="sxs-lookup"><span data-stu-id="68b50-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="68b50-128">Измените файлы в репозитории, удалив все существующие файлы *\*.csproj* и создав единственный файл *\*.csproj*, предназначенный для нескольких платформ.</span><span class="sxs-lookup"><span data-stu-id="68b50-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="68b50-129">Это удобно по той причине, что один проект можно компилировать для разных платформ.</span><span class="sxs-lookup"><span data-stu-id="68b50-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="68b50-130">Это также позволяет управлять различными параметрами компиляции и зависимостями для каждой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="68b50-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

![Создание файла CSPROJ, предназначенного для нескольких платформ](./media/project-structure/multi-targeted-project.png)

[<span data-ttu-id="68b50-132">**Исходный код**</span><span class="sxs-lookup"><span data-stu-id="68b50-132">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

<span data-ttu-id="68b50-133">Обратите внимание на следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="68b50-133">Changes to note are:</span></span>

- <span data-ttu-id="68b50-134">Замена файлов *packages.config* и *\*.csproj* на новый файл [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span><span class="sxs-lookup"><span data-stu-id="68b50-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span></span> <span data-ttu-id="68b50-135">Пакеты NuGet указываются с помощью `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="68b50-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="68b50-136">Сохранение существующих проектов и создание проекта .NET Core</span><span class="sxs-lookup"><span data-stu-id="68b50-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="68b50-137">При наличии существующих проектов, предназначенных для более старых платформ, можно оставить эти проекты без изменения и использовать проект .NET Core для новых платформ.</span><span class="sxs-lookup"><span data-stu-id="68b50-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

![Проект .NET Core с существующим проектом в другой папке](./media/project-structure/separate-projects-same-source.png)

[<span data-ttu-id="68b50-139">**Исходный код**</span><span class="sxs-lookup"><span data-stu-id="68b50-139">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

<span data-ttu-id="68b50-140">Обратите внимание на следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="68b50-140">Changes to note are:</span></span>

- <span data-ttu-id="68b50-141">Проект .NET Core и существующие проекты хранятся в разных папках.</span><span class="sxs-lookup"><span data-stu-id="68b50-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  - <span data-ttu-id="68b50-142">Размещение проектов в разных папках позволяет обойтись без Visual Studio 2017 или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="68b50-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017 or later versions.</span></span> <span data-ttu-id="68b50-143">Вы можете создать отдельное решение, которое открывает только старые проекты.</span><span class="sxs-lookup"><span data-stu-id="68b50-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="68b50-144">См. также</span><span class="sxs-lookup"><span data-stu-id="68b50-144">See also</span></span>

- [<span data-ttu-id="68b50-145">Документация по переносу .NET Core</span><span class="sxs-lookup"><span data-stu-id="68b50-145">.NET Core porting documentation</span></span>](index.md)
