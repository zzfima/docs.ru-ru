---
title: Практическое руководство. Вызов процедуры оператора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: b1dc4477daa4ceb9dfc6a9a6ab3f041e68011acd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Практическое руководство. Вызов процедуры оператора (Visual Basic)
Вызов процедуры оператора с помощью символа оператора в выражении. При наличии оператора преобразования следует вызвать [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа в другой.  
  
 Процедуры операторов не вызывается явно. Просто используйте оператор, или `CType` функции, в операторе присваивания или выражения, как и вы обычно используется оператор. Visual Basic выполняет вызов процедуры оператора.  
  
 Определение оператора в классе или структуре также называется *перегрузка* оператора.  
  
### <a name="to-call-an-operator-procedure"></a>Вызов процедуры оператора  
  
1.  Используйте символ оператора в выражении обычным образом.  
  
2.  Убедитесь, что типы данных операндов подходят для оператора и в правильном порядке.  
  
3.  Оператор увеличивает значение выражения, как ожидалось.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Вызов процедуры оператора преобразования  
  
1.  Используйте `CType` внутри выражения.  
  
2.  Убедитесь, что типы данных операндов подходят для преобразования, а также в правильном порядке.  
  
3.  `CType` вызывает процедуру оператора преобразования и возвращает преобразованное значение.  
  
## <a name="example"></a>Пример  
 В следующем примере создается два <xref:System.TimeSpan> структуры, складывает их и сохраняет результат в третьей <xref:System.TimeSpan> структуры. <xref:System.TimeSpan> Структуры определяются процедуры оператора для перегрузки нескольких стандартных операторов.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Поскольку <xref:System.TimeSpan> перегружает стандартный `+` оператор, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.  
  
 Пример вызова процедуры оператора преобразования см. в разделе [как: использование класса преобразования](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать.  
  
## <a name="see-also"></a>См. также  
 [Процедуры операторов](./operator-procedures.md)  
 [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)  
 [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)  
 [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Расширение](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
