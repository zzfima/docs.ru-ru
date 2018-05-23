---
title: Новые возможности C# 7.1
description: Обзор новых возможностей в C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="ee0b3-103">Новые возможности C# 7.1</span><span class="sxs-lookup"><span data-stu-id="ee0b3-103">What's new in C# 7.1</span></span>

<span data-ttu-id="ee0b3-104">C# 7.1 — это первая доработанная версия для C#.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="ee0b3-105">Это означает, что новые выпуски для этого языка стали выходить чаще.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="ee0b3-106">Вы сможете использовать новые возможности раньше. В идеале — как только функция будет готова.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="ee0b3-107">В C# 7.1 можно настраивать компилятор в соответствии с указанной версией языка.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="ee0b3-108">Это позволяет отделить решение обновить средства от решения обновить версию языка.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="ee0b3-109">В C# 7.1 добавлен элемент конфигурации [выбора версии языка](#language-version-selection), три новые возможности языка и новое поведение компилятора.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-109">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="ee0b3-110">Новые языковые функции в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="ee0b3-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="ee0b3-111">`async` метод `Main`</span><span class="sxs-lookup"><span data-stu-id="ee0b3-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="ee0b3-112">Точка входа для приложения может иметь модификатор `async`.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="ee0b3-113">Литеральные выражения `default`</span><span class="sxs-lookup"><span data-stu-id="ee0b3-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="ee0b3-114">Литеральные выражения по умолчанию можно использовать в выражениях значения по умолчанию, если можно вывести тип целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="ee0b3-115">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="ee0b3-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="ee0b3-116">Имена элементов кортежа часто можно вывести из инициализации кортежа.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="ee0b3-117">Наконец, у компилятора есть два параметра `/refout` и `/refonly`, которые управляют [созданием базовой сборки](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="ee0b3-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="ee0b3-118">Выбор версии языка</span><span class="sxs-lookup"><span data-stu-id="ee0b3-118">Language version selection</span></span>

<span data-ttu-id="ee0b3-119">Компилятор C# поддерживает C# 7.1 начиная с Visual Studio 2017 версии 15.3 или пакета SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-119">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="ee0b3-120">Но компоненты версии 7.1 по умолчанию отключены.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-120">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="ee0b3-121">Чтобы включить компоненты версии 7.1, необходимо изменить параметр версии языка для проекта.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-121">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="ee0b3-122">В Visual Studio щелкните правой кнопкой мыши узел проекта в обозревателе решений и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-122">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="ee0b3-123">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="ee0b3-124">В раскрывающемся списке выберите **Последняя дополнительная версия C# (последняя)** или конкретную версию **C# 7.1**, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-124">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="ee0b3-125">Значение `latest` указывает, что вы хотите использовать последнюю дополнительную версию на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-125">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="ee0b3-126">`C# 7.1` означает, что вы хотите использовать C# 7.1 даже после выпуска новой дополнительной версии.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-126">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Установка версии языка](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="ee0b3-128">Вы также можете отредактировать CSPROJ-файл и добавить или изменить следующие строки:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-128">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="ee0b3-129">Если вы используете интегрированную среду разработки Visual Studio для обновления CSPROJ-файлов, IDE создает отдельные узлы для каждой конфигурации сборки.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-129">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="ee0b3-130">Как правило, вы устанавливаете одинаковое значение во всех конфигурациях сборки, но необходимо задать его явным образом для каждой конфигурации сборки или выбрать "Все конфигурации" при изменении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-130">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="ee0b3-131">В CSPROJ-файле вы увидите следующий код:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-131">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="ee0b3-132">Допустимые значения для `LangVersion`:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-132">Valid settings for the `LangVersion` element are:</span></span>

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

<span data-ttu-id="ee0b3-133">В специальных строках `default` и `latest` будет указана соответственно последняя основная и дополнительная версия языка, установленная на компьютере сборки.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-133">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="ee0b3-134">Этот параметр разделяет установку новых версий пакета SDK и средств в среде разработки и включение новых возможностей языка в проект.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-134">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="ee0b3-135">Вы можете установить последнюю версию пакета SDK и средств на компьютер сборки.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-135">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="ee0b3-136">В каждом проекте можно настроить использование определенной версии языка для сборки.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-136">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="ee0b3-137">Async main</span><span class="sxs-lookup"><span data-stu-id="ee0b3-137">Async main</span></span>

<span data-ttu-id="ee0b3-138">Метод *async main* позволяет использовать `await` в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-138">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="ee0b3-139">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-139">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="ee0b3-140">Теперь можно написать:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-140">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="ee0b3-141">Если программа не возвращает код выхода, объявите метод `Main`, возвращающий <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-141">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="ee0b3-142">Дополнительные сведения см. в разделе [async main](../programming-guide/main-and-command-args/index.md) в руководстве по программированию.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-142">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="ee0b3-143">Литеральные выражения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ee0b3-143">Default literal expressions</span></span>

<span data-ttu-id="ee0b3-144">Литеральные выражения по умолчанию — это усовершенствование выражения значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-144">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="ee0b3-145">Эти выражения инициализируют переменную до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-145">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="ee0b3-146">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-146">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="ee0b3-147">Теперь можно опустить тип с правой стороны инициализации:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-147">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="ee0b3-148">Дополнительные сведения об этом усовершенствовании см. в разделе о [выражениях значения по умолчанию](../programming-guide/statements-expressions-operators/default-value-expressions.md) в руководстве по программированию на C#.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-148">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="ee0b3-149">В этом усовершенствовании также изменены некоторые правила синтаксического анализа для [ключевого слова default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="ee0b3-149">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="ee0b3-150">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="ee0b3-150">Inferred tuple element names</span></span>

<span data-ttu-id="ee0b3-151">Эта возможность улучшает функцию кортежей, представленную в C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-151">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="ee0b3-152">Очень часто при инициализации кортежа переменные в правой части задания совпадают с именами для элементов кортежа:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-152">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="ee0b3-153">Имена элементов кортежа можно вывести из переменных, используемых для инициализации кортежа в C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="ee0b3-153">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="ee0b3-154">Дополнительные сведения об этой функции см. в разделе [Кортежи](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="ee0b3-154">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="ee0b3-155">Создание базовой сборки</span><span class="sxs-lookup"><span data-stu-id="ee0b3-155">Reference assembly generation</span></span>

<span data-ttu-id="ee0b3-156">Существует два новых параметра компилятора, которые создают *сборки для справки*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) и [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ee0b3-156">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="ee0b3-157">В соответствующих разделах подробно рассматриваются эти параметры и базовые сборки.</span><span class="sxs-lookup"><span data-stu-id="ee0b3-157">The linked topics explain these options and reference assemblies in more detail.</span></span>
