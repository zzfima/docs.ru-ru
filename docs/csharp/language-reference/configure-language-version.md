---
title: Управление версиями языка C# — руководство по C#
description: Дополнительные сведения о том, как версия языка C# определяется на основе вашего проекта и какие значения можно настроить вручную.
ms.date: 07/10/2019
ms.openlocfilehash: e35fdf2bcdb1a31b752c760f3f6df59232e498a4
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236094"
---
# <a name="c-language-versioning"></a><span data-ttu-id="720ea-103">Управление версиями языка C#</span><span class="sxs-lookup"><span data-stu-id="720ea-103">C# language versioning</span></span>

<span data-ttu-id="720ea-104">Компилятор C# определяет версию языка по умолчанию на основе целевой платформы или платформ проекта.</span><span class="sxs-lookup"><span data-stu-id="720ea-104">The C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="720ea-105">Это обусловлено тем, что язык C# может иметь функции, которые зависят от типов или компонентов среды выполнения и не доступны в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="720ea-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="720ea-106">Это также гарантирует, что для любой целевой платформы, для которой выполняется сборка проекта, вы получаете последнюю совместимую версию языка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="720ea-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

## <a name="defaults"></a><span data-ttu-id="720ea-107">расписания</span><span class="sxs-lookup"><span data-stu-id="720ea-107">Defaults</span></span>

<span data-ttu-id="720ea-108">Компилятор определяет значение по умолчанию на основе следующих правил:</span><span class="sxs-lookup"><span data-stu-id="720ea-108">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="720ea-109">Целевая платформа</span><span class="sxs-lookup"><span data-stu-id="720ea-109">Target framework</span></span>|<span data-ttu-id="720ea-110">version</span><span class="sxs-lookup"><span data-stu-id="720ea-110">version</span></span>|<span data-ttu-id="720ea-111">Версия языка C# по умолчанию</span><span class="sxs-lookup"><span data-stu-id="720ea-111">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="720ea-112">.NET Core</span><span class="sxs-lookup"><span data-stu-id="720ea-112">.NET Core</span></span>|<span data-ttu-id="720ea-113">3.x</span><span class="sxs-lookup"><span data-stu-id="720ea-113">3.x</span></span>|<span data-ttu-id="720ea-114">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="720ea-114">C# 8.0</span></span>|
|<span data-ttu-id="720ea-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="720ea-115">.NET Core</span></span>|<span data-ttu-id="720ea-116">2.x</span><span class="sxs-lookup"><span data-stu-id="720ea-116">2.x</span></span>|<span data-ttu-id="720ea-117">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="720ea-117">C# 7.3</span></span>|
|<span data-ttu-id="720ea-118">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="720ea-118">.NET Standard</span></span>|<span data-ttu-id="720ea-119">все</span><span class="sxs-lookup"><span data-stu-id="720ea-119">all</span></span>|<span data-ttu-id="720ea-120">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="720ea-120">C# 7.3</span></span>|
|<span data-ttu-id="720ea-121">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="720ea-121">.NET Framework</span></span>|<span data-ttu-id="720ea-122">все</span><span class="sxs-lookup"><span data-stu-id="720ea-122">all</span></span>|<span data-ttu-id="720ea-123">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="720ea-123">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="720ea-124">Параметры по умолчанию для предварительных версий</span><span class="sxs-lookup"><span data-stu-id="720ea-124">Default for previews</span></span>

<span data-ttu-id="720ea-125">Если проект предназначен для платформы в предварительной версии с поддержкой соответствующего языка в предварительной версии, будет использоваться язык, поддерживаемый в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-125">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="720ea-126">Это гарантирует, что вы можете использовать новейшие возможности, которые точно будут работать с этой предварительной версией в любой среде, не затрагивая проекты, предназначенные для выпущенной версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="720ea-126">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="overriding-a-default"></a><span data-ttu-id="720ea-127">Переопределение значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="720ea-127">Overriding a default</span></span>

<span data-ttu-id="720ea-128">Если необходимо явно указать версию C#, это можно сделать несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="720ea-128">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="720ea-129">Вручную изменить [файл проекта](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="720ea-129">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="720ea-130">задание языковой версии [для нескольких проектов в подкаталоге](#configure-multiple-projects);</span><span class="sxs-lookup"><span data-stu-id="720ea-130">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="720ea-131">настройка [параметра компилятора `-langversion`](compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="720ea-131">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="720ea-132">Изменение файла проекта</span><span class="sxs-lookup"><span data-stu-id="720ea-132">Edit the project file</span></span>

<span data-ttu-id="720ea-133">Версию языка можно задать в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="720ea-133">You can set the language version in your project file.</span></span> <span data-ttu-id="720ea-134">Например, если доступ к предварительной версии функций должен быть задан явным образом, можно добавить следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="720ea-134">For example, if you explicitly wanted access to preview features, you could do add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="720ea-135">Значение `preview` использует последнюю предварительную версию языка C#, которую поддерживает компилятор.</span><span class="sxs-lookup"><span data-stu-id="720ea-135">The value `preview` uses the latest available preview C# language that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="720ea-136">Настройка нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="720ea-136">Configure multiple projects</span></span>

