---
title: "Практическое руководство: вызов процедуры оператора (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2403e7a8270c17a8db5417cd8394fd47c373d493
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Практическое руководство. Вызов процедуры оператора (Visual Basic)
Вызов процедуры оператора с помощью символа оператора в выражении. При наличии оператора преобразования следует вызвать [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа данных в другой.  
  
 Не вызывайте процедуры оператора явным образом. Просто используйте оператор, или `CType` функции, в операторе присваивания или выражении так же, обычно используется оператор. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]выполняет вызов процедуры оператора.  
  
 Определение оператора в классе или структуре также называется *перегрузка* оператора.  
  
### <a name="to-call-an-operator-procedure"></a>Вызов процедуры оператора  
  
1.  Используйте символ оператора в выражении обычным образом.  
  
2.  Убедитесь, что типы данных операндов соответствуют для оператора и в правильном порядке.  
  
3.  Оператор относится к значению выражения как ожидалось.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Вызов процедуры оператора преобразования  
  
1.  Используйте `CType` внутри выражения.  
  
2.  Убедитесь, что типы данных операндов соответствуют для преобразования и в правильном порядке.  
  
3.  `CType`вызывает процедуру оператора преобразования и возвращает преобразованное значение.  
  
## <a name="example"></a>Пример  
 В следующем примере создаются два <xref:System.TimeSpan>структур, складывает их и сохраняет результат в третьей <xref:System.TimeSpan>структуры.</xref:System.TimeSpan> </xref:System.TimeSpan> <xref:System.TimeSpan>Структуры определяются процедуры оператора для перегрузки нескольких стандартных операторов.</xref:System.TimeSpan>  
  
 [!code-vb[VbVbcnProcedures&#29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Поскольку <xref:System.TimeSpan>перегружает стандартный `+` оператор, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.</xref:System.TimeSpan>  
  
 Пример вызова процедуры оператора см [Практическое руководство: использование класса преобразования](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать.  
  
## <a name="see-also"></a>См. также  
 [Процедуры операторов](./operator-procedures.md)   
 [Практическое руководство: определение оператора](./how-to-define-an-operator.md)   
 [Практическое руководство: определение оператора преобразования](./how-to-define-a-conversion-operator.md)   
 [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Расширяющие](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Сужающие](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Практическое руководство: объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
