---
title: Выбор версии языка C#. Руководство по C#
description: Настройка компилятора для выполнения проверки синтаксиса с помощью конкретной версии компилятора
ms.date: 05/24/2018
ms.openlocfilehash: 2056a99544d0cac94bc7cc79e8cd8793b1bcff78
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566368"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="d1002-103">Выбор версии языка C#</span><span class="sxs-lookup"><span data-stu-id="d1002-103">Select the C# language version</span></span>

<span data-ttu-id="d1002-104">Компилятор C# по умолчанию использует последнюю доступную основную версию языка.</span><span class="sxs-lookup"><span data-stu-id="d1002-104">The C# compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="d1002-105">Можно выбрать компиляцию любого проекта с помощью новой доработанной версии языка.</span><span class="sxs-lookup"><span data-stu-id="d1002-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="d1002-106">Выбор более новой версии языка позволяет использовать в проекте новейшие возможности языка.</span><span class="sxs-lookup"><span data-stu-id="d1002-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="d1002-107">В других случаях может потребоваться убедиться, что проект компилируется без ошибок при использовании более старой версии языка.</span><span class="sxs-lookup"><span data-stu-id="d1002-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="d1002-108">Эта возможность разделяет установку новых версий пакета SDK и средств в среде разработки и включение новых возможностей языка в проект.</span><span class="sxs-lookup"><span data-stu-id="d1002-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="d1002-109">Вы можете установить последнюю версию пакета SDK и средств на компьютер сборки.</span><span class="sxs-lookup"><span data-stu-id="d1002-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="d1002-110">В каждом проекте можно настроить использование определенной версии языка для сборки.</span><span class="sxs-lookup"><span data-stu-id="d1002-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="d1002-111">Существует несколько способов задания языковой версии:</span><span class="sxs-lookup"><span data-stu-id="d1002-111">There are several ways to set the language version:</span></span>

