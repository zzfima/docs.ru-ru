---
title: Справочник по C#. Ключевое слово bool
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 880e8c0b733afbf5c09f543e06a5a4a858d2b456
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771850"
---
# <a name="bool-c-reference"></a><span data-ttu-id="801ef-102">bool (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="801ef-102">bool (C# Reference)</span></span>

<span data-ttu-id="801ef-103">Ключевое слово `bool` является псевдонимом для <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="801ef-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="801ef-104">Оно используется для объявления переменных для хранения логических значений [true](true-literal.md) и [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="801ef-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="801ef-105">Используйте тип `bool?`, если вам нужно использовать трехзначную логику, например при работе с базами данных, которые поддерживают трехзначный логический тип.</span><span class="sxs-lookup"><span data-stu-id="801ef-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="801ef-106">Для операндов `bool?` предопределенные операторы `&` и `|` поддерживают троичную логику.</span><span class="sxs-lookup"><span data-stu-id="801ef-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="801ef-107">См. подробнее о [логических операторах, поддерживающих значение NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="801ef-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="801ef-108">Литералы</span><span class="sxs-lookup"><span data-stu-id="801ef-108">Literals</span></span>

<span data-ttu-id="801ef-109">Логическое значение можно назначить переменной `bool`.</span><span class="sxs-lookup"><span data-stu-id="801ef-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="801ef-110">Переменной `bool` также может назначить выражение, результатом которого является `bool`.</span><span class="sxs-lookup"><span data-stu-id="801ef-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="801ef-111">Значением переменной `bool` по умолчанию является `false`.</span><span class="sxs-lookup"><span data-stu-id="801ef-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="801ef-112">Значением переменной `bool?` по умолчанию является `null`.</span><span class="sxs-lookup"><span data-stu-id="801ef-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="801ef-113">Преобразования</span><span class="sxs-lookup"><span data-stu-id="801ef-113">Conversions</span></span>

<span data-ttu-id="801ef-114">В C++ значение типа `bool` можно преобразовать в значение типа `int`; другими словами, `false` эквивалентно нулю, а `true` эквивалентно ненулевым значениям.</span><span class="sxs-lookup"><span data-stu-id="801ef-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="801ef-115">В C# не предусмотрено преобразование между типом `bool` и другими типами.</span><span class="sxs-lookup"><span data-stu-id="801ef-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="801ef-116">Например, следующий оператор `if` недопустим в C#:</span><span class="sxs-lookup"><span data-stu-id="801ef-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="801ef-117">Чтобы проверить переменную типа `int`, нужно явно сравнить ее со значением, например с нулем, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="801ef-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="801ef-118">Пример</span><span class="sxs-lookup"><span data-stu-id="801ef-118">Example</span></span>

<span data-ttu-id="801ef-119">В этом примере символ вводится с клавиатуры, и программа проверяет, является ли введенный символ буквой.</span><span class="sxs-lookup"><span data-stu-id="801ef-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="801ef-120">Если это буква, проверяется ее регистр.</span><span class="sxs-lookup"><span data-stu-id="801ef-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="801ef-121">Эти проверки выполняются с использованием <xref:System.Char.IsLetter%2A> и <xref:System.Char.IsLower%2A>, которые возвращают значение типа `bool`:</span><span class="sxs-lookup"><span data-stu-id="801ef-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="801ef-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="801ef-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="801ef-123">См. также</span><span class="sxs-lookup"><span data-stu-id="801ef-123">See also</span></span>

- [<span data-ttu-id="801ef-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="801ef-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="801ef-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="801ef-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="801ef-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="801ef-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="801ef-127">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="801ef-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="801ef-128">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="801ef-128">Built-In Types Table</span></span>](./built-in-types-table.md)
