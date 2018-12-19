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
ms.openlocfilehash: 6acb40117c4f59deb084965cb3db9e4a96f7f61a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242351"
---
# <a name="char-c-reference"></a><span data-ttu-id="ff8d0-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ff8d0-102">char (C# Reference)</span></span>

<span data-ttu-id="ff8d0-103">Ключевое слово `char` используется для объявления экземпляра структуры <xref:System.Char?displayProperty=nameWithType>, используемой .NET Framework для представления символа Юникода.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="ff8d0-104">Значение объекта `Char` представляет собой 16-разрядное числовое (порядковое) значение.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="ff8d0-105">Символы в кодировке Юникода используются для представления большинства письменных языков в мире.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="ff8d0-106">Тип</span><span class="sxs-lookup"><span data-stu-id="ff8d0-106">Type</span></span>|<span data-ttu-id="ff8d0-107">Диапазон</span><span class="sxs-lookup"><span data-stu-id="ff8d0-107">Range</span></span>|<span data-ttu-id="ff8d0-108">Размер</span><span class="sxs-lookup"><span data-stu-id="ff8d0-108">Size</span></span>|<span data-ttu-id="ff8d0-109">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="ff8d0-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="ff8d0-110">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="ff8d0-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="ff8d0-111">Символ Юникода (16-разрядный)</span><span class="sxs-lookup"><span data-stu-id="ff8d0-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="ff8d0-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="ff8d0-112">Literals</span></span>

<span data-ttu-id="ff8d0-113">Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="ff8d0-114">Также можно выполнить приведение целочисленных кодов символов.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="ff8d0-115">В следующем примере четыре переменные `char` инициализируются с помощью одного символа `X`:</span><span class="sxs-lookup"><span data-stu-id="ff8d0-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="ff8d0-116">Преобразования</span><span class="sxs-lookup"><span data-stu-id="ff8d0-116">Conversions</span></span>

<span data-ttu-id="ff8d0-117">Тип `char` может быть неявно преобразован в тип [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="ff8d0-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="ff8d0-118">Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="ff8d0-119">Тип <xref:System.Char?displayProperty=nameWithType> предоставляет несколько статических методов для работы со значениями `char`.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ff8d0-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ff8d0-120">C# language specification</span></span>  

<span data-ttu-id="ff8d0-121">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff8d0-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="ff8d0-122">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="ff8d0-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff8d0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ff8d0-123">See also</span></span>

- <xref:System.Char>  
- [<span data-ttu-id="ff8d0-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ff8d0-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ff8d0-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ff8d0-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ff8d0-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ff8d0-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ff8d0-127">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="ff8d0-127">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="ff8d0-128">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="ff8d0-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="ff8d0-129">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="ff8d0-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="ff8d0-130">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="ff8d0-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [<span data-ttu-id="ff8d0-131">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="ff8d0-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
- [<span data-ttu-id="ff8d0-132">Строки</span><span class="sxs-lookup"><span data-stu-id="ff8d0-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)