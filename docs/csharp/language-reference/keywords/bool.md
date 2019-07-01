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
ms.openlocfilehash: a6aae34433ee6f5d141d95f0c434af1825e9bf4b
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424439"
---
# <a name="bool-c-reference"></a><span data-ttu-id="6bcdb-102">bool (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6bcdb-102">bool (C# Reference)</span></span>

<span data-ttu-id="6bcdb-103">Ключевое слово `bool` является псевдонимом для <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6bcdb-104">Оно используется для объявления переменных для хранения логических значений [true](true-literal.md) и [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="6bcdb-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6bcdb-105">Используйте тип `bool?`, если вам нужно использовать трехзначную логику, например при работе с базами данных, которые поддерживают трехзначный логический тип.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="6bcdb-106">Для операндов `bool?` предопределенные операторы `&` и `|` поддерживают троичную логику.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="6bcdb-107">См. подробнее о [логических операторах, поддерживающих значение NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6bcdb-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="6bcdb-108">Литералы</span><span class="sxs-lookup"><span data-stu-id="6bcdb-108">Literals</span></span>

<span data-ttu-id="6bcdb-109">Логическое значение можно назначить переменной `bool`.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="6bcdb-110">Переменной `bool` также может назначить выражение, результатом которого является `bool`.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="6bcdb-111">Значением переменной `bool` по умолчанию является `false`.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="6bcdb-112">Значением переменной `bool?` по умолчанию является `null`.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="6bcdb-113">Преобразования</span><span class="sxs-lookup"><span data-stu-id="6bcdb-113">Conversions</span></span>

<span data-ttu-id="6bcdb-114">В C++ значение типа `bool` можно преобразовать в значение типа `int`; другими словами, `false` эквивалентно нулю, а `true` эквивалентно ненулевым значениям.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="6bcdb-115">В C# не предусмотрено преобразование между типом `bool` и другими типами.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="6bcdb-116">Например, следующий оператор `if` недопустим в C#:</span><span class="sxs-lookup"><span data-stu-id="6bcdb-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="6bcdb-117">Чтобы проверить переменную типа `int`, нужно явно сравнить ее со значением, например с нулем, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6bcdb-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="6bcdb-118">Пример</span><span class="sxs-lookup"><span data-stu-id="6bcdb-118">Example</span></span>

<span data-ttu-id="6bcdb-119">В этом примере символ вводится с клавиатуры, и программа проверяет, является ли введенный символ буквой.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="6bcdb-120">Если это буква, проверяется ее регистр.</span><span class="sxs-lookup"><span data-stu-id="6bcdb-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="6bcdb-121">Эти проверки выполняются с использованием <xref:System.Char.IsLetter%2A> и <xref:System.Char.IsLower%2A>, которые возвращают значение типа `bool`:</span><span class="sxs-lookup"><span data-stu-id="6bcdb-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="6bcdb-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6bcdb-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6bcdb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6bcdb-123">See also</span></span>

- [<span data-ttu-id="6bcdb-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6bcdb-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="6bcdb-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6bcdb-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6bcdb-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6bcdb-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="6bcdb-127">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="6bcdb-127">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="6bcdb-128">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="6bcdb-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="6bcdb-129">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="6bcdb-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="6bcdb-130">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="6bcdb-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
