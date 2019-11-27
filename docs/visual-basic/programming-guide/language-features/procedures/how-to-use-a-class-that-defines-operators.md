---
title: Практическое руководство. Использование класса, в котором определяются операторы
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 9ec4b4c07910100dd02cc86e882b44aa7dbd2ced
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346040"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)
При использовании класса или структуры, определяющей собственные операторы, можно получить доступ к этим операторам из Visual Basic.  
  
 Определение оператора для класса или структуры также называется *перегрузкой* оператора.  
  
## <a name="example"></a>Пример  
 В следующем примере осуществляется доступ к структуре SQL <xref:System.Data.SqlTypes.SqlString>, которая определяет операторы преобразования ([Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) в обоих направлениях между строкой SQL и строкой Visual Basic. Используйте `CType(`*строковое выражение SQL*, `String)` для преобразования строки sql в Visual Basic строку и `CType(`*Visual Basic строкового выражения*<xref:System.Data.SqlTypes.SqlString>`)` для преобразования в другом направлении.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 Структура <xref:System.Data.SqlTypes.SqlString> определяет оператор преобразования ([функцию CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) от `String` до <xref:System.Data.SqlTypes.SqlString>, а другой — от <xref:System.Data.SqlTypes.SqlString> до `String`. Инструкция, которая присваивает `title` `jobTitle` использует первый оператор, а <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов функции использует второй метод.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что используемый класс или структура определяет оператор, который вы хотите использовать. Не следует считать, что класс или структура определили все операторы, доступные для перегрузки. Список доступных операторов см. в разделе Оператор [operator](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Включите соответствующую инструкцию `Imports` для строки SQL в начало исходного файла (в данном случае <xref:System.Data.SqlTypes>).  
  
 Проект должен иметь ссылки на System. Data и System. XML.  
  
## <a name="see-also"></a>См. также

- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Расширение](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