- <span data-ttu-id="d1002-112">использование [быстрого действия Visual Studio](#visual-studio-quick-action);</span><span class="sxs-lookup"><span data-stu-id="d1002-112">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="d1002-113">установка версии языка в [пользовательском интерфейсе Visual Studio](#set-the-language-version-in-visual-studio);</span><span class="sxs-lookup"><span data-stu-id="d1002-113">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="d1002-114">ручное редактирование [**CSPROJ**-файла](#edit-the-csproj-file);</span><span class="sxs-lookup"><span data-stu-id="d1002-114">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="d1002-115">задание языковой версии [для нескольких проектов в подкаталоге](#configure-multiple-projects);</span><span class="sxs-lookup"><span data-stu-id="d1002-115">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="d1002-116">настройка [параметра компилятора `-langversion`](#set-the-langversion-compiler-option).</span><span class="sxs-lookup"><span data-stu-id="d1002-116">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="d1002-117">Быстрое действие Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d1002-117">Visual Studio quick action</span></span>

<span data-ttu-id="d1002-118">Visual Studio позволяет определить требуемую версию языка.</span><span class="sxs-lookup"><span data-stu-id="d1002-118">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="d1002-119">При использовании функции языка, которая недоступна для текущей выбранной версии, Visual Studio отображает возможное решение для изменения версии языка для проекта.</span><span class="sxs-lookup"><span data-stu-id="d1002-119">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="d1002-120">Установка версии языка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d1002-120">Set the language version in Visual Studio</span></span>

<span data-ttu-id="d1002-121">Вы можете задать версию в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1002-121">You can set the version in Visual Studio.</span></span> <span data-ttu-id="d1002-122">В обозревателе решений щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d1002-122">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="d1002-123">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="d1002-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="d1002-124">В раскрывающемся списке выберите версию.</span><span class="sxs-lookup"><span data-stu-id="d1002-124">In the dropdown, select the version.</span></span> <span data-ttu-id="d1002-125">На следующем рисунке показаны "последние" параметры:</span><span class="sxs-lookup"><span data-stu-id="d1002-125">The following image shows the "latest" setting:</span></span>

![Снимок экрана: дополнительные параметры сборки, в которых можно указать версию языка](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="d1002-127">Если вы используете интегрированную среду разработки Visual Studio для обновления CSPROJ-файлов, IDE создает отдельные узлы для каждой конфигурации сборки.</span><span class="sxs-lookup"><span data-stu-id="d1002-127">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="d1002-128">Как правило, вы устанавливаете одинаковое значение во всех конфигурациях сборки, но необходимо задать его явным образом для каждой конфигурации сборки или выбрать "Все конфигурации" при изменении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="d1002-128">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="d1002-129">В CSPROJ-файле вы увидите следующий код:</span><span class="sxs-lookup"><span data-stu-id="d1002-129">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="d1002-130">Редактирование CSPROJ-файла</span><span class="sxs-lookup"><span data-stu-id="d1002-130">Edit the csproj file</span></span>

<span data-ttu-id="d1002-131">Версию языка можно задать в **CSPROJ**-файле.</span><span class="sxs-lookup"><span data-stu-id="d1002-131">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="d1002-132">Добавьте элемент следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d1002-132">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="d1002-133">Значение параметра `latest` использует последнюю дополнительную версию языка C#.</span><span class="sxs-lookup"><span data-stu-id="d1002-133">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="d1002-134">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d1002-134">Valid values are:</span></span>

|<span data-ttu-id="d1002-135">Значение</span><span class="sxs-lookup"><span data-stu-id="d1002-135">Value</span></span>|<span data-ttu-id="d1002-136">Значение</span><span class="sxs-lookup"><span data-stu-id="d1002-136">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="d1002-137">default</span><span class="sxs-lookup"><span data-stu-id="d1002-137">default</span></span>|<span data-ttu-id="d1002-138">Компилятор допускает использование любого допустимого синтаксиса языка из последней основной версии, которую он поддерживает.</span><span class="sxs-lookup"><span data-stu-id="d1002-138">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="d1002-139">ISO-1</span><span class="sxs-lookup"><span data-stu-id="d1002-139">ISO-1</span></span>|<span data-ttu-id="d1002-140">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="d1002-140">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
|<span data-ttu-id="d1002-141">ISO-2</span><span class="sxs-lookup"><span data-stu-id="d1002-141">ISO-2</span></span>|<span data-ttu-id="d1002-142">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="d1002-142">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="d1002-143">3</span><span class="sxs-lookup"><span data-stu-id="d1002-143">3</span></span>|<span data-ttu-id="d1002-144">Компилятор принимает только синтаксис, включенный в спецификацию C# 3.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-144">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="d1002-145">4</span><span class="sxs-lookup"><span data-stu-id="d1002-145">4</span></span>|<span data-ttu-id="d1002-146">Компилятор принимает только синтаксис, включенный в спецификацию C# 4.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-146">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="d1002-147">5</span><span class="sxs-lookup"><span data-stu-id="d1002-147">5</span></span>|<span data-ttu-id="d1002-148">Компилятор принимает только синтаксис, включенный в спецификацию C# 5.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-148">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="d1002-149">6</span><span class="sxs-lookup"><span data-stu-id="d1002-149">6</span></span>|<span data-ttu-id="d1002-150">Компилятор принимает только синтаксис, включенный в спецификацию C# 6.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-150">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="d1002-151">7</span><span class="sxs-lookup"><span data-stu-id="d1002-151">7</span></span>|<span data-ttu-id="d1002-152">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.0 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-152">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="d1002-153">7.1</span><span class="sxs-lookup"><span data-stu-id="d1002-153">7.1</span></span>|<span data-ttu-id="d1002-154">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.1 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="d1002-155">7.2</span><span class="sxs-lookup"><span data-stu-id="d1002-155">7.2</span></span>|<span data-ttu-id="d1002-156">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.2 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-156">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="d1002-157">7.3</span><span class="sxs-lookup"><span data-stu-id="d1002-157">7.3</span></span>|<span data-ttu-id="d1002-158">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.3 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="d1002-158">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="d1002-159">latest</span><span class="sxs-lookup"><span data-stu-id="d1002-159">latest</span></span>|<span data-ttu-id="d1002-160">Компилятор допускает использование любого допустимого синтаксиса языка, который он может поддерживать.</span><span class="sxs-lookup"><span data-stu-id="d1002-160">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="d1002-161">В специальных строках `default` и `latest` будет указана соответственно последняя основная (C# 7.0) и дополнительная (C# 7.3) версия языка, установленная на компьютере сборки.</span><span class="sxs-lookup"><span data-stu-id="d1002-161">The special strings `default` and `latest` resolve to the latest major (C# 7.0) and minor (C# 7.3) language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="d1002-162">Настройка нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="d1002-162">Configure multiple projects</span></span>

<span data-ttu-id="d1002-163">Можно создать файл **Directory.build.props**, содержащий элемент `<LangVersion>`, чтобы настроить несколько каталогов.</span><span class="sxs-lookup"><span data-stu-id="d1002-163">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="d1002-164">Обычно это делается в каталоге решения.</span><span class="sxs-lookup"><span data-stu-id="d1002-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="d1002-165">Добавьте следующий код в файл **Directory.build.props** в каталоге решения:</span><span class="sxs-lookup"><span data-stu-id="d1002-165">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="d1002-166">Теперь сборки в каждом подкаталоге каталога, который содержит этот файл, будут использовать синтаксис C# версии 7.3.</span><span class="sxs-lookup"><span data-stu-id="d1002-166">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="d1002-167">Дополнительные сведения см. в статье о [настройке сборки](/visualstudio/msbuild/customize-your-build.md).</span><span class="sxs-lookup"><span data-stu-id="d1002-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build.md).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="d1002-168">Задание параметра компилятора langversion</span><span class="sxs-lookup"><span data-stu-id="d1002-168">Set the langversion compiler option</span></span>

<span data-ttu-id="d1002-169">Вы можете использовать параметр командной строки `-langversion`.</span><span class="sxs-lookup"><span data-stu-id="d1002-169">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="d1002-170">Дополнительные сведения см. в статье, посвященной параметру компилятора [-langversion](../language-reference/compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d1002-170">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="d1002-171">Чтобы просмотреть список допустимых значений, введите `csc -langversion:?`.</span><span class="sxs-lookup"><span data-stu-id="d1002-171">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
