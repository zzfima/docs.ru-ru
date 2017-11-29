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
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)
Если вы хотите определить выражение [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) соответствует шаблону, можно использовать [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like`принимает два операнда. Левый операнд представляет собой строковое выражение, а правый операнд является строкой, содержащей шаблон, используемый для сопоставления. `Like`Возвращает `Boolean` значение, указывающее, удовлетворяет ли строковое выражение шаблону.  
  
 Можно сопоставить каждый символ в строковом выражении с определенный символ, подстановочный знак, список символ или диапазон символов. Позиции спецификации в строке шаблона соответствуют позиций символов сопоставляемым строковым выражением.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Сравнение символа в строковом выражении с определенный символ  
  
-   Поместите указанный символ непосредственно в строку шаблона. Некоторые специальные символы должны заключаться в квадратные скобки (`[ ]`). Дополнительные сведения см. в разделе [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     В следующем примере проверяется ли `myString` состоит только из символов `H`.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Сравнение символа в строковом выражении с подстановочным символом  
  
-   Поместите вопросительный знак (`?`) в строке шаблона. Любой допустимый символ в этой позиции совпадение является успешным.  
  
     В следующем примере проверяется ли `myString` состоит из символов `W` и значений между двумя символами.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Сравнение символа в строковом выражении в списке символов  
  
-   Поместите квадратные скобки (`[ ]`) в строке шаблона и внутри скобок поместите список символов. Не разделяйте знаки запятыми или любым другим разделителем. Любой символ в списке совпадение является успешным.  
  
     В следующем примере проверяется ли `myString` состоит из любой допустимый символ, за которым следует точно один из символов `A`, `C`, или `E`.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     Обратите внимание, что при сравнении учитывается регистр.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Сравнение символа в строковом выражении с диапазона символов  
  
-   Поместите квадратные скобки (`[ ]`) в строке шаблона и внутри скобок укажите наименьшим и наибольшим символы в диапазоне, разделенных дефисом (`–`). Любой символ в диапазоне совпадение является успешным.  
  
     В следующем примере проверяется ли `myString` состоит из символов `num` с одного из символов `i`, `j`, `k`, `l`, `m`, или `n`.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     Обратите внимание, что при сравнении учитывается регистр.  
  
## <a name="matching-empty-strings"></a>Сравнение пустых строк  
 `Like`рассматривает последовательность `[]` как строка нулевой длины (`""`). Можно использовать `[]` для проверки выражения всю строку пуст, но его нельзя использовать для проверки, если определенное место в строковом выражении пуст. Если пустая позиция является одним из параметров необходимо проверить, можно использовать `Like` более одного раза.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Сравнение символа в строковом выражении в списке символов или ни один знак  
  
1.  Вызовите `Like` оператор дважды для одного строкового выражения и подключиться с помощью двух вызовов [или оператор](../../../../visual-basic/language-reference/operators/or-operator.md) или [оператор OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  В строке шаблона для первого `Like` предложение, включите список символов, заключенный в квадратные скобки (`[ ]`).  
  
3.  В строке шаблона для второго `Like` предложения, не следует помещать любой символ в позиции в вопросе.  
  
     В следующем примере проверяется семь цифр телефонного номера `phoneNum` ровно три цифры, а затем пробел, дефис (`–`), точку (`.`), или ни один знак, за которым следует строго четыре цифры.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a>См. также  
 [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
