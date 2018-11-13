---
title: Ключевое слово char (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 4d4e4719eabf7dbe31a59cc2e1e3d3d9019f080d
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "43742030"
---
# <a name="char-c-reference"></a><span data-ttu-id="0b11c-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0b11c-102">char (C# Reference)</span></span>

<span data-ttu-id="0b11c-103">Ключевое слово `char` используется для объявления экземпляра структуры <xref:System.Char?displayProperty=nameWithType>, используемой .NET Framework для представления символа Юникода.</span><span class="sxs-lookup"><span data-stu-id="0b11c-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="0b11c-104">Значение объекта `Char` представляет собой 16-разрядное числовое (порядковое) значение.</span><span class="sxs-lookup"><span data-stu-id="0b11c-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="0b11c-105">Символы в кодировке Юникода используются для представления большинства письменных языков в мире.</span><span class="sxs-lookup"><span data-stu-id="0b11c-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="0b11c-106">Тип</span><span class="sxs-lookup"><span data-stu-id="0b11c-106">Type</span></span>|<span data-ttu-id="0b11c-107">Диапазон</span><span class="sxs-lookup"><span data-stu-id="0b11c-107">Range</span></span>|<span data-ttu-id="0b11c-108">Размер</span><span class="sxs-lookup"><span data-stu-id="0b11c-108">Size</span></span>|<span data-ttu-id="0b11c-109">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="0b11c-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="0b11c-110">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="0b11c-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="0b11c-111">Символ Юникода (16-разрядный)</span><span class="sxs-lookup"><span data-stu-id="0b11c-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="0b11c-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="0b11c-112">Literals</span></span>

<span data-ttu-id="0b11c-113">Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода.</span><span class="sxs-lookup"><span data-stu-id="0b11c-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="0b11c-114">Также можно выполнить приведение целочисленных кодов символов.</span><span class="sxs-lookup"><span data-stu-id="0b11c-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="0b11c-115">В следующем примере четыре переменные `char` инициализируются с помощью одного символа `X`:</span><span class="sxs-lookup"><span data-stu-id="0b11c-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="0b11c-116">Преобразования</span><span class="sxs-lookup"><span data-stu-id="0b11c-116">Conversions</span></span>

<span data-ttu-id="0b11c-117">Тип `char` может быть неявно преобразован в тип [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="0b11c-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="0b11c-118">Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="0b11c-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="0b11c-119">Тип <xref:System.Char?displayProperty=nameWithType> предоставляет несколько статических методов для работы со значениями `char`.</span><span class="sxs-lookup"><span data-stu-id="0b11c-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b11c-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0b11c-120">C# language specification</span></span>  

<span data-ttu-id="0b11c-121">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0b11c-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="0b11c-122">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="0b11c-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b11c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0b11c-123">See also</span></span>

- <xref:System.Char>  
- [<span data-ttu-id="0b11c-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0b11c-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0b11c-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0b11c-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0b11c-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0b11c-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="0b11c-127">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="0b11c-127">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="0b11c-128">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="0b11c-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="0b11c-129">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="0b11c-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="0b11c-130">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="0b11c-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [<span data-ttu-id="0b11c-131">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="0b11c-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
- [<span data-ttu-id="0b11c-132">Строки</span><span class="sxs-lookup"><span data-stu-id="0b11c-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)