---
title: Практическое руководство. Сопоставление строки с шаблоном (Visual Basic)
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
ms.openlocfilehash: 0bac0869d9e319071abb31dd0576edf0450aa198
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054155"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Практическое руководство. Сопоставление строки с шаблоном (Visual Basic)

Если нужно выяснить, удовлетворяет ли выражение [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) шаблону, можно использовать [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).

`Like`принимает два операнда. Левый операнд является строковым выражением, а правый — строкой, содержащей шаблон, используемый для сопоставления. `Like``Boolean` возвращает значение, указывающее, удовлетворяет ли строковое выражение шаблону.

Каждый символ в строковом выражении можно сопоставить с конкретным символом, символом-шаблоном, списком символов или диапазоном символов. Положения спецификаций в строке шаблона соответствуют позициям символов, которые должны быть сопоставлены в строковом выражении.

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Сопоставление символа в строковом выражении с конкретным символом

Помещает конкретный символ непосредственно в строку шаблона. Некоторые специальные символы должны быть заключены в квадратные скобки (`[ ]`). Дополнительные сведения см. [в разделе Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).

В следующем примере проверяется `myString` , состоит ли только из одного `H`символа.

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Сопоставление символа в строковом выражении с подстановочным знаком

Добавьте вопросительный знак (`?`) в строку шаблона. Любой допустимый символ в этой позиции делает успешное совпадение.

В следующем примере проверяется `myString` , состоит ли из одного `W` символа, за которым следует ровно два символа любого значения.

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Сопоставление символа в строковом выражении со списком символов

Вставьте квадратные`[ ]`скобки () в строку шаблона, а внутри квадратных скобок вставьте список символов. Не разделяйте символы запятыми или любым другим разделителем. Любой отдельный символ в списке успешно выполняет сопоставление.

В следующем примере проверяется `myString` , состоит ли из любого допустимого символа, за которым следует `A`только один из `E`символов, `C`или.

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

Обратите внимание, что в этом совпадении учитывается регистр.

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Сопоставление символа в строковом выражении с диапазоном символов

Вставьте квадратные`[ ]`скобки () в строку шаблона, а внутри квадратных скобок — наименьшие и максимальные символы в диапазоне, разделенные`–`дефисом (). Любой отдельный символ в диапазоне выполняет успешное совпадение.

В следующем примере проверяется `myString` , состоит ли из `num` символов, за которыми следует только один `i`из `j` `m`символов `k`: `l`,,, `n`, или.

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

Обратите внимание, что в этом совпадении учитывается регистр.

## <a name="matching-empty-strings"></a>Совпадающие пустые строки

`Like`обрабатывает последовательность `[]` как строку нулевой длины (`""`). Можно использовать `[]` для проверки, является ли все строковое выражение пустым, но нельзя использовать его для проверки того, что определенная позицией в строковом выражении пуста. Если пустое расположение является одним из параметров, которые необходимо проверить, можно использовать `Like` более одного раза.

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Сопоставление символа в строковом выражении со списком символов или без символа

1. Дважды вызовите `Like` оператор для того же строкового выражения и соедините два вызова с помощью [оператора OR](../../../../visual-basic/language-reference/operators/or-operator.md) или [оператора OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md).

2. В строке шаблона для первого `Like` предложения включите список символов, заключенный в квадратные скобки (`[ ]`).

3. В строке шаблона для второго `Like` предложения не помещайте ни один символ в позиции.

    В следующем примере проверяется номер `phoneNum` телефона, состоящий из семи цифр, для ровно трех цифр, за которыми следует пробел, дефис (`–`), точка`.`() или вообще нет символа, за которыми следует только четыре цифры.

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a>См. также

- [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md)
- [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
