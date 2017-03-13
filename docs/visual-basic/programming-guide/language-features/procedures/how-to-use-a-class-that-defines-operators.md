---
title: "Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "примеры [Visual Basic], CType"
  - "перегрузка операторов"
  - "процедуры операторов, вызов"
  - "операторы [Visual Basic], перегрузка"
  - "процедуры, вызов"
  - "процедуры, оператор"
  - "возвращаемые значения, Процедуры операторов"
  - "синтаксис, Процедуры операторов"
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

При использовании класса или структуры, определяющей свои собственные операторы, можно получить доступ к этим операторам из [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Определение оператора в классе или структуре называется также *перегрузкой* оператора.  
  
## Пример  
 В следующем примере осуществляется доступ к SQL структуре <xref:System.Data.SqlTypes.SqlString>, в которой определены операторы преобразования \([Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)\) в обоих направлениях между строкой SQL и строкой [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Используйте `CType(`*SQL string expression*, `String)` для преобразования строки SQL к строке [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] и `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` для преобразования в обоих направлениях.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 Структура <xref:System.Data.SqlTypes.SqlString> определяет оператор преобразования \([Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)\) из `String` в <xref:System.Data.SqlTypes.SqlString> и из <xref:System.Data.SqlTypes.SqlString> в `String`.  Оператор, который присваивает значение `title` объекту `jobTitle`, использует первый оператор, а вызов функции <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> использует второй.  
  
## Компиляция кода  
 Убедитесь, что используемый класс или структура определяет оператор, который нужно использовать.  Не следует предполагать, что класс или структура определяет каждый оператор как доступный для перегрузки.  Список доступных операторов содержится в разделе [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Включите соответствующий оператор `Imports` для строки SQL в начале исходного файла \(в этом случае <xref:System.Data.SqlTypes>\).  
  
 Проект должен ссылаться на System.Data и System.XML.  
  
## См. также  
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Практическое руководство. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Практическое руководство. Вызов процедуры оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)