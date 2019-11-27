---
title: Практическое руководство. Сравнение строки на соответствие с шаблоном
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: 49328a72c2cff78b8fe13ca73209d224495ad7a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343636"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="2b18c-102">Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b18c-102">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="2b18c-103">Если нужно выяснить, удовлетворяет ли выражение [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) шаблону, можно использовать [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2b18c-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="2b18c-104">`Like` принимает два операнда.</span><span class="sxs-lookup"><span data-stu-id="2b18c-104">`Like` takes two operands.</span></span> <span data-ttu-id="2b18c-105">Левый операнд является строковым выражением, а правый — строкой, содержащей шаблон, используемый для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2b18c-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="2b18c-106">`Like` возвращает значение типа `Boolean`, указывающее, удовлетворяет ли строковое выражение шаблону.</span><span class="sxs-lookup"><span data-stu-id="2b18c-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="2b18c-107">Каждый символ в строковом выражении можно сопоставить с конкретным символом, символом-шаблоном, списком символов или диапазоном символов.</span><span class="sxs-lookup"><span data-stu-id="2b18c-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="2b18c-108">Положения спецификаций в строке шаблона соответствуют позициям символов, которые должны быть сопоставлены в строковом выражении.</span><span class="sxs-lookup"><span data-stu-id="2b18c-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="2b18c-109">Сопоставление символа в строковом выражении с конкретным символом</span><span class="sxs-lookup"><span data-stu-id="2b18c-109">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="2b18c-110">Помещает конкретный символ непосредственно в строку шаблона.</span><span class="sxs-lookup"><span data-stu-id="2b18c-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="2b18c-111">Некоторые специальные символы должны быть заключены в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="2b18c-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="2b18c-112">Дополнительные сведения см. [в разделе Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2b18c-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="2b18c-113">В следующем примере проверяется, содержит ли `myString` ровно один символ `H`.</span><span class="sxs-lookup"><span data-stu-id="2b18c-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="2b18c-114">Сопоставление символа в строковом выражении с подстановочным знаком</span><span class="sxs-lookup"><span data-stu-id="2b18c-114">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="2b18c-115">Добавьте вопросительный знак (`?`) в строку шаблона.</span><span class="sxs-lookup"><span data-stu-id="2b18c-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="2b18c-116">Любой допустимый символ в этой позиции делает успешное совпадение.</span><span class="sxs-lookup"><span data-stu-id="2b18c-116">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="2b18c-117">В следующем примере проверяется, состоит ли `myString` из одного символа `W` за которым следует ровно два символа любого значения.</span><span class="sxs-lookup"><span data-stu-id="2b18c-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="2b18c-118">Сопоставление символа в строковом выражении со списком символов</span><span class="sxs-lookup"><span data-stu-id="2b18c-118">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="2b18c-119">Вставьте квадратные скобки (`[ ]`) в строку шаблона, а внутри квадратных скобок вставьте список символов.</span><span class="sxs-lookup"><span data-stu-id="2b18c-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="2b18c-120">Не разделяйте символы запятыми или любым другим разделителем.</span><span class="sxs-lookup"><span data-stu-id="2b18c-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="2b18c-121">Любой отдельный символ в списке успешно выполняет сопоставление.</span><span class="sxs-lookup"><span data-stu-id="2b18c-121">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="2b18c-122">В следующем примере проверяется, состоит ли `myString` из любого допустимого символа, за которым следует только один из символов `A`, `C`или `E`.</span><span class="sxs-lookup"><span data-stu-id="2b18c-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="2b18c-123">Обратите внимание, что в этом совпадении учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="2b18c-123">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="2b18c-124">Сопоставление символа в строковом выражении с диапазоном символов</span><span class="sxs-lookup"><span data-stu-id="2b18c-124">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="2b18c-125">Вставьте квадратные скобки (`[ ]`) в строку шаблона, а внутри квадратных скобок — наименьшие и максимальные символы в диапазоне, разделенные дефисом (`–`).</span><span class="sxs-lookup"><span data-stu-id="2b18c-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="2b18c-126">Любой отдельный символ в диапазоне выполняет успешное совпадение.</span><span class="sxs-lookup"><span data-stu-id="2b18c-126">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="2b18c-127">В следующем примере проверяется, состоит ли `myString` символов `num`, за которыми следует только один из символов `i`, `j`, `k`, `l`, `m`или `n`.</span><span class="sxs-lookup"><span data-stu-id="2b18c-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="2b18c-128">Обратите внимание, что в этом совпадении учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="2b18c-128">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="2b18c-129">Совпадающие пустые строки</span><span class="sxs-lookup"><span data-stu-id="2b18c-129">Matching Empty Strings</span></span>

<span data-ttu-id="2b18c-130">`Like` считает `[]` последовательности строкой нулевой длины (`""`).</span><span class="sxs-lookup"><span data-stu-id="2b18c-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="2b18c-131">Можно использовать `[]`, чтобы проверить, пусто ли строковое выражение, но нельзя использовать его для проверки того, что определенная позицией в строковом выражении пуста.</span><span class="sxs-lookup"><span data-stu-id="2b18c-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="2b18c-132">Если пустое расположение является одним из параметров, которые необходимо проверить, можно использовать `Like` несколько раз.</span><span class="sxs-lookup"><span data-stu-id="2b18c-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="2b18c-133">Сопоставление символа в строковом выражении со списком символов или без символа</span><span class="sxs-lookup"><span data-stu-id="2b18c-133">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="2b18c-134">Дважды вызовите оператор `Like` в одном и том же строковом выражении и соедините два вызова с помощью [оператора либо](../../../../visual-basic/language-reference/operators/or-operator.md) либо [оператора OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2b18c-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="2b18c-135">В строке шаблона для первого предложения `Like` включите список символов, заключенный в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="2b18c-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="2b18c-136">В строке шаблона для второго предложения `Like` не помещайте какой бы то ни было символа в рассматриваемой позиции.</span><span class="sxs-lookup"><span data-stu-id="2b18c-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="2b18c-137">В следующем примере проверяется номер телефона, состоящий из семи цифр, `phoneNum` только для трех цифр, за которыми следует пробел, дефис (`–`), точка (`.`) или символ, за которым следует только четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="2b18c-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="2b18c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="2b18c-138">See also</span></span>

- [<span data-ttu-id="2b18c-139">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="2b18c-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="2b18c-140">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="2b18c-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="2b18c-141">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="2b18c-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="2b18c-142">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="2b18c-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