<span data-ttu-id="720ea-137">Можно создать файл **Directory.Build.props**, содержащий элемент `<LangVersion>`, чтобы настроить несколько каталогов.</span><span class="sxs-lookup"><span data-stu-id="720ea-137">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="720ea-138">Обычно это делается в каталоге решения.</span><span class="sxs-lookup"><span data-stu-id="720ea-138">You typically do that in your solution directory.</span></span> <span data-ttu-id="720ea-139">Добавьте следующий код в файл **Directory.Build.props** в каталоге решения:</span><span class="sxs-lookup"><span data-stu-id="720ea-139">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="720ea-140">Теперь сборки в каждом подкаталоге каталога, который содержит этот файл, будут использовать предварительную версию C#.</span><span class="sxs-lookup"><span data-stu-id="720ea-140">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="720ea-141">Дополнительные сведения см. в статье о [настройке сборки](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="720ea-141">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="720ea-142">Справочник по версиям языка C#</span><span class="sxs-lookup"><span data-stu-id="720ea-142">C# language version reference</span></span>

<span data-ttu-id="720ea-143">В следующей таблице показаны все текущие версии языка C#.</span><span class="sxs-lookup"><span data-stu-id="720ea-143">The following table shows all current C# language versions.</span></span> <span data-ttu-id="720ea-144">Ваш компилятор может не распознавать все значения, если имеет более раннюю версию.</span><span class="sxs-lookup"><span data-stu-id="720ea-144">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="720ea-145">Если вы установите .NET Core 3.0, вы получите доступ ко всем значениям в таблице.</span><span class="sxs-lookup"><span data-stu-id="720ea-145">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="720ea-146">Значение</span><span class="sxs-lookup"><span data-stu-id="720ea-146">Value</span></span>|<span data-ttu-id="720ea-147">Значение</span><span class="sxs-lookup"><span data-stu-id="720ea-147">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="720ea-148">preview</span><span class="sxs-lookup"><span data-stu-id="720ea-148">preview</span></span>|<span data-ttu-id="720ea-149">Компилятор допускает использование любого допустимого синтаксиса языка из последней предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-149">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="720ea-150">latest</span><span class="sxs-lookup"><span data-stu-id="720ea-150">latest</span></span>|<span data-ttu-id="720ea-151">Компилятор принимает синтаксис из последней выпущенной версии компилятора (включая дополнительный номер версии).</span><span class="sxs-lookup"><span data-stu-id="720ea-151">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="720ea-152">latestMajor</span><span class="sxs-lookup"><span data-stu-id="720ea-152">latestMajor</span></span>|<span data-ttu-id="720ea-153">Компилятор принимает синтаксис из последней основной версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="720ea-153">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="720ea-154">8.0</span><span class="sxs-lookup"><span data-stu-id="720ea-154">8.0</span></span>|<span data-ttu-id="720ea-155">Компилятор принимает только синтаксис, включенный в спецификацию C# 8.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-155">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="720ea-156">7.3</span><span class="sxs-lookup"><span data-stu-id="720ea-156">7.3</span></span>|<span data-ttu-id="720ea-157">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.3 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-157">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="720ea-158">7.2</span><span class="sxs-lookup"><span data-stu-id="720ea-158">7.2</span></span>|<span data-ttu-id="720ea-159">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.2 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-159">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="720ea-160">7.1</span><span class="sxs-lookup"><span data-stu-id="720ea-160">7.1</span></span>|<span data-ttu-id="720ea-161">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.1 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-161">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="720ea-162">7</span><span class="sxs-lookup"><span data-stu-id="720ea-162">7</span></span>|<span data-ttu-id="720ea-163">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-163">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="720ea-164">6</span><span class="sxs-lookup"><span data-stu-id="720ea-164">6</span></span>|<span data-ttu-id="720ea-165">Компилятор принимает только синтаксис, включенный в спецификацию C# 6.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-165">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="720ea-166">5</span><span class="sxs-lookup"><span data-stu-id="720ea-166">5</span></span>|<span data-ttu-id="720ea-167">Компилятор принимает только синтаксис, включенный в спецификацию C# 5.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-167">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="720ea-168">4</span><span class="sxs-lookup"><span data-stu-id="720ea-168">4</span></span>|<span data-ttu-id="720ea-169">Компилятор принимает только синтаксис, включенный в спецификацию C# 4.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-169">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="720ea-170">3</span><span class="sxs-lookup"><span data-stu-id="720ea-170">3</span></span>|<span data-ttu-id="720ea-171">Компилятор принимает только синтаксис, включенный в спецификацию C# 3.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="720ea-171">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="720ea-172">ISO-2</span><span class="sxs-lookup"><span data-stu-id="720ea-172">ISO-2</span></span>|<span data-ttu-id="720ea-173">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="720ea-173">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="720ea-174">ISO-1</span><span class="sxs-lookup"><span data-stu-id="720ea-174">ISO-1</span></span>|<span data-ttu-id="720ea-175">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="720ea-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
