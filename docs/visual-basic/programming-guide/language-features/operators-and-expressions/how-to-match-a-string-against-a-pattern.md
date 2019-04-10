---
title: Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)
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
ms.openlocfilehash: c14aa35ce15549ad9eccabe2330a7c43b6795140
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316275"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="9473b-102">Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9473b-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="9473b-103">Если вы хотите определить выражение [строковый тип данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) удовлетворяет шаблону, можно использовать [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9473b-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 `Like` <span data-ttu-id="9473b-104">принимает два операнда.</span><span class="sxs-lookup"><span data-stu-id="9473b-104">takes two operands.</span></span> <span data-ttu-id="9473b-105">Левый операнд представляет собой строковое выражение, а правый — строка, содержащая шаблон, используемый для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="9473b-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> `Like` <span data-ttu-id="9473b-106">Возвращает `Boolean` значение, указывающее, удовлетворяет ли строковое выражение шаблону.</span><span class="sxs-lookup"><span data-stu-id="9473b-106">returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="9473b-107">Можно сопоставить каждый символ в строковом выражении с определенный символ, символом-шаблоном, список символ или диапазон символов.</span><span class="sxs-lookup"><span data-stu-id="9473b-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="9473b-108">Позиции в строке шаблона спецификации соответствуют позиции символов для сопоставления строковым выражением.</span><span class="sxs-lookup"><span data-stu-id="9473b-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="9473b-109">Сравнение символа в строковом выражении с указанным символом</span><span class="sxs-lookup"><span data-stu-id="9473b-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="9473b-110">Поместите указанный символ непосредственно в строку шаблона.</span><span class="sxs-lookup"><span data-stu-id="9473b-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="9473b-111">Некоторые специальные символы должны заключаться в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="9473b-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="9473b-112">Дополнительные сведения см. в разделе [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9473b-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="9473b-113">В следующем примере производится проверка ли `myString` состоит ровно из символов `H`.</span><span class="sxs-lookup"><span data-stu-id="9473b-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="9473b-114">Сравнение символа в строковом выражении с символом-шаблоном</span><span class="sxs-lookup"><span data-stu-id="9473b-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="9473b-115">Поместить знак вопроса (`?`) в строке шаблона.</span><span class="sxs-lookup"><span data-stu-id="9473b-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="9473b-116">Любой допустимый символ в этой позиции совпадение является успешным.</span><span class="sxs-lookup"><span data-stu-id="9473b-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="9473b-117">В следующем примере производится проверка ли `myString` состоит из символов `W` и любых значений между двумя символами.</span><span class="sxs-lookup"><span data-stu-id="9473b-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="9473b-118">Сравнение символа в строковом выражении в списке символов</span><span class="sxs-lookup"><span data-stu-id="9473b-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="9473b-119">Поместите квадратные скобки (`[ ]`) в строке шаблона и внутри скобок укажите список символов.</span><span class="sxs-lookup"><span data-stu-id="9473b-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="9473b-120">Они не разделяют символы с запятыми или любых других разделителей.</span><span class="sxs-lookup"><span data-stu-id="9473b-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="9473b-121">Любому одиночному символу в списке совпадение является успешным.</span><span class="sxs-lookup"><span data-stu-id="9473b-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="9473b-122">В следующем примере производится проверка ли `myString` состоит из любой допустимый символ, за которым следует точно один из символов `A`, `C`, или `E`.</span><span class="sxs-lookup"><span data-stu-id="9473b-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     <span data-ttu-id="9473b-123">Обратите внимание на то, что при сравнении учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9473b-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="9473b-124">Сравнение символа в строковом выражении с диапазона символов</span><span class="sxs-lookup"><span data-stu-id="9473b-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="9473b-125">Поместите квадратные скобки (`[ ]`) в строку шаблона, а в скобках укажите символы минимальный и максимальный диапазон, разделенных дефисом (`–`).</span><span class="sxs-lookup"><span data-stu-id="9473b-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="9473b-126">Любому одиночному символу в диапазоне совпадение является успешным.</span><span class="sxs-lookup"><span data-stu-id="9473b-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="9473b-127">В следующем примере производится проверка ли `myString` состоит из символов `num` с одного из символов `i`, `j`, `k`, `l`, `m`, или `n`.</span><span class="sxs-lookup"><span data-stu-id="9473b-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     <span data-ttu-id="9473b-128">Обратите внимание на то, что при сравнении учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9473b-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="9473b-129">Сравнение пустых строк</span><span class="sxs-lookup"><span data-stu-id="9473b-129">Matching Empty Strings</span></span>  
 `Like` <span data-ttu-id="9473b-130">рассматривает последовательность `[]` как строка нулевой длины (`""`).</span><span class="sxs-lookup"><span data-stu-id="9473b-130">treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="9473b-131">Можно использовать `[]` для тестирования ли выражение всю строку пуст, но его нельзя использовать для проверки, если определенное положение в строковое выражение является пустым.</span><span class="sxs-lookup"><span data-stu-id="9473b-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="9473b-132">Если пустая позиция является один из параметров необходимо проверить, можно использовать `Like` более одного раза.</span><span class="sxs-lookup"><span data-stu-id="9473b-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="9473b-133">Сравнение символа в строковом выражении в списке символов или ни один знак</span><span class="sxs-lookup"><span data-stu-id="9473b-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1. <span data-ttu-id="9473b-134">Вызовите `Like` оператор дважды для одного строкового выражения и подключение двух вызовов с помощью либо [или оператор](../../../../visual-basic/language-reference/operators/or-operator.md) или [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9473b-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2. <span data-ttu-id="9473b-135">В строке шаблона для первого `Like` предложения, включите список символов, заключенные в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="9473b-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3. <span data-ttu-id="9473b-136">В строке шаблона для второго `Like` предложение, не следует помещать любой символ в позиции в вопросе.</span><span class="sxs-lookup"><span data-stu-id="9473b-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="9473b-137">В следующем примере проверяется номер телефона из семи цифр `phoneNum` ровно три цифры, а затем пробел, дефис (`–`), точку (`.`), или ни один знак, за которым следует ровно четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="9473b-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="9473b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="9473b-138">See also</span></span>

- [<span data-ttu-id="9473b-139">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="9473b-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="9473b-140">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="9473b-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="9473b-141">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="9473b-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="9473b-142">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="9473b-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
