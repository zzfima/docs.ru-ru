---
title: Ключевое слово char — справочник по C#
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771801"
---
# <a name="char-c-reference"></a><span data-ttu-id="c5fa5-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c5fa5-102">char (C# reference)</span></span>

<span data-ttu-id="c5fa5-103">Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде:</span><span class="sxs-lookup"><span data-stu-id="c5fa5-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character:</span></span>

|<span data-ttu-id="c5fa5-104">Тип</span><span class="sxs-lookup"><span data-stu-id="c5fa5-104">Type</span></span>|<span data-ttu-id="c5fa5-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="c5fa5-105">Range</span></span>|<span data-ttu-id="c5fa5-106">Размер</span><span class="sxs-lookup"><span data-stu-id="c5fa5-106">Size</span></span>|<span data-ttu-id="c5fa5-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="c5fa5-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="c5fa5-108">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="c5fa5-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="c5fa5-109">16 разрядов</span><span class="sxs-lookup"><span data-stu-id="c5fa5-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="c5fa5-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="c5fa5-110">Literals</span></span>

<span data-ttu-id="c5fa5-111">Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода.</span><span class="sxs-lookup"><span data-stu-id="c5fa5-111">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="c5fa5-112">Можно также привести целочисленный код символа к соответствующему значению `char`.</span><span class="sxs-lookup"><span data-stu-id="c5fa5-112">You can also cast an integral character code into the corresponding `char` value.</span></span> <span data-ttu-id="c5fa5-113">В следующем примере четыре элемента массива `char` инициализируются с помощью одного символа `X`:</span><span class="sxs-lookup"><span data-stu-id="c5fa5-113">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="c5fa5-114">Преобразования</span><span class="sxs-lookup"><span data-stu-id="c5fa5-114">Conversions</span></span>

<span data-ttu-id="c5fa5-115">Тип `char` неявно преобразуется в следующие [целочисленные](../builtin-types/integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`.</span><span class="sxs-lookup"><span data-stu-id="c5fa5-115">The `char` type is implicitly convertible to the following [integral](../builtin-types/integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="c5fa5-116">Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](../builtin-types/floating-point-numeric-types.md): `float`, `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="c5fa5-116">It's also implicitly convertible to the built-in [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="c5fa5-117">Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.</span><span class="sxs-lookup"><span data-stu-id="c5fa5-117">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="c5fa5-118">Неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="c5fa5-118">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="c5fa5-119">Но любой [целочисленный тип](../builtin-types/integral-numeric-types.md) или числовой тип [с плавающей запятой](../builtin-types/floating-point-numeric-types.md) явно преобразуется в `char`.</span><span class="sxs-lookup"><span data-stu-id="c5fa5-119">However, any [integral](../builtin-types/integral-numeric-types.md) or [floating-point](../builtin-types/floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c5fa5-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c5fa5-120">C# language specification</span></span>

<span data-ttu-id="c5fa5-121">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c5fa5-121">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c5fa5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c5fa5-122">See also</span></span>

- [<span data-ttu-id="c5fa5-123">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c5fa5-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c5fa5-124">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="c5fa5-124">C# keywords</span></span>](./index.md)
- [<span data-ttu-id="c5fa5-125">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="c5fa5-125">Built-in types table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="c5fa5-126">Строки</span><span class="sxs-lookup"><span data-stu-id="c5fa5-126">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
