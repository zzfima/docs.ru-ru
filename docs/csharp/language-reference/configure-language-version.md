---
title: Управление версиями языка C# — руководство по C#
description: Дополнительные сведения о том, как версия языка C# определяется на основе вашего проекта и какие значения можно настроить вручную.
ms.date: 07/10/2019
ms.openlocfilehash: fae36f5305e23fbfa1c55c5881e37391670f93ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040353"
---
# <a name="c-language-versioning"></a><span data-ttu-id="479d6-103">Управление версиями языка C#</span><span class="sxs-lookup"><span data-stu-id="479d6-103">C# language versioning</span></span>

<span data-ttu-id="479d6-104">Компилятор C# последней версии определяет версию языка по умолчанию на основе целевой платформы или платформ проекта.</span><span class="sxs-lookup"><span data-stu-id="479d6-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="479d6-105">Это обусловлено тем, что язык C# может иметь функции, которые зависят от типов или компонентов среды выполнения и не доступны в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="479d6-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="479d6-106">Это также гарантирует, что для любой целевой платформы, для которой выполняется сборка проекта, вы получаете последнюю совместимую версию языка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="479d6-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="479d6-107">Правила, описанные в этой статье, относятся к компилятору, поставляемому с Visual Studio 2019, или пакету SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="479d6-107">The rules in this article apply to the compiler delivered with Visual Studio 2019, or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="479d6-108">Компиляторы C#, которые являются частью установки Visual Studio 2017 или более ранних версий пакета SDK для .NET Core предназначены для C# 7.0 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="479d6-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="479d6-109">расписания</span><span class="sxs-lookup"><span data-stu-id="479d6-109">Defaults</span></span>

<span data-ttu-id="479d6-110">Компилятор определяет значение по умолчанию на основе следующих правил:</span><span class="sxs-lookup"><span data-stu-id="479d6-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="479d6-111">Целевая платформа</span><span class="sxs-lookup"><span data-stu-id="479d6-111">Target framework</span></span>|<span data-ttu-id="479d6-112">version</span><span class="sxs-lookup"><span data-stu-id="479d6-112">version</span></span>|<span data-ttu-id="479d6-113">Версия языка C# по умолчанию</span><span class="sxs-lookup"><span data-stu-id="479d6-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="479d6-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="479d6-114">.NET Core</span></span>|<span data-ttu-id="479d6-115">3.x</span><span class="sxs-lookup"><span data-stu-id="479d6-115">3.x</span></span>|<span data-ttu-id="479d6-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="479d6-116">C# 8.0</span></span>|
|<span data-ttu-id="479d6-117">.NET Core</span><span class="sxs-lookup"><span data-stu-id="479d6-117">.NET Core</span></span>|<span data-ttu-id="479d6-118">2.x</span><span class="sxs-lookup"><span data-stu-id="479d6-118">2.x</span></span>|<span data-ttu-id="479d6-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="479d6-119">C# 7.3</span></span>|
|<span data-ttu-id="479d6-120">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="479d6-120">.NET Standard</span></span>|<span data-ttu-id="479d6-121">все</span><span class="sxs-lookup"><span data-stu-id="479d6-121">all</span></span>|<span data-ttu-id="479d6-122">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="479d6-122">C# 7.3</span></span>|
|<span data-ttu-id="479d6-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="479d6-123">.NET Framework</span></span>|<span data-ttu-id="479d6-124">все</span><span class="sxs-lookup"><span data-stu-id="479d6-124">all</span></span>|<span data-ttu-id="479d6-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="479d6-125">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="479d6-126">Параметры по умолчанию для предварительных версий</span><span class="sxs-lookup"><span data-stu-id="479d6-126">Default for previews</span></span>

<span data-ttu-id="479d6-127">Если проект предназначен для платформы в предварительной версии с поддержкой соответствующего языка в предварительной версии, будет использоваться язык, поддерживаемый в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-127">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="479d6-128">Это гарантирует, что вы можете использовать новейшие возможности, которые точно будут работать с этой предварительной версией в любой среде, не затрагивая проекты, предназначенные для выпущенной версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="479d6-128">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="479d6-129">Переопределение значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="479d6-129">Override a default</span></span>

<span data-ttu-id="479d6-130">Если необходимо явно указать версию C#, это можно сделать несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="479d6-130">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="479d6-131">Вручную изменить [файл проекта](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="479d6-131">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="479d6-132">задание языковой версии [для нескольких проектов в подкаталоге](#configure-multiple-projects);</span><span class="sxs-lookup"><span data-stu-id="479d6-132">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="479d6-133">настройка [параметра компилятора `-langversion`](compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="479d6-133">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="479d6-134">Изменение файла проекта</span><span class="sxs-lookup"><span data-stu-id="479d6-134">Edit the project file</span></span>

<span data-ttu-id="479d6-135">Версию языка можно задать в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="479d6-135">You can set the language version in your project file.</span></span> <span data-ttu-id="479d6-136">Например, если доступ к предварительной версии функций должен быть задан явным образом, можно добавить следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="479d6-136">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="479d6-137">Значение `preview` использует последнюю предварительную версию языка C#, которую поддерживает компилятор.</span><span class="sxs-lookup"><span data-stu-id="479d6-137">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="479d6-138">Настройка нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="479d6-138">Configure multiple projects</span></span>

