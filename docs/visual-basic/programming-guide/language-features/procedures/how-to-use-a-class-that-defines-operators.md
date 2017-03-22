---
title: "Практическое руководство: использование класс, который определяет операторы (Visual Basic) | Документы Microsoft"
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
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
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
ms.openlocfilehash: b1db7c0b2a6fd8160baa48892b5f2214df24674e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)
При использовании класса или структуры, определяющей свои собственные операторы, можно получить доступ к этим операторам из [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Определение оператора в классе или структуре также называется *перегрузка* оператора.  
  
## <a name="example"></a>Пример  
 Следующий пример обращается к структуре SQL <xref:System.Data.SqlTypes.SqlString>, который определяет операторы преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) в обоих направлениях между строкой SQL и [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] строки.</xref:System.Data.SqlTypes.SqlString> Используйте `CType(` *строковое выражение SQL*, `String)` для преобразования строки SQL для [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] строку, и `CType(` *строковое выражение Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` для преобразования в другом направлении.</xref:System.Data.SqlTypes.SqlString>  
  
 [!code-vb[VbVbcnProcedures&#30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <xref:System.Data.SqlTypes.SqlString>Структура определяет оператор преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) из `String` для <xref:System.Data.SqlTypes.SqlString>и <xref:System.Data.SqlTypes.SqlString>для `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> Оператор, который присваивает `title` для `jobTitle` использует первый оператор и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>вызова функции используется второй.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать. Не следует предполагать, что класс или структура определяет каждый оператор, доступный для перегрузки. Список доступных операторов см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Включить соответствующую `Imports` инструкции для строки SQL в начале файла исходного кода (в данном случае <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes>  
  
 Проект должен иметь ссылки на System.Data и System.XML.  
  
## <a name="see-also"></a>См. также  
 [Процедуры операторов](./operator-procedures.md)   
 [Практическое руководство: определение оператора](./how-to-define-an-operator.md)   
 [Практическое руководство: определение оператора преобразования](./how-to-define-a-conversion-operator.md)   
 [Практическое руководство: вызов процедуры оператора](./how-to-call-an-operator-procedure.md)   
 [Расширяющие](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Сужающие](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Практическое руководство: объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
