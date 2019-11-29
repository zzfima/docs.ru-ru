---
title: Тип char. Справочник по C#
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 3b2eec4f0e17aa329fe3865fb3ef453ee030c6a7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450844"
---
# <a name="char-c-reference"></a><span data-ttu-id="5f164-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5f164-102">char (C# reference)</span></span>

<span data-ttu-id="5f164-103">Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="5f164-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="5f164-104">Тип</span><span class="sxs-lookup"><span data-stu-id="5f164-104">Type</span></span>|<span data-ttu-id="5f164-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="5f164-105">Range</span></span>|<span data-ttu-id="5f164-106">Размер</span><span class="sxs-lookup"><span data-stu-id="5f164-106">Size</span></span>|<span data-ttu-id="5f164-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="5f164-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="5f164-108">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="5f164-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="5f164-109">16 разрядов</span><span class="sxs-lookup"><span data-stu-id="5f164-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="5f164-110">Тип [string](reference-types.md#the-string-type) представляет текст как последовательность значений `char`.</span><span class="sxs-lookup"><span data-stu-id="5f164-110">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="5f164-111">Литералы</span><span class="sxs-lookup"><span data-stu-id="5f164-111">Literals</span></span>

<span data-ttu-id="5f164-112">Значение `char` можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5f164-112">You can specify a `char` value with:</span></span>

- <span data-ttu-id="5f164-113">символьный литерал;</span><span class="sxs-lookup"><span data-stu-id="5f164-113">a character literal.</span></span>
- <span data-ttu-id="5f164-114">escape-последовательность Юникода, то есть символы `\u`, за которыми следует шестнадцатеричное представление кода символа из четырех символов;</span><span class="sxs-lookup"><span data-stu-id="5f164-114">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="5f164-115">шестнадцатеричная escape-последовательность, то есть символы `\x`, за которыми следует шестнадцатеричное представление кода символа.</span><span class="sxs-lookup"><span data-stu-id="5f164-115">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](~/samples/csharp/language-reference/builtin-types/CharType.cs#Literals)]

<span data-ttu-id="5f164-116">Как показано в предыдущем примере, можно также привести значение кода символа к соответствующему значению `char`.</span><span class="sxs-lookup"><span data-stu-id="5f164-116">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="5f164-117">В случае escape-последовательности Юникода необходимо указать все четыре шестнадцатеричные цифры.</span><span class="sxs-lookup"><span data-stu-id="5f164-117">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="5f164-118">То есть `\u006A` — допустимая escape-последовательность, а `\u06A` и `\u6A` нет.</span><span class="sxs-lookup"><span data-stu-id="5f164-118">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="5f164-119">В случае шестнадцатеричной escape-последовательности начальные нули можно опустить.</span><span class="sxs-lookup"><span data-stu-id="5f164-119">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="5f164-120">То есть `\x006A`, `\x06A` и `\x6A` — допустимые escape-последовательности, соответствующие одному символу.</span><span class="sxs-lookup"><span data-stu-id="5f164-120">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="5f164-121">Преобразования</span><span class="sxs-lookup"><span data-stu-id="5f164-121">Conversions</span></span>

<span data-ttu-id="5f164-122">Тип `char` неявно преобразуется в следующие [целочисленные](integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`.</span><span class="sxs-lookup"><span data-stu-id="5f164-122">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="5f164-123">Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](floating-point-numeric-types.md): `float`, `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="5f164-123">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="5f164-124">Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.</span><span class="sxs-lookup"><span data-stu-id="5f164-124">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="5f164-125">Неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="5f164-125">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="5f164-126">Но любой [целочисленный тип](integral-numeric-types.md) или числовой тип [с плавающей запятой](floating-point-numeric-types.md) явно преобразуется в `char`.</span><span class="sxs-lookup"><span data-stu-id="5f164-126">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5f164-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5f164-127">C# language specification</span></span>

<span data-ttu-id="5f164-128">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5f164-128">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f164-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5f164-129">See also</span></span>

- [<span data-ttu-id="5f164-130">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5f164-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5f164-131">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="5f164-131">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="5f164-132">Строки</span><span class="sxs-lookup"><span data-stu-id="5f164-132">Strings</span></span>](../../programming-guide/strings/index.md)