<span data-ttu-id="479d6-139">Можно создать файл **Directory.Build.props**, содержащий элемент `<LangVersion>`, чтобы настроить несколько каталогов.</span><span class="sxs-lookup"><span data-stu-id="479d6-139">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="479d6-140">Обычно это делается в каталоге решения.</span><span class="sxs-lookup"><span data-stu-id="479d6-140">You typically do that in your solution directory.</span></span> <span data-ttu-id="479d6-141">Добавьте следующий код в файл **Directory.Build.props** в каталоге решения:</span><span class="sxs-lookup"><span data-stu-id="479d6-141">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="479d6-142">Теперь сборки в каждом подкаталоге каталога, который содержит этот файл, будут использовать предварительную версию C#.</span><span class="sxs-lookup"><span data-stu-id="479d6-142">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="479d6-143">Дополнительные сведения см. в статье о [настройке сборки](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="479d6-143">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="479d6-144">Справочник по версиям языка C#</span><span class="sxs-lookup"><span data-stu-id="479d6-144">C# language version reference</span></span>

<span data-ttu-id="479d6-145">В следующей таблице показаны все текущие версии языка C#.</span><span class="sxs-lookup"><span data-stu-id="479d6-145">The following table shows all current C# language versions.</span></span> <span data-ttu-id="479d6-146">Ваш компилятор может не распознавать все значения, если имеет более раннюю версию.</span><span class="sxs-lookup"><span data-stu-id="479d6-146">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="479d6-147">Если вы установите .NET Core 3.0, вы получите доступ ко всем значениям в таблице.</span><span class="sxs-lookup"><span data-stu-id="479d6-147">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="479d6-148">Значение</span><span class="sxs-lookup"><span data-stu-id="479d6-148">Value</span></span>|<span data-ttu-id="479d6-149">Значение</span><span class="sxs-lookup"><span data-stu-id="479d6-149">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="479d6-150">preview</span><span class="sxs-lookup"><span data-stu-id="479d6-150">preview</span></span>|<span data-ttu-id="479d6-151">Компилятор допускает использование любого допустимого синтаксиса языка из последней предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-151">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="479d6-152">latest</span><span class="sxs-lookup"><span data-stu-id="479d6-152">latest</span></span>|<span data-ttu-id="479d6-153">Компилятор принимает синтаксис из последней выпущенной версии компилятора (включая дополнительный номер версии).</span><span class="sxs-lookup"><span data-stu-id="479d6-153">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="479d6-154">latestMajor</span><span class="sxs-lookup"><span data-stu-id="479d6-154">latestMajor</span></span>|<span data-ttu-id="479d6-155">Компилятор принимает синтаксис из последней основной версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="479d6-155">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="479d6-156">8.0</span><span class="sxs-lookup"><span data-stu-id="479d6-156">8.0</span></span>|<span data-ttu-id="479d6-157">Компилятор принимает только синтаксис, включенный в спецификацию C# 8.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-157">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="479d6-158">7.3</span><span class="sxs-lookup"><span data-stu-id="479d6-158">7.3</span></span>|<span data-ttu-id="479d6-159">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.3 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-159">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="479d6-160">7.2</span><span class="sxs-lookup"><span data-stu-id="479d6-160">7.2</span></span>|<span data-ttu-id="479d6-161">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.2 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-161">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="479d6-162">7.1</span><span class="sxs-lookup"><span data-stu-id="479d6-162">7.1</span></span>|<span data-ttu-id="479d6-163">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.1 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-163">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="479d6-164">7</span><span class="sxs-lookup"><span data-stu-id="479d6-164">7</span></span>|<span data-ttu-id="479d6-165">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-165">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="479d6-166">6</span><span class="sxs-lookup"><span data-stu-id="479d6-166">6</span></span>|<span data-ttu-id="479d6-167">Компилятор принимает только синтаксис, включенный в спецификацию C# 6.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-167">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="479d6-168">5</span><span class="sxs-lookup"><span data-stu-id="479d6-168">5</span></span>|<span data-ttu-id="479d6-169">Компилятор принимает только синтаксис, включенный в спецификацию C# 5.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-169">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="479d6-170">4</span><span class="sxs-lookup"><span data-stu-id="479d6-170">4</span></span>|<span data-ttu-id="479d6-171">Компилятор принимает только синтаксис, включенный в спецификацию C# 4.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-171">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="479d6-172">3</span><span class="sxs-lookup"><span data-stu-id="479d6-172">3</span></span>|<span data-ttu-id="479d6-173">Компилятор принимает только синтаксис, включенный в спецификацию C# 3.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="479d6-173">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="479d6-174">ISO-2</span><span class="sxs-lookup"><span data-stu-id="479d6-174">ISO-2</span></span>|<span data-ttu-id="479d6-175">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="479d6-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="479d6-176">ISO-1</span><span class="sxs-lookup"><span data-stu-id="479d6-176">ISO-1</span></span>|<span data-ttu-id="479d6-177">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="479d6-177">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
