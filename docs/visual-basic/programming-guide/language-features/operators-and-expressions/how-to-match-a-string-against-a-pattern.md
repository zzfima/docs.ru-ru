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
ms.openlocfilehash: ca6537d81f080120fcbea0cf083f450dce4e9f62
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826019"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)
Если вы хотите определить выражение [строковый тип данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) удовлетворяет шаблону, можно использовать [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like` принимает два операнда. Левый операнд представляет собой строковое выражение, а правый — строка, содержащая шаблон, используемый для сопоставления. `Like` Возвращает `Boolean` значение, указывающее, удовлетворяет ли строковое выражение шаблону.  
  
 Можно сопоставить каждый символ в строковом выражении с определенный символ, символом-шаблоном, список символ или диапазон символов. Позиции в строке шаблона спецификации соответствуют позиции символов для сопоставления строковым выражением.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Сравнение символа в строковом выражении с указанным символом  
  
-   Поместите указанный символ непосредственно в строку шаблона. Некоторые специальные символы должны заключаться в квадратные скобки (`[ ]`). Дополнительные сведения см. в разделе [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     В следующем примере производится проверка ли `myString` состоит ровно из символов `H`.  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Сравнение символа в строковом выражении с символом-шаблоном  
  
-   Поместить знак вопроса (`?`) в строке шаблона. Любой допустимый символ в этой позиции совпадение является успешным.  
  
     В следующем примере производится проверка ли `myString` состоит из символов `W` и любых значений между двумя символами.  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Сравнение символа в строковом выражении в списке символов  
  
-   Поместите квадратные скобки (`[ ]`) в строке шаблона и внутри скобок укажите список символов. Они не разделяют символы с запятыми или любых других разделителей. Любому одиночному символу в списке совпадение является успешным.  
  
     В следующем примере производится проверка ли `myString` состоит из любой допустимый символ, за которым следует точно один из символов `A`, `C`, или `E`.  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     Обратите внимание на то, что при сравнении учитывается регистр.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Сравнение символа в строковом выражении с диапазона символов  
  
-   Поместите квадратные скобки (`[ ]`) в строку шаблона, а в скобках укажите символы минимальный и максимальный диапазон, разделенных дефисом (`–`). Любому одиночному символу в диапазоне совпадение является успешным.  
  
     В следующем примере производится проверка ли `myString` состоит из символов `num` с одного из символов `i`, `j`, `k`, `l`, `m`, или `n`.  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     Обратите внимание на то, что при сравнении учитывается регистр.  
  
## <a name="matching-empty-strings"></a>Сравнение пустых строк  
 `Like` рассматривает последовательность `[]` как строка нулевой длины (`""`). Можно использовать `[]` для тестирования ли выражение всю строку пуст, но его нельзя использовать для проверки, если определенное положение в строковое выражение является пустым. Если пустая позиция является один из параметров необходимо проверить, можно использовать `Like` более одного раза.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Сравнение символа в строковом выражении в списке символов или ни один знак  
  
1.  Вызовите `Like` оператор дважды для одного строкового выражения и подключение двух вызовов с помощью либо [или оператор](../../../../visual-basic/language-reference/operators/or-operator.md) или [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  В строке шаблона для первого `Like` предложения, включите список символов, заключенные в квадратные скобки (`[ ]`).  
  
3.  В строке шаблона для второго `Like` предложение, не следует помещать любой символ в позиции в вопросе.  
  
     В следующем примере проверяется номер телефона из семи цифр `phoneNum` ровно три цифры, а затем пробел, дефис (`–`), точку (`.`), или ни один знак, за которым следует ровно четыре цифры.  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a>См. также

- [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md)
- [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
