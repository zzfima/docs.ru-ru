---
title: "Новые возможности C# 7.2"
description: "Общие сведения о новых функциях в C# 7.2."
keywords: "C# конструкции языка 7.2 2017 г. Visual Studio"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="c6750-104">Новые возможности C# 7.2</span><span class="sxs-lookup"><span data-stu-id="c6750-104">What's new in C# 7.2</span></span>

<span data-ttu-id="c6750-105">7.2 C# — другой выпуск точки, который добавляет ряд полезных функций.</span><span class="sxs-lookup"><span data-stu-id="c6750-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="c6750-106">Один темы в этом выпуске более эффективно работает с типами значений, чтобы избежать ненужных копий, а также выделения.</span><span class="sxs-lookup"><span data-stu-id="c6750-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="c6750-107">Оставшиеся компоненты — это маленькие, хорошо бы иметь функции.</span><span class="sxs-lookup"><span data-stu-id="c6750-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="c6750-108">7.2 C# использует [Выбор версии языка](csharp-7-1.md#language-version-selection) элемента конфигурации для выбора версии языка компилятора.</span><span class="sxs-lookup"><span data-stu-id="c6750-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="c6750-109">Ниже перечислены новые возможности языка в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="c6750-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="c6750-110">Семантику ссылки с типами значений</span><span class="sxs-lookup"><span data-stu-id="c6750-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="c6750-111">Сочетание синтаксис усовершенствования, позволяющие работа с типами значений с помощью семантики ссылок.</span><span class="sxs-lookup"><span data-stu-id="c6750-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="c6750-112">Не конечные именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="c6750-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="c6750-113">Именованные аргументы могут следовать позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="c6750-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="c6750-114">В числовых литералах подчеркивания</span><span class="sxs-lookup"><span data-stu-id="c6750-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="c6750-115">Числовые литералы теперь может иметь символами подчеркивания в начале перед любой печатаемых знаков.</span><span class="sxs-lookup"><span data-stu-id="c6750-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="c6750-116">`private protected`модификатор доступа</span><span class="sxs-lookup"><span data-stu-id="c6750-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="c6750-117">`private protected` Модификатор доступа разрешает доступ для производных классов в той же сборке.</span><span class="sxs-lookup"><span data-stu-id="c6750-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="c6750-118">Семантику ссылки с типами значений</span><span class="sxs-lookup"><span data-stu-id="c6750-118">Reference semantics with value types</span></span>

<span data-ttu-id="c6750-119">Функции языка, представленные в 7.2 позволяют работать с типами значений при работе с семантикой ссылок.</span><span class="sxs-lookup"><span data-stu-id="c6750-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="c6750-120">Они предназначены для повышения производительности путем минимизации копирование типы значений без увеличения выделения памяти, связанные с использованием ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="c6750-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="c6750-121">Доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="c6750-121">The features include:</span></span>

 - <span data-ttu-id="c6750-122">`in` Модификатор для параметров, чтобы указать, что аргумент передается по ссылке, но не изменяет вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="c6750-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="c6750-123">`ref readonly` Модификатор возвращает метод, чтобы указать, что метод возвращает его значение по ссылке, но не допускает запись на этот объект.</span><span class="sxs-lookup"><span data-stu-id="c6750-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="c6750-124">`readonly struct` Объявление, чтобы указать, что структура является неизменяемым и должен передаваться как `in` параметра для методов-членов.</span><span class="sxs-lookup"><span data-stu-id="c6750-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="c6750-125">`ref struct` Объявление, указывающего на тип структуры напрямую обращается к управляемой памяти должен всегда быть стека выделен.</span><span class="sxs-lookup"><span data-stu-id="c6750-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="c6750-126">Можно прочитать дополнительные сведения о всех этих изменений в [использование типов значения с семантикой ссылок](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="c6750-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="c6750-127">Не конечные именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="c6750-127">Non-trailing named arguments</span></span>

<span data-ttu-id="c6750-128">Вызовы методов теперь можно использовать именованные аргументы, предшествующие позиционные аргументы те аргументы, которые в соответствующие позиции.</span><span class="sxs-lookup"><span data-stu-id="c6750-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="c6750-129">Дополнительные сведения см. [именованные и необязательные аргументы](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="c6750-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="c6750-130">В числовых литералах подчеркивания</span><span class="sxs-lookup"><span data-stu-id="c6750-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="c6750-131">Реализация поддержки разделители между цифрами в C# 7.0 не допускают `_` на первый символ, литеральное значение.</span><span class="sxs-lookup"><span data-stu-id="c6750-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="c6750-132">Hex и двоичные числовые литералы теперь может начинаться с `_`.</span><span class="sxs-lookup"><span data-stu-id="c6750-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="c6750-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="c6750-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="c6750-134">Наконец, новый модификатор комплексной доступа: `private protected` указывает, что член может осуществляться производными классами, которые объявлены в той же сборке.</span><span class="sxs-lookup"><span data-stu-id="c6750-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="c6750-135">Хотя `protected internal` позволяет получать доступ производные классы или классы, которые находятся в той же сборке `private protected` ограничивает доступ к производные типы, объявленные в той же сборке.</span><span class="sxs-lookup"><span data-stu-id="c6750-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="c6750-136">Дополнительные сведения см. [модификаторы доступа](../language-reference/keywords/access-modifiers.md) справочника по языку.</span><span class="sxs-lookup"><span data-stu-id="c6750-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
