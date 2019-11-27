---
title: Практическое руководство. Вызов процедуры оператора
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
ms.openlocfilehash: a685be7cc3b346b271413e2c29faae5a839313f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340246"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Практическое руководство. Вызов процедуры оператора (Visual Basic)
Для вызова процедуры оператора используется символ оператора в выражении. В случае оператора преобразования вызывается [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа данных в другой.  
  
 Процедуры оператора не вызываются явным образом. Вы просто используете оператор или функцию `CType` в операторе присваивания или выражении так же, как обычно используется оператор. Visual Basic выполняет вызов процедуры оператора.  
  
 Определение оператора для класса или структуры также называется *перегрузкой* оператора.  
  
### <a name="to-call-an-operator-procedure"></a>Вызов процедуры оператора  
  
1. Используйте символ оператора в выражении обычным образом.  
  
2. Убедитесь, что типы данных операндов подходят для оператора, и в правильном порядке.  
  
3. Оператор влияет на значение выражения, как и ожидалось.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Вызов процедуры оператора преобразования  
  
1. Используйте `CType` внутри выражения.  
  
2. Убедитесь, что типы данных операндов подходят для преобразования, и в правильном порядке.  
  
3. `CType` вызывает процедуру оператора преобразования и возвращает преобразованное значение.  
  
## <a name="example"></a>Пример  
 Следующий пример создает две структуры <xref:System.TimeSpan>, добавляет их вместе и сохраняет результат в третьей структуре <xref:System.TimeSpan>. Структура <xref:System.TimeSpan> определяет процедуры операторов для перегрузки нескольких стандартных операторов.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 Поскольку <xref:System.TimeSpan> перегружает стандартный оператор `+`, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.  
  
 Пример вызова процедуры оператора диалога см. [в разделе как использовать класс, определяющий операторы](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что используемый класс или структура определяет оператор, который вы хотите использовать.  
  
## <a name="see-also"></a>См. также

- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Расширение](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
