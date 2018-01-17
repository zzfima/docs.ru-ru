---
title: "Новые возможности C# 7.2"
description: "Обзор новых возможностей в C# 7.2."
keywords: "Разработка языка C#, версия 7.2, Visual Studio 2017"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 9e7fefde6763dbd5c73c01e45e5652d9f207c213
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="fd304-104">Новые возможности C# 7.2</span><span class="sxs-lookup"><span data-stu-id="fd304-104">What's new in C# 7.2</span></span>

<span data-ttu-id="fd304-105">В очередной версии C# 7.2 реализован ряд новых полезных возможностей.</span><span class="sxs-lookup"><span data-stu-id="fd304-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="fd304-106">Одной из основных задач этого выпуска стало повышение эффективности работы с типами значений за счет исключения избыточных операций копирования и выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="fd304-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="fd304-107">Остальные нововведения реализованы преимущественно для удобства.</span><span class="sxs-lookup"><span data-stu-id="fd304-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="fd304-108">В C# 7.2 предусмотрен элемент управления [выбором версии языка](csharp-7-1.md#language-version-selection), с помощью которого можно задать версию языка компилятора.</span><span class="sxs-lookup"><span data-stu-id="fd304-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="fd304-109">Новые языковые функции в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="fd304-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="fd304-110">Семантика ссылок с типами значений</span><span class="sxs-lookup"><span data-stu-id="fd304-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="fd304-111">Ряд улучшений синтаксиса, обеспечивающих работу с типами значений с использованием семантики ссылок.</span><span class="sxs-lookup"><span data-stu-id="fd304-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="fd304-112">Неконечные именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="fd304-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="fd304-113">После именованных аргументов могут следовать позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="fd304-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="fd304-114">Начальные символы подчеркивания в числовых литералах</span><span class="sxs-lookup"><span data-stu-id="fd304-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="fd304-115">Перед любыми печатными знаками в числовых литералах теперь могут использоваться начальные знаки подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="fd304-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="fd304-116">Модификатор доступа `private protected`</span><span class="sxs-lookup"><span data-stu-id="fd304-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="fd304-117">Модификатор доступа `private protected` разрешает доступ для производных классов в одной сборке.</span><span class="sxs-lookup"><span data-stu-id="fd304-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="fd304-118">Семантика ссылок с типами значений</span><span class="sxs-lookup"><span data-stu-id="fd304-118">Reference semantics with value types</span></span>

<span data-ttu-id="fd304-119">Представленные в версии 7.2 языковые функции обеспечивают работу с типами значений с использованием семантики ссылок.</span><span class="sxs-lookup"><span data-stu-id="fd304-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="fd304-120">Благодаря этому удается повысить производительность за счет использования минимального числа операций копирования типов значений без выделения памяти в связи с применением ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="fd304-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="fd304-121">В число новых возможностей входят:</span><span class="sxs-lookup"><span data-stu-id="fd304-121">The features include:</span></span>

 - <span data-ttu-id="fd304-122">модификатор `in` для параметров, указывающий, что аргумент передается по ссылке, но не изменяется вызываемым методом;</span><span class="sxs-lookup"><span data-stu-id="fd304-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="fd304-123">модификатор `ref readonly` для возвращаемого значения метода, указывающий, что метод возвращает значение по ссылке, но не допускает операции записи в соответствующий объект;</span><span class="sxs-lookup"><span data-stu-id="fd304-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="fd304-124">объявление `readonly struct`, указывающее, что структура является неизменяемой и должна передаваться в методы члена как параметр `in`;</span><span class="sxs-lookup"><span data-stu-id="fd304-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="fd304-125">объявление `ref struct`, указывающее, что тип структуры обращается напрямую к управляемой памяти и всегда должен обрабатываться с выделением стека.</span><span class="sxs-lookup"><span data-stu-id="fd304-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="fd304-126">Дополнительные сведения об этих изменениях см. в разделе [Использование типов значений с семантикой ссылок](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="fd304-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="fd304-127">Неконечные именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="fd304-127">Non-trailing named arguments</span></span>

<span data-ttu-id="fd304-128">В вызовах методов после находящихся в правильной позиции именованных аргументов теперь можно использовать позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="fd304-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="fd304-129">Дополнительные сведения см. в разделе [Именованные и необязательные аргументы](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="fd304-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="fd304-130">Начальные символы подчеркивания в числовых литералах</span><span class="sxs-lookup"><span data-stu-id="fd304-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="fd304-131">Из-за того, как в версии C# 7.0 была реализована поддержка разделителей между знаками, в качестве первого знака в значении литерала нельзя было использовать символ `_`.</span><span class="sxs-lookup"><span data-stu-id="fd304-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="fd304-132">Теперь шестнадцатеричные и двоичные числовые литералы могут начинаться со знака `_`.</span><span class="sxs-lookup"><span data-stu-id="fd304-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="fd304-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="fd304-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="fd304-134">_private protected_ — модификатор доступа</span><span class="sxs-lookup"><span data-stu-id="fd304-134">_private protected_ access modifier</span></span>

<span data-ttu-id="fd304-135">Также представлен новый составной модификатор доступа `private protected`, указывающий, что доступ к члену может осуществляться содержащим классом или производными классами, которые объявлены в рамках одной сборки.</span><span class="sxs-lookup"><span data-stu-id="fd304-135">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="fd304-136">В отличие от модификатора `protected internal`, который разрешает доступ производным классам или классам из той же сборки, `private protected` ограничивает доступ только для производных классов, объявленных в рамках одной сборки.</span><span class="sxs-lookup"><span data-stu-id="fd304-136">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="fd304-137">Дополнительные сведения см. в разделе [Модификаторы доступа](../language-reference/keywords/access-modifiers.md) в справочнике по языку.</span><span class="sxs-lookup"><span data-stu-id="fd304-137">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
