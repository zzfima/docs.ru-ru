---
title: Тип char. Справочник по C#
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: c4e29e6437edfe549b36a04a2050f63caa0d3d2a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846526"
---
# <a name="char-c-reference"></a><span data-ttu-id="18801-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="18801-102">char (C# reference)</span></span>

<span data-ttu-id="18801-103">Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="18801-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="18801-104">Type</span><span class="sxs-lookup"><span data-stu-id="18801-104">Type</span></span>|<span data-ttu-id="18801-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="18801-105">Range</span></span>|<span data-ttu-id="18801-106">Размер</span><span class="sxs-lookup"><span data-stu-id="18801-106">Size</span></span>|<span data-ttu-id="18801-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="18801-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="18801-108">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="18801-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="18801-109">16 разрядов</span><span class="sxs-lookup"><span data-stu-id="18801-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="18801-110">Значение по умолчанию для типа `char` — `\0`, то есть U+0000.</span><span class="sxs-lookup"><span data-stu-id="18801-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="18801-111">Тип [string](reference-types.md#the-string-type) представляет текст как последовательность значений `char`.</span><span class="sxs-lookup"><span data-stu-id="18801-111">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="18801-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="18801-112">Literals</span></span>

<span data-ttu-id="18801-113">Значение `char` можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="18801-113">You can specify a `char` value with:</span></span>

- <span data-ttu-id="18801-114">символьный литерал;</span><span class="sxs-lookup"><span data-stu-id="18801-114">a character literal.</span></span>
- <span data-ttu-id="18801-115">escape-последовательность Юникода, то есть символы `\u`, за которыми следует шестнадцатеричное представление кода символа из четырех символов;</span><span class="sxs-lookup"><span data-stu-id="18801-115">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="18801-116">шестнадцатеричная escape-последовательность, то есть символы `\x`, за которыми следует шестнадцатеричное представление кода символа.</span><span class="sxs-lookup"><span data-stu-id="18801-116">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="18801-117">Как показано в предыдущем примере, можно также привести значение кода символа к соответствующему значению `char`.</span><span class="sxs-lookup"><span data-stu-id="18801-117">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="18801-118">В случае escape-последовательности Юникода необходимо указать все четыре шестнадцатеричные цифры.</span><span class="sxs-lookup"><span data-stu-id="18801-118">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="18801-119">То есть `\u006A` — допустимая escape-последовательность, а `\u06A` и `\u6A` нет.</span><span class="sxs-lookup"><span data-stu-id="18801-119">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="18801-120">В случае шестнадцатеричной escape-последовательности начальные нули можно опустить.</span><span class="sxs-lookup"><span data-stu-id="18801-120">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="18801-121">То есть `\x006A`, `\x06A` и `\x6A` — допустимые escape-последовательности, соответствующие одному символу.</span><span class="sxs-lookup"><span data-stu-id="18801-121">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="18801-122">Преобразования</span><span class="sxs-lookup"><span data-stu-id="18801-122">Conversions</span></span>

<span data-ttu-id="18801-123">Тип `char` неявно преобразуется в следующие [целочисленные](integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`.</span><span class="sxs-lookup"><span data-stu-id="18801-123">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="18801-124">Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](floating-point-numeric-types.md): `float`, `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="18801-124">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="18801-125">Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.</span><span class="sxs-lookup"><span data-stu-id="18801-125">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="18801-126">Неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="18801-126">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="18801-127">Но любой [целочисленный тип](integral-numeric-types.md) или числовой тип [с плавающей запятой](floating-point-numeric-types.md) явно преобразуется в `char`.</span><span class="sxs-lookup"><span data-stu-id="18801-127">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="18801-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="18801-128">C# language specification</span></span>

<span data-ttu-id="18801-129">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="18801-129">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18801-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="18801-130">See also</span></span>

- [<span data-ttu-id="18801-131">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="18801-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="18801-132">Типы значений</span><span class="sxs-lookup"><span data-stu-id="18801-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="18801-133">Строки</span><span class="sxs-lookup"><span data-stu-id="18801-133">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
