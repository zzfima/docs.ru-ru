---
title: "Новые возможности C# 7.1"
description: "Общие сведения о новых функциях в C# 7.1."
keywords: "C# конструкции языка, 7.1, Visual Studio 2017 г.,"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="3f521-104">Новые возможности C# 7.1</span><span class="sxs-lookup"><span data-stu-id="3f521-104">What's new in C# 7.1</span></span>

<span data-ttu-id="3f521-105">7.1 C# находится в первом выпуске точки для языка C#.</span><span class="sxs-lookup"><span data-stu-id="3f521-105">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="3f521-106">Он отмечает последовательность Повышенная выпусков для языка.</span><span class="sxs-lookup"><span data-stu-id="3f521-106">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="3f521-107">Можно использовать новые функции раньше, в идеале при готовности каждой новой функции.</span><span class="sxs-lookup"><span data-stu-id="3f521-107">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="3f521-108">7.1 C# добавляет возможность настройки компилятора в соответствии с указанной версией языка.</span><span class="sxs-lookup"><span data-stu-id="3f521-108">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="3f521-109">Позволяет отделить решение обновление средств решение для обновления версии языка.</span><span class="sxs-lookup"><span data-stu-id="3f521-109">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="3f521-110">Добавляет C# 7.1 [Выбор версии языка](#language-version-selection) элемента конфигурации, три новые возможности языка и новое поведение компилятора.</span><span class="sxs-lookup"><span data-stu-id="3f521-110">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="3f521-111">Ниже перечислены новые возможности языка в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="3f521-111">The new language features in this release are:</span></span>

* [<span data-ttu-id="3f521-112">`async``Main` метод</span><span class="sxs-lookup"><span data-stu-id="3f521-112">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="3f521-113">Точка входа для приложения может иметь `async` модификатор.</span><span class="sxs-lookup"><span data-stu-id="3f521-113">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="3f521-114">`default`литеральные выражения</span><span class="sxs-lookup"><span data-stu-id="3f521-114">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="3f521-115">Литеральные выражения по умолчанию можно использовать в выражениях значение по умолчанию, если целевой тип может быть выведен.</span><span class="sxs-lookup"><span data-stu-id="3f521-115">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="3f521-116">Имена элементов выводимых кортежа</span><span class="sxs-lookup"><span data-stu-id="3f521-116">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="3f521-117">Имена элементов кортежа может быть выведен из кортежей инициализации во многих случаях.</span><span class="sxs-lookup"><span data-stu-id="3f521-117">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="3f521-118">Наконец, у компилятора имеются два варианта `/refout` и `/refonly` этого элемента управления [ссылаются на создание сборки](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="3f521-118">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="3f521-119">Выбор версии языка</span><span class="sxs-lookup"><span data-stu-id="3f521-119">Language version selection</span></span>

<span data-ttu-id="3f521-120">Компилятор C# поддерживает 7.1 C#, начиная с версии 15,3 2017 г. Visual Studio или .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="3f521-120">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="3f521-121">Тем не менее 7.1 компоненты отключены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f521-121">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="3f521-122">Чтобы включить функции 7.1, необходимо изменить параметр версии языка для проекта.</span><span class="sxs-lookup"><span data-stu-id="3f521-122">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="3f521-123">В Visual Studio, щелкните правой кнопкой мыши узел проекта в обозревателе решений и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="3f521-123">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="3f521-124">Выберите **построения** и выберите **Дополнительно** кнопки.</span><span class="sxs-lookup"><span data-stu-id="3f521-124">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="3f521-125">В раскрывающемся списке выберите **C# последняя вспомогательная версия (последняя)**, или конкретная версия **C# 7.1** как показано в следующем изображения.</span><span class="sxs-lookup"><span data-stu-id="3f521-125">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="3f521-126">`latest` Значение указывает, будет использоваться последняя вспомогательная версия на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="3f521-126">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="3f521-127">`C# 7.1` Означает, что вы хотите использовать C# 7.1, даже после выпускаются новые дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="3f521-127">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Установка на английском языке](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="3f521-129">Кроме того можно изменить файл «csproj» и добавьте или измените следующие строки:</span><span class="sxs-lookup"><span data-stu-id="3f521-129">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="3f521-130">Если вы используете интегрированную среду разработки Visual Studio для обновления файлов csproj, IDE создает отдельные узлы для каждой конфигурации сборки.</span><span class="sxs-lookup"><span data-stu-id="3f521-130">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="3f521-131">Вы будете обычно устанавливается значение же во всех конфигурациях сборки, но необходимо задать явным образом для каждой конфигурации сборки, или выберите «Все конфигурации» после изменения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="3f521-131">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="3f521-132">Вы увидите следующее в csproj-файле:</span><span class="sxs-lookup"><span data-stu-id="3f521-132">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="3f521-133">Допустимые значения для `LangVersion` являются:</span><span class="sxs-lookup"><span data-stu-id="3f521-133">Valid settings for the `LangVersion` element are:</span></span>

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

<span data-ttu-id="3f521-134">Специальные строки `default` и `latest` решения до последних версий основной и дополнительный язык установлен на компьютере построения, соответственно.</span><span class="sxs-lookup"><span data-stu-id="3f521-134">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="3f521-135">Этот параметр выполняет установку новых версий пакета SDK и средств в среде разработки в выборе внедрить новые возможности языка в проекте.</span><span class="sxs-lookup"><span data-stu-id="3f521-135">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="3f521-136">Последние версии пакета SDK и средства можно установить на компьютере сборки.</span><span class="sxs-lookup"><span data-stu-id="3f521-136">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="3f521-137">Каждый проект можно настроить для использования определенной версии языка для его сборки.</span><span class="sxs-lookup"><span data-stu-id="3f521-137">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="3f521-138">Основной Async</span><span class="sxs-lookup"><span data-stu-id="3f521-138">Async main</span></span>

<span data-ttu-id="3f521-139">*Async основной* метод дает возможность использовать `await` в ваш `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="3f521-139">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="3f521-140">Ранее вы должны были написать:</span><span class="sxs-lookup"><span data-stu-id="3f521-140">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="3f521-141">Теперь можно написать:</span><span class="sxs-lookup"><span data-stu-id="3f521-141">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="3f521-142">Если программа не возвращает код выхода, можно объявить `Main` метод, возвращающий <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="3f521-142">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="3f521-143">Дополнительные подробные сведения в [async основной](../programming-guide/main-and-command-args/index.md) раздела руководства программирования.</span><span class="sxs-lookup"><span data-stu-id="3f521-143">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="3f521-144">Литеральные выражения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3f521-144">Default literal expressions</span></span>

<span data-ttu-id="3f521-145">Литеральные выражения по умолчанию — это усовершенствование выражения значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f521-145">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="3f521-146">Эти выражения инициализации переменной значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f521-146">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="3f521-147">Где вы ранее написать:</span><span class="sxs-lookup"><span data-stu-id="3f521-147">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="3f521-148">Теперь можно опустить тип с правой стороны инициализации:</span><span class="sxs-lookup"><span data-stu-id="3f521-148">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="3f521-149">Дополнительные сведения о этого компонента в разделе Руководство по программированию C# на [выражения значения по умолчанию](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3f521-149">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="3f521-150">Это расширение также изменяет некоторые правила синтаксического разбора для [ключевое слово default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="3f521-150">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="3f521-151">Имена элементов выводимых кортежа</span><span class="sxs-lookup"><span data-stu-id="3f521-151">Inferred tuple element names</span></span>

<span data-ttu-id="3f521-152">Эта возможность очень небольшое улучшение для функции кортежей, была представлена в C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="3f521-152">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="3f521-153">Много раз при инициализации кортеж переменных, используемых для правой части назначения совпадают с именами, которые будут отправлены для элементов кортежа:</span><span class="sxs-lookup"><span data-stu-id="3f521-153">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="3f521-154">Имена элементов кортежа может быть выведен из переменных, используемых для инициализации кортеж в C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="3f521-154">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="3f521-155">Дополнительные сведения об этой возможности в [кортежей](../tuples.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="3f521-155">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="3f521-156">Создание сборки ссылок</span><span class="sxs-lookup"><span data-stu-id="3f521-156">Reference assembly generation</span></span>

<span data-ttu-id="3f521-157">Существует два варианта компилятора, которые создают *только для ссылки сборкам*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) и [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3f521-157">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="3f521-158">В связанных разделах описаны эти параметры и ссылочные сборки более подробно.</span><span class="sxs-lookup"><span data-stu-id="3f521-158">The linked topics explain these options and reference assemblies in more detail.</span></span>
