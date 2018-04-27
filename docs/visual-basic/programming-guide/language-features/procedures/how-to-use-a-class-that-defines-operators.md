---
title: Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e0bcfaeca638dfabb841a9e935b872f76fdf957
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)
При использовании класса или структуры, определяющей свои собственные операторы, эти операторы доступен в Visual Basic.  
  
 Определение оператора в классе или структуре также называется *перегрузка* оператора.  
  
## <a name="example"></a>Пример  
 Следующий пример обращается к структуре SQL <xref:System.Data.SqlTypes.SqlString>, который определяет операторы преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) в обоих направлениях между строкой SQL и Visual Basic строка. Используйте `CType(` *строковое выражение SQL*, `String)` для преобразования строки SQL в Visual Basic строку и `CType(` *строковое выражение Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` для преобразования в обратном направлении.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <xref:System.Data.SqlTypes.SqlString> Структура определяет оператор преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) из `String` для <xref:System.Data.SqlTypes.SqlString> , а другой из <xref:System.Data.SqlTypes.SqlString> для `String`. Оператор, который присваивает `title` для `jobTitle` использует первый оператор и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов функции используется второй.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать. Не следует предполагать, что класс или структура определяет каждый оператор доступный для перегрузки. Список доступных операторов см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Включите соответствующий `Imports` инструкции для строки SQL в начале файла исходного кода (в данном случае <xref:System.Data.SqlTypes>).  
  
 Проект должен иметь ссылки на System.Data и System.XML.  
  
## <a name="see-also"></a>См. также  
 [Процедуры операторов](./operator-procedures.md)  
 [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)  
 [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)  
 [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)  
 [Расширение](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
