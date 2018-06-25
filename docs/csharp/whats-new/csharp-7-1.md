---
title: Новые возможности C# 7.1
description: Обзор новых возможностей в C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728658"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="b61cd-103">Новые возможности C# 7.1</span><span class="sxs-lookup"><span data-stu-id="b61cd-103">What's new in C# 7.1</span></span>

<span data-ttu-id="b61cd-104">C# 7.1 — это первая доработанная версия для C#.</span><span class="sxs-lookup"><span data-stu-id="b61cd-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="b61cd-105">Это означает, что новые выпуски для этого языка стали выходить чаще.</span><span class="sxs-lookup"><span data-stu-id="b61cd-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="b61cd-106">Вы сможете использовать новые возможности раньше. В идеале — как только функция будет готова.</span><span class="sxs-lookup"><span data-stu-id="b61cd-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="b61cd-107">В C# 7.1 можно настраивать компилятор в соответствии с указанной версией языка.</span><span class="sxs-lookup"><span data-stu-id="b61cd-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="b61cd-108">Это позволяет отделить решение обновить средства от решения обновить версию языка.</span><span class="sxs-lookup"><span data-stu-id="b61cd-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="b61cd-109">В C# 7.1 добавлен элемент конфигурации [выбора версии языка](../language-reference/configure-language-version.md), три новые возможности языка и новое поведение компилятора.</span><span class="sxs-lookup"><span data-stu-id="b61cd-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="b61cd-110">Новые языковые функции в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="b61cd-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="b61cd-111">`async` метод `Main`</span><span class="sxs-lookup"><span data-stu-id="b61cd-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="b61cd-112">Точка входа для приложения может иметь модификатор `async`.</span><span class="sxs-lookup"><span data-stu-id="b61cd-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="b61cd-113">Литеральные выражения `default`</span><span class="sxs-lookup"><span data-stu-id="b61cd-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="b61cd-114">Литеральные выражения по умолчанию можно использовать в выражениях значения по умолчанию, если можно вывести тип целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="b61cd-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="b61cd-115">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="b61cd-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="b61cd-116">Имена элементов кортежа часто можно вывести из инициализации кортежа.</span><span class="sxs-lookup"><span data-stu-id="b61cd-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="b61cd-117">Наконец, у компилятора есть два параметра `/refout` и `/refonly`, которые управляют [созданием базовой сборки](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="b61cd-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="b61cd-118">Чтобы использовать новые возможности доработанной версии, [настройте версию языка компилятора](../language-reference/configure-language-version.md) и выберите версию.</span><span class="sxs-lookup"><span data-stu-id="b61cd-118">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

## <a name="async-main"></a><span data-ttu-id="b61cd-119">Async main</span><span class="sxs-lookup"><span data-stu-id="b61cd-119">Async main</span></span>

<span data-ttu-id="b61cd-120">Метод *async main* позволяет использовать `await` в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="b61cd-120">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="b61cd-121">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="b61cd-121">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="b61cd-122">Теперь можно написать:</span><span class="sxs-lookup"><span data-stu-id="b61cd-122">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="b61cd-123">Если программа не возвращает код выхода, объявите метод `Main`, возвращающий <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="b61cd-123">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="b61cd-124">Дополнительные сведения см. в разделе [async main](../programming-guide/main-and-command-args/index.md) в руководстве по программированию.</span><span class="sxs-lookup"><span data-stu-id="b61cd-124">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="b61cd-125">Литеральные выражения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b61cd-125">Default literal expressions</span></span>

<span data-ttu-id="b61cd-126">Литеральные выражения по умолчанию — это усовершенствование выражения значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b61cd-126">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="b61cd-127">Эти выражения инициализируют переменную до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b61cd-127">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="b61cd-128">Раньше пришлось бы написать:</span><span class="sxs-lookup"><span data-stu-id="b61cd-128">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="b61cd-129">Теперь можно опустить тип с правой стороны инициализации:</span><span class="sxs-lookup"><span data-stu-id="b61cd-129">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="b61cd-130">Дополнительные сведения об этом усовершенствовании см. в разделе о [выражениях значения по умолчанию](../programming-guide/statements-expressions-operators/default-value-expressions.md) в руководстве по программированию на C#.</span><span class="sxs-lookup"><span data-stu-id="b61cd-130">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="b61cd-131">В этом усовершенствовании также изменены некоторые правила синтаксического анализа для [ключевого слова default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="b61cd-131">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="b61cd-132">Выводимые имена элементов кортежа</span><span class="sxs-lookup"><span data-stu-id="b61cd-132">Inferred tuple element names</span></span>

<span data-ttu-id="b61cd-133">Эта возможность улучшает функцию кортежей, представленную в C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="b61cd-133">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="b61cd-134">Очень часто при инициализации кортежа переменные в правой части задания совпадают с именами для элементов кортежа:</span><span class="sxs-lookup"><span data-stu-id="b61cd-134">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="b61cd-135">Имена элементов кортежа можно вывести из переменных, используемых для инициализации кортежа в C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="b61cd-135">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="b61cd-136">Дополнительные сведения об этой функции см. в разделе [Кортежи](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="b61cd-136">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="b61cd-137">Создание базовой сборки</span><span class="sxs-lookup"><span data-stu-id="b61cd-137">Reference assembly generation</span></span>

<span data-ttu-id="b61cd-138">Существует два новых параметра компилятора, которые создают *сборки для справки*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) и [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b61cd-138">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="b61cd-139">В соответствующих разделах подробно рассматриваются эти параметры и базовые сборки.</span><span class="sxs-lookup"><span data-stu-id="b61cd-139">The linked topics explain these options and reference assemblies in more detail.</span></span>
