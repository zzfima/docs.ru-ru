---
title: 'How to: Define a Conversion Operator'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344897"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Практическое руководство. Определение оператора преобразования (Visual Basic)
Если вы определили класс или структуру, можно определить оператор преобразования типа между типом класса или структуры и другим типом данных (например, `Integer`, `Double`или `String`).  
  
 Определите преобразование типа как процедуру [функции CType](../../../../visual-basic/language-reference/functions/ctype-function.md) в классе или структуре. Все процедуры преобразования должны быть `Public Shared`, и каждая из них должна указывать либо [расширение](../../../../visual-basic/language-reference/modifiers/widening.md) , либо [сужение](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 Определение оператора для класса или структуры также называется *перегрузкой* оператора.  
  
## <a name="example"></a>Пример  
 В следующем примере определяются операторы преобразования между структурой, именуемой `digit`, и `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Вы можете проверить структуру `digit` с помощью следующего кода.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>См. также

- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
- [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
