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
ms.openlocfilehash: a274083ad2e518f8f29384e51d692bcf9a9cb61e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237250"
---
# <a name="bool-c-reference"></a><span data-ttu-id="7b7e5-102">bool (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7b7e5-102">bool (C# Reference)</span></span>

<span data-ttu-id="7b7e5-103">Ключевое слово `bool` является псевдонимом для <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7b7e5-104">Оно используется для объявления переменных для хранения логических значений [true](true-literal.md) и [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="7b7e5-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7b7e5-105">Если вам требуется логическая переменная, которая также может принимать значение `null`, используйте `bool?`.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="7b7e5-106">Дополнительные сведения см. в описании [типа bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="7b7e5-106">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="7b7e5-107">Литералы</span><span class="sxs-lookup"><span data-stu-id="7b7e5-107">Literals</span></span>

<span data-ttu-id="7b7e5-108">Логическое значение можно назначить переменной `bool`.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="7b7e5-109">Переменной `bool` также может назначить выражение, результатом которого является `bool`.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="7b7e5-110">Значением переменной `bool` по умолчанию является `false`.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="7b7e5-111">Значением переменной `bool?` по умолчанию является `null`.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="7b7e5-112">Преобразования</span><span class="sxs-lookup"><span data-stu-id="7b7e5-112">Conversions</span></span>

<span data-ttu-id="7b7e5-113">В C++ значение типа `bool` можно преобразовать в значение типа `int`; другими словами, `false` эквивалентно нулю, а `true` эквивалентно ненулевым значениям.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="7b7e5-114">В C# не предусмотрено преобразование между типом `bool` и другими типами.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="7b7e5-115">Например, следующий оператор `if` недопустим в C#:</span><span class="sxs-lookup"><span data-stu-id="7b7e5-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="7b7e5-116">Чтобы проверить переменную типа `int`, нужно явно сравнить ее со значением, например с нулем, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7b7e5-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="7b7e5-117">Пример</span><span class="sxs-lookup"><span data-stu-id="7b7e5-117">Example</span></span>

<span data-ttu-id="7b7e5-118">В этом примере символ вводится с клавиатуры, и программа проверяет, является ли введенный символ буквой.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="7b7e5-119">Если это буква, проверяется ее регистр.</span><span class="sxs-lookup"><span data-stu-id="7b7e5-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="7b7e5-120">Эти проверки выполняются с использованием <xref:System.Char.IsLetter%2A> и <xref:System.Char.IsLower%2A>, которые возвращают значение типа `bool`:</span><span class="sxs-lookup"><span data-stu-id="7b7e5-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="7b7e5-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7b7e5-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7b7e5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7b7e5-122">See also</span></span>

- [<span data-ttu-id="7b7e5-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7b7e5-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7b7e5-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7b7e5-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7b7e5-125">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="7b7e5-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="7b7e5-126">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="7b7e5-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="7b7e5-127">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="7b7e5-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="7b7e5-128">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="7b7e5-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="7b7e5-129">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="7b7e5-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  