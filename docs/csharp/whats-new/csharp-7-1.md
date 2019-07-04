---
title: Новые возможности C# 7.1
description: Обзор новых возможностей в C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: a95111b6f217a2ca5c520c2d4d70efa0e23742f9
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347605"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="f6a20-103">Новые возможности C# 7.1</span><span class="sxs-lookup"><span data-stu-id="f6a20-103">What's new in C# 7.1</span></span>

<span data-ttu-id="f6a20-104">C# 7.1 — это первая доработанная версия для C#.</span><span class="sxs-lookup"><span data-stu-id="f6a20-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="f6a20-105">Это означает, что новые выпуски для этого языка стали выходить чаще.</span><span class="sxs-lookup"><span data-stu-id="f6a20-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="f6a20-106">Вы сможете использовать новые возможности раньше. В идеале — как только функция будет готова.</span><span class="sxs-lookup"><span data-stu-id="f6a20-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="f6a20-107">В C# 7.1 можно настраивать компилятор в соответствии с указанной версией языка.</span><span class="sxs-lookup"><span data-stu-id="f6a20-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="f6a20-108">Это позволяет отделить решение обновить средства от решения обновить версию языка.</span><span class="sxs-lookup"><span data-stu-id="f6a20-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="f6a20-109">В C# 7.1 добавлен элемент конфигурации [выбора версии языка](../language-reference/configure-language-version.md), три новые возможности языка и новое поведение компилятора.</span><span class="sxs-lookup"><span data-stu-id="f6a20-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="f6a20-110">Новые языковые функции в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="f6a20-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="f6a20-111">`async` метод `Main`</span><span class="sxs-lookup"><span data-stu-id="f6a20-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="f6a20-112">Точка входа для приложения может иметь модификатор `async`.</span><span class="sxs-lookup"><span data-stu-id="f6a20-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="f6a20-113">Литеральные выражения `default`</span><span class="sxs-lookup"><span data-stu-id="f6a20-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="f6a20-114">Литеральные выражения по умолчанию можно использовать в выражениях значения по умолчанию, если можно вывести тип целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="f6a20-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="f6a20-115">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="f6a20-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="f6a20-116">Имена элементов кортежа часто можно вывести из инициализации кортежа.</span><span class="sxs-lookup"><span data-stu-id="f6a20-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
* [<span data-ttu-id="f6a20-117">Сопоставление шаблонов в параметрах универсального типа</span><span class="sxs-lookup"><span data-stu-id="f6a20-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="f6a20-118">Выражения сопоставления шаблонов можно использовать с переменными, тип которых является параметром универсального типа.</span><span class="sxs-lookup"><span data-stu-id="f6a20-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="f6a20-119">Наконец, у компилятора есть два параметра `-refout` и `-refonly`, которые управляют [созданием базовой сборки](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="f6a20-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="f6a20-120">Чтобы использовать новые возможности доработанного выпуска, [настройте версию языка компилятора](../language-reference/configure-language-version.md), выбрав необходимую.</span><span class="sxs-lookup"><span data-stu-id="f6a20-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

<span data-ttu-id="f6a20-121">В оставшейся части этой статьи представлены общие сведения об этих функциях.</span><span class="sxs-lookup"><span data-stu-id="f6a20-121">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="f6a20-122">Каждая функция сопровождается обоснованием.</span><span class="sxs-lookup"><span data-stu-id="f6a20-122">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="f6a20-123">Вы изучите синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6a20-123">You'll learn the syntax.</span></span> <span data-ttu-id="f6a20-124">Эти функции можно изучить в своей среде с помощью глобального средства `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="f6a20-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="f6a20-125">Установите глобальное средство [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="f6a20-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="f6a20-126">Клонируйте репозиторий [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="f6a20-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="f6a20-127">Для репозитория *try-samples* установите в качестве текущего каталога подкаталог *csharp7*.</span><span class="sxs-lookup"><span data-stu-id="f6a20-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="f6a20-128">Запустите `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="f6a20-128">Run `dotnet try`.</span></span>

## <a name="async-main"></a><span data-ttu-id="f6a20-129">Async main</span><span class="sxs-lookup"><span data-stu-id="f6a20-129">Async main</span></span>

<span data-ttu-id="f6a20-130">Метод *async main* позволяет использовать `await` в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="f6a20-130">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="f6a20-131">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="f6a20-131">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="f6a20-132">Теперь можно написать:</span><span class="sxs-lookup"><span data-stu-id="f6a20-132">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="f6a20-133">Если программа не возвращает код выхода, объявите метод `Main`, возвращающий <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="f6a20-133">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="f6a20-134">См. подробнее в описании [async main](../programming-guide/main-and-command-args/index.md) в руководстве по программированию.</span><span class="sxs-lookup"><span data-stu-id="f6a20-134">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="f6a20-135">Литеральные выражения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f6a20-135">Default literal expressions</span></span>

<span data-ttu-id="f6a20-136">Литеральные выражения по умолчанию — это усовершенствование выражения значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6a20-136">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="f6a20-137">Эти выражения инициализируют переменную до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6a20-137">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="f6a20-138">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="f6a20-138">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="f6a20-139">Теперь можно опустить тип с правой стороны инициализации:</span><span class="sxs-lookup"><span data-stu-id="f6a20-139">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="f6a20-140">См. подробнее об этом усовершенствовании в описании [выражений значений по умолчанию](../programming-guide/statements-expressions-operators/default-value-expressions.md) в руководстве по программированию на C#.</span><span class="sxs-lookup"><span data-stu-id="f6a20-140">You can learn more about this enhancement in the C# Programming Guide article on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="f6a20-141">В этом усовершенствовании также изменены некоторые правила синтаксического анализа для [ключевого слова default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="f6a20-141">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="f6a20-142">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="f6a20-142">Inferred tuple element names</span></span>

<span data-ttu-id="f6a20-143">Эта возможность улучшает функцию кортежей, представленную в C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="f6a20-143">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="f6a20-144">Очень часто при инициализации кортежа переменные в правой части задания совпадают с именами для элементов кортежа:</span><span class="sxs-lookup"><span data-stu-id="f6a20-144">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="f6a20-145">Имена элементов кортежа можно вывести из переменных, используемых для инициализации кортежа в C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="f6a20-145">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="f6a20-146">См. подробнее об этой функции в описании [кортежей](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="f6a20-146">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="f6a20-147">Сопоставление шаблонов в параметрах универсального типа</span><span class="sxs-lookup"><span data-stu-id="f6a20-147">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="f6a20-148">Начиная с версии C# 7.1, выражение шаблона для шаблона типа `is` и `switch` может быть типом параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="f6a20-148">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="f6a20-149">Эта возможность особенно полезна при проверке типов, которые могут представлять типы `struct` или `class`, когда вы хотите избежать упаковки-преобразования.</span><span class="sxs-lookup"><span data-stu-id="f6a20-149">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="f6a20-150">Создание базовой сборки</span><span class="sxs-lookup"><span data-stu-id="f6a20-150">Reference assembly generation</span></span>

<span data-ttu-id="f6a20-151">Существует два новых параметра компилятора, которые создают *только базовые сборки*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) и [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f6a20-151">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="f6a20-152">В соответствующих статьях подробно рассматриваются эти параметры и базовые сборки.</span><span class="sxs-lookup"><span data-stu-id="f6a20-152">The linked articles explain these options and reference assemblies in more detail.</span></span>
