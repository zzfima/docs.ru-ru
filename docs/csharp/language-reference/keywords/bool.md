---
title: Ключевое слово bool (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 2041182dffa0330ea601b30e047c0b09731618f2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042404"
---
# <a name="bool-c-reference"></a><span data-ttu-id="07357-102">bool (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="07357-102">bool (C# Reference)</span></span>

<span data-ttu-id="07357-103">Ключевое слово `bool` является псевдонимом для <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="07357-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="07357-104">Оно используется для объявления переменных для хранения логических значений, [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="07357-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>

> [!NOTE]
> <span data-ttu-id="07357-105">Если вам требуется логическая переменная, которая также может принимать значение `null`, используйте `bool?`.</span><span class="sxs-lookup"><span data-stu-id="07357-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="07357-106">Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).</span><span class="sxs-lookup"><span data-stu-id="07357-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>

## <a name="literals"></a><span data-ttu-id="07357-107">Литералы</span><span class="sxs-lookup"><span data-stu-id="07357-107">Literals</span></span>

<span data-ttu-id="07357-108">Логическое значение можно назначить переменной `bool`.</span><span class="sxs-lookup"><span data-stu-id="07357-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="07357-109">Переменной `bool` также может назначить выражение, результатом которого является `bool`.</span><span class="sxs-lookup"><span data-stu-id="07357-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="07357-110">Значением переменной `bool` по умолчанию является `false`.</span><span class="sxs-lookup"><span data-stu-id="07357-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="07357-111">Значением переменной `bool?` по умолчанию является `null`.</span><span class="sxs-lookup"><span data-stu-id="07357-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="07357-112">Преобразования</span><span class="sxs-lookup"><span data-stu-id="07357-112">Conversions</span></span>

<span data-ttu-id="07357-113">В C++ значение типа `bool` можно преобразовать в значение типа `int`; другими словами, `false` эквивалентно нулю, а `true` эквивалентно ненулевым значениям.</span><span class="sxs-lookup"><span data-stu-id="07357-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="07357-114">В C# не предусмотрено преобразование между типом `bool` и другими типами.</span><span class="sxs-lookup"><span data-stu-id="07357-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="07357-115">Например, следующий оператор `if` недопустим в C#:</span><span class="sxs-lookup"><span data-stu-id="07357-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="07357-116">Чтобы проверить переменную типа `int`, нужно явно сравнить ее со значением, например с нулем, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07357-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="07357-117">Пример</span><span class="sxs-lookup"><span data-stu-id="07357-117">Example</span></span>

<span data-ttu-id="07357-118">В этом примере символ вводится с клавиатуры, и программа проверяет, является ли введенный символ буквой.</span><span class="sxs-lookup"><span data-stu-id="07357-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="07357-119">Если это буква, проверяется ее регистр.</span><span class="sxs-lookup"><span data-stu-id="07357-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="07357-120">Эти проверки выполняются с использованием <xref:System.Char.IsLetter%2A> и <xref:System.Char.IsLower%2A>, которые возвращают значение типа `bool`:</span><span class="sxs-lookup"><span data-stu-id="07357-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="07357-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="07357-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="07357-122">См. также</span><span class="sxs-lookup"><span data-stu-id="07357-122">See also</span></span>

- [<span data-ttu-id="07357-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="07357-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="07357-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="07357-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="07357-125">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="07357-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="07357-126">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="07357-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="07357-127">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="07357-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="07357-128">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="07357-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="07357-129">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="07357-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  