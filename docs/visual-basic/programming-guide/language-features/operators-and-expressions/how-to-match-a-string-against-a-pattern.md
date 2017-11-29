---
title: "Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83433bdb41df0ce40d0979f3f44603f10ba1c7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="0777b-102">Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0777b-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="0777b-103">Если вы хотите определить выражение [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) соответствует шаблону, можно использовать [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0777b-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="0777b-104">`Like`принимает два операнда.</span><span class="sxs-lookup"><span data-stu-id="0777b-104">`Like` takes two operands.</span></span> <span data-ttu-id="0777b-105">Левый операнд представляет собой строковое выражение, а правый операнд является строкой, содержащей шаблон, используемый для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="0777b-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="0777b-106">`Like`Возвращает `Boolean` значение, указывающее, удовлетворяет ли строковое выражение шаблону.</span><span class="sxs-lookup"><span data-stu-id="0777b-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="0777b-107">Можно сопоставить каждый символ в строковом выражении с определенный символ, подстановочный знак, список символ или диапазон символов.</span><span class="sxs-lookup"><span data-stu-id="0777b-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="0777b-108">Позиции спецификации в строке шаблона соответствуют позиций символов сопоставляемым строковым выражением.</span><span class="sxs-lookup"><span data-stu-id="0777b-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="0777b-109">Сравнение символа в строковом выражении с определенный символ</span><span class="sxs-lookup"><span data-stu-id="0777b-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="0777b-110">Поместите указанный символ непосредственно в строку шаблона.</span><span class="sxs-lookup"><span data-stu-id="0777b-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="0777b-111">Некоторые специальные символы должны заключаться в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="0777b-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="0777b-112">Дополнительные сведения см. в разделе [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0777b-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="0777b-113">В следующем примере проверяется ли `myString` состоит только из символов `H`.</span><span class="sxs-lookup"><span data-stu-id="0777b-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="0777b-114">Сравнение символа в строковом выражении с подстановочным символом</span><span class="sxs-lookup"><span data-stu-id="0777b-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="0777b-115">Поместите вопросительный знак (`?`) в строке шаблона.</span><span class="sxs-lookup"><span data-stu-id="0777b-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="0777b-116">Любой допустимый символ в этой позиции совпадение является успешным.</span><span class="sxs-lookup"><span data-stu-id="0777b-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="0777b-117">В следующем примере проверяется ли `myString` состоит из символов `W` и значений между двумя символами.</span><span class="sxs-lookup"><span data-stu-id="0777b-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="0777b-118">Сравнение символа в строковом выражении в списке символов</span><span class="sxs-lookup"><span data-stu-id="0777b-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="0777b-119">Поместите квадратные скобки (`[ ]`) в строке шаблона и внутри скобок поместите список символов.</span><span class="sxs-lookup"><span data-stu-id="0777b-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="0777b-120">Не разделяйте знаки запятыми или любым другим разделителем.</span><span class="sxs-lookup"><span data-stu-id="0777b-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="0777b-121">Любой символ в списке совпадение является успешным.</span><span class="sxs-lookup"><span data-stu-id="0777b-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="0777b-122">В следующем примере проверяется ли `myString` состоит из любой допустимый символ, за которым следует точно один из символов `A`, `C`, или `E`.</span><span class="sxs-lookup"><span data-stu-id="0777b-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     <span data-ttu-id="0777b-123">Обратите внимание, что при сравнении учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="0777b-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="0777b-124">Сравнение символа в строковом выражении с диапазона символов</span><span class="sxs-lookup"><span data-stu-id="0777b-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="0777b-125">Поместите квадратные скобки (`[ ]`) в строке шаблона и внутри скобок укажите наименьшим и наибольшим символы в диапазоне, разделенных дефисом (`–`).</span><span class="sxs-lookup"><span data-stu-id="0777b-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="0777b-126">Любой символ в диапазоне совпадение является успешным.</span><span class="sxs-lookup"><span data-stu-id="0777b-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="0777b-127">В следующем примере проверяется ли `myString` состоит из символов `num` с одного из символов `i`, `j`, `k`, `l`, `m`, или `n`.</span><span class="sxs-lookup"><span data-stu-id="0777b-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     <span data-ttu-id="0777b-128">Обратите внимание, что при сравнении учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="0777b-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="0777b-129">Сравнение пустых строк</span><span class="sxs-lookup"><span data-stu-id="0777b-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="0777b-130">`Like`рассматривает последовательность `[]` как строка нулевой длины (`""`).</span><span class="sxs-lookup"><span data-stu-id="0777b-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="0777b-131">Можно использовать `[]` для проверки выражения всю строку пуст, но его нельзя использовать для проверки, если определенное место в строковом выражении пуст.</span><span class="sxs-lookup"><span data-stu-id="0777b-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="0777b-132">Если пустая позиция является одним из параметров необходимо проверить, можно использовать `Like` более одного раза.</span><span class="sxs-lookup"><span data-stu-id="0777b-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="0777b-133">Сравнение символа в строковом выражении в списке символов или ни один знак</span><span class="sxs-lookup"><span data-stu-id="0777b-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1.  <span data-ttu-id="0777b-134">Вызовите `Like` оператор дважды для одного строкового выражения и подключиться с помощью двух вызовов [или оператор](../../../../visual-basic/language-reference/operators/or-operator.md) или [оператор OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0777b-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2.  <span data-ttu-id="0777b-135">В строке шаблона для первого `Like` предложение, включите список символов, заключенный в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="0777b-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3.  <span data-ttu-id="0777b-136">В строке шаблона для второго `Like` предложения, не следует помещать любой символ в позиции в вопросе.</span><span class="sxs-lookup"><span data-stu-id="0777b-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="0777b-137">В следующем примере проверяется семь цифр телефонного номера `phoneNum` ровно три цифры, а затем пробел, дефис (`–`), точку (`.`), или ни один знак, за которым следует строго четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="0777b-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0777b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="0777b-138">See Also</span></span>  
 [<span data-ttu-id="0777b-139">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="0777b-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="0777b-140">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="0777b-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="0777b-141">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="0777b-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="0777b-142">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="0777b-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
