---
title: Новые возможности C# 7.1
description: Обзор новых возможностей в C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: 4b7bd96e428f990b2db91a4cfd45da01dc133aac
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881546"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="aeec0-103">Новые возможности C# 7.1</span><span class="sxs-lookup"><span data-stu-id="aeec0-103">What's new in C# 7.1</span></span>

<span data-ttu-id="aeec0-104">C# 7.1 — это первая доработанная версия для C#.</span><span class="sxs-lookup"><span data-stu-id="aeec0-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="aeec0-105">Это означает, что новые выпуски для этого языка стали выходить чаще.</span><span class="sxs-lookup"><span data-stu-id="aeec0-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="aeec0-106">Вы сможете использовать новые возможности раньше. В идеале — как только функция будет готова.</span><span class="sxs-lookup"><span data-stu-id="aeec0-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="aeec0-107">В C# 7.1 можно настраивать компилятор в соответствии с указанной версией языка.</span><span class="sxs-lookup"><span data-stu-id="aeec0-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="aeec0-108">Это позволяет отделить решение обновить средства от решения обновить версию языка.</span><span class="sxs-lookup"><span data-stu-id="aeec0-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="aeec0-109">В C# 7.1 добавлен элемент конфигурации [выбора версии языка](../language-reference/configure-language-version.md), три новые возможности языка и новое поведение компилятора.</span><span class="sxs-lookup"><span data-stu-id="aeec0-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="aeec0-110">Новые языковые функции в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="aeec0-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="aeec0-111">`async` метод `Main`</span><span class="sxs-lookup"><span data-stu-id="aeec0-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="aeec0-112">Точка входа для приложения может иметь модификатор `async`.</span><span class="sxs-lookup"><span data-stu-id="aeec0-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="aeec0-113">Литеральные выражения `default`</span><span class="sxs-lookup"><span data-stu-id="aeec0-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="aeec0-114">Литеральные выражения по умолчанию можно использовать в выражениях значения по умолчанию, если можно вывести тип целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="aeec0-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="aeec0-115">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="aeec0-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="aeec0-116">Имена элементов кортежа часто можно вывести из инициализации кортежа.</span><span class="sxs-lookup"><span data-stu-id="aeec0-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
* [<span data-ttu-id="aeec0-117">Сопоставление шаблонов в параметрах универсального типа</span><span class="sxs-lookup"><span data-stu-id="aeec0-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="aeec0-118">Выражения сопоставления шаблонов можно использовать с переменными, тип которых является параметром универсального типа.</span><span class="sxs-lookup"><span data-stu-id="aeec0-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="aeec0-119">Наконец, у компилятора есть два параметра `-refout` и `-refonly`, которые управляют [созданием базовой сборки](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="aeec0-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="aeec0-120">Чтобы использовать новые возможности доработанного выпуска, [настройте версию языка компилятора](../language-reference/configure-language-version.md), выбрав необходимую.</span><span class="sxs-lookup"><span data-stu-id="aeec0-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

## <a name="async-main"></a><span data-ttu-id="aeec0-121">Async main</span><span class="sxs-lookup"><span data-stu-id="aeec0-121">Async main</span></span>

<span data-ttu-id="aeec0-122">Метод *async main* позволяет использовать `await` в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="aeec0-122">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="aeec0-123">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="aeec0-123">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="aeec0-124">Теперь можно написать:</span><span class="sxs-lookup"><span data-stu-id="aeec0-124">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="aeec0-125">Если программа не возвращает код выхода, объявите метод `Main`, возвращающий <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="aeec0-125">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="aeec0-126">См. подробнее в описании [async main](../programming-guide/main-and-command-args/index.md) в руководстве по программированию.</span><span class="sxs-lookup"><span data-stu-id="aeec0-126">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="aeec0-127">Литеральные выражения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="aeec0-127">Default literal expressions</span></span>

<span data-ttu-id="aeec0-128">Литеральные выражения по умолчанию — это усовершенствование выражения значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aeec0-128">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="aeec0-129">Эти выражения инициализируют переменную до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aeec0-129">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="aeec0-130">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="aeec0-130">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="aeec0-131">Теперь можно опустить тип с правой стороны инициализации:</span><span class="sxs-lookup"><span data-stu-id="aeec0-131">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="aeec0-132">См. подробнее об этом усовершенствовании в описании [выражений значений по умолчанию](../programming-guide/statements-expressions-operators/default-value-expressions.md) в руководстве по программированию на C#.</span><span class="sxs-lookup"><span data-stu-id="aeec0-132">You can learn more about this enhancement in the C# Programming Guide article on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="aeec0-133">В этом усовершенствовании также изменены некоторые правила синтаксического анализа для [ключевого слова default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="aeec0-133">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="aeec0-134">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="aeec0-134">Inferred tuple element names</span></span>

<span data-ttu-id="aeec0-135">Эта возможность улучшает функцию кортежей, представленную в C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="aeec0-135">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="aeec0-136">Очень часто при инициализации кортежа переменные в правой части задания совпадают с именами для элементов кортежа:</span><span class="sxs-lookup"><span data-stu-id="aeec0-136">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="aeec0-137">Имена элементов кортежа можно вывести из переменных, используемых для инициализации кортежа в C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="aeec0-137">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="aeec0-138">См. подробнее об этой функции в описании [кортежей](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="aeec0-138">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="aeec0-139">Сопоставление шаблонов в параметрах универсального типа</span><span class="sxs-lookup"><span data-stu-id="aeec0-139">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="aeec0-140">Начиная с версии C# 7.1, выражение шаблона для шаблона типа `is` и `switch` может быть типом параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="aeec0-140">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="aeec0-141">Эта возможность особенно полезна при проверке типов, которые могут представлять типы `struct` или `class`, когда вы хотите избежать упаковки-преобразования.</span><span class="sxs-lookup"><span data-stu-id="aeec0-141">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="aeec0-142">Создание базовой сборки</span><span class="sxs-lookup"><span data-stu-id="aeec0-142">Reference assembly generation</span></span>

<span data-ttu-id="aeec0-143">Существует два новых параметра компилятора, которые создают *только базовые сборки*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) и [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="aeec0-143">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="aeec0-144">В соответствующих статьях подробно рассматриваются эти параметры и базовые сборки.</span><span class="sxs-lookup"><span data-stu-id="aeec0-144">The linked articles explain these options and reference assemblies in more detail.</span></span>
