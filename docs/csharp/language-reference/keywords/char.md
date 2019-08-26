---
title: Справочник по C#. Ключевое слово char
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 754c04bfc3b4090906420d55d55e51606b72f187
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605947"
---
# <a name="char-c-reference"></a><span data-ttu-id="f9445-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f9445-102">char (C# Reference)</span></span>

<span data-ttu-id="f9445-103">Ключевое слово `char` используется для объявления экземпляра структуры <xref:System.Char?displayProperty=nameWithType>, используемой .NET Framework для представления символа Юникода.</span><span class="sxs-lookup"><span data-stu-id="f9445-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="f9445-104">Значение объекта `Char` представляет собой 16-разрядное числовое (порядковое) значение.</span><span class="sxs-lookup"><span data-stu-id="f9445-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="f9445-105">Символы в кодировке Юникода используются для представления большинства письменных языков в мире.</span><span class="sxs-lookup"><span data-stu-id="f9445-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="f9445-106">Тип</span><span class="sxs-lookup"><span data-stu-id="f9445-106">Type</span></span>|<span data-ttu-id="f9445-107">Диапазон</span><span class="sxs-lookup"><span data-stu-id="f9445-107">Range</span></span>|<span data-ttu-id="f9445-108">Размер</span><span class="sxs-lookup"><span data-stu-id="f9445-108">Size</span></span>|<span data-ttu-id="f9445-109">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="f9445-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="f9445-110">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="f9445-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="f9445-111">Символ Юникода (16-разрядный)</span><span class="sxs-lookup"><span data-stu-id="f9445-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="f9445-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="f9445-112">Literals</span></span>

<span data-ttu-id="f9445-113">Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода.</span><span class="sxs-lookup"><span data-stu-id="f9445-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="f9445-114">Также можно выполнить приведение целочисленных кодов символов.</span><span class="sxs-lookup"><span data-stu-id="f9445-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="f9445-115">В следующем примере четыре переменные `char` инициализируются с помощью одного символа `X`:</span><span class="sxs-lookup"><span data-stu-id="f9445-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="f9445-116">Преобразования</span><span class="sxs-lookup"><span data-stu-id="f9445-116">Conversions</span></span>

<span data-ttu-id="f9445-117">Тип `char` может быть неявно преобразован в тип [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) или [decimal](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="f9445-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="f9445-118">Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="f9445-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="f9445-119">Тип <xref:System.Char?displayProperty=nameWithType> предоставляет несколько статических методов для работы со значениями `char`.</span><span class="sxs-lookup"><span data-stu-id="f9445-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f9445-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f9445-120">C# language specification</span></span>  

<span data-ttu-id="f9445-121">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9445-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="f9445-122">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="f9445-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9445-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f9445-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="f9445-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f9445-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f9445-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f9445-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f9445-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f9445-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="f9445-127">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="f9445-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="f9445-128">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="f9445-128">Built-In Types Table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="f9445-129">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f9445-129">Implicit Numeric Conversions Table</span></span>](./implicit-numeric-conversions-table.md)
- [<span data-ttu-id="f9445-130">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="f9445-130">Explicit Numeric Conversions Table</span></span>](./explicit-numeric-conversions-table.md)
- [<span data-ttu-id="f9445-131">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="f9445-131">Nullable Types</span></span>](../../programming-guide/nullable-types/index.md)
- [<span data-ttu-id="f9445-132">Строки</span><span class="sxs-lookup"><span data-stu-id="f9445-132">Strings</span></span>](../../programming-guide/strings/index.md)
