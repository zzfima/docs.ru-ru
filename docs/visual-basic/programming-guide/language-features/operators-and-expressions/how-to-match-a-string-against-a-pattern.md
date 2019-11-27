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
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Практическое руководство. Сравнение строки на соответствие с шаблоном (Visual Basic)

Если нужно выяснить, удовлетворяет ли выражение [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md) шаблону, можно использовать [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).

`Like` принимает два операнда. Левый операнд является строковым выражением, а правый — строкой, содержащей шаблон, используемый для сопоставления. `Like` возвращает значение типа `Boolean`, указывающее, удовлетворяет ли строковое выражение шаблону.

Каждый символ в строковом выражении можно сопоставить с конкретным символом, символом-шаблоном, списком символов или диапазоном символов. Положения спецификаций в строке шаблона соответствуют позициям символов, которые должны быть сопоставлены в строковом выражении.

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Сопоставление символа в строковом выражении с конкретным символом

Помещает конкретный символ непосредственно в строку шаблона. Некоторые специальные символы должны быть заключены в квадратные скобки (`[ ]`). Дополнительные сведения см. [в разделе Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md).

В следующем примере проверяется, содержит ли `myString` ровно один символ `H`.

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Сопоставление символа в строковом выражении с подстановочным знаком

Добавьте вопросительный знак (`?`) в строку шаблона. Любой допустимый символ в этой позиции делает успешное совпадение.

В следующем примере проверяется, состоит ли `myString` из одного символа `W` за которым следует ровно два символа любого значения.

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Сопоставление символа в строковом выражении со списком символов

Вставьте квадратные скобки (`[ ]`) в строку шаблона, а внутри квадратных скобок вставьте список символов. Не разделяйте символы запятыми или любым другим разделителем. Любой отдельный символ в списке успешно выполняет сопоставление.

В следующем примере проверяется, состоит ли `myString` из любого допустимого символа, за которым следует только один из символов `A`, `C`или `E`.

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

Обратите внимание, что в этом совпадении учитывается регистр.

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Сопоставление символа в строковом выражении с диапазоном символов

Вставьте квадратные скобки (`[ ]`) в строку шаблона, а внутри квадратных скобок — наименьшие и максимальные символы в диапазоне, разделенные дефисом (`–`). Любой отдельный символ в диапазоне выполняет успешное совпадение.

В следующем примере проверяется, состоит ли `myString` символов `num`, за которыми следует только один из символов `i`, `j`, `k`, `l`, `m`или `n`.

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

Обратите внимание, что в этом совпадении учитывается регистр.

## <a name="matching-empty-strings"></a>Совпадающие пустые строки

`Like` считает `[]` последовательности строкой нулевой длины (`""`). Можно использовать `[]`, чтобы проверить, пусто ли строковое выражение, но нельзя использовать его для проверки того, что определенная позицией в строковом выражении пуста. Если пустое расположение является одним из параметров, которые необходимо проверить, можно использовать `Like` несколько раз.

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Сопоставление символа в строковом выражении со списком символов или без символа

1. Дважды вызовите оператор `Like` в одном и том же строковом выражении и соедините два вызова с помощью [оператора либо](../../../../visual-basic/language-reference/operators/or-operator.md) либо [оператора OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md).

2. В строке шаблона для первого предложения `Like` включите список символов, заключенный в квадратные скобки (`[ ]`).

3. В строке шаблона для второго предложения `Like` не помещайте какой бы то ни было символа в рассматриваемой позиции.

    В следующем примере проверяется номер телефона, состоящий из семи цифр, `phoneNum` только для трех цифр, за которыми следует пробел, дефис (`–`), точка (`.`) или символ, за которым следует только четыре цифры.

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a>См. также

- [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md)
- [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
