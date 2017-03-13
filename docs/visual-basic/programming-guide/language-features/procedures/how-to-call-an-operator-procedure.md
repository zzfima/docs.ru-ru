---
title: "Практическое руководство. Вызов процедуры оператора (Visual Basic) | Microsoft Docs"
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
  - "перегрузка операторов"
  - "процедуры операторов, вызов"
  - "операторы [Visual Basic], перегрузка"
  - "перегруженные операторы, вызов"
  - "вызовы процедур, перегрузка операторов"
  - "процедуры, оператор"
  - "возвращаемые значения, Процедуры операторов"
  - "синтаксис, Процедуры операторов"
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Вызов процедуры оператора (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Вызов оператора процедуры осуществляется с помощью символа оператора в выражении.  При наличии такого оператора преобразования следует вызвать [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа данных в другой.  
  
 Не вызывайте процедуры оператора явным образом.  Просто используйте оператор или функцию `CType` в операторе присваивания или выражении так же, как обычно используется оператор.  В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] выполняется вызов процедуры оператора.  
  
 Определение оператора в классе или структуре называется также *перегрузкой* оператора.  
  
### Вызов процедуры оператора  
  
1.  Используйте символ оператора в выражении обычным образом.  
  
2.  Убедитесь, что типы данных операндов соответствуют оператору и имеют правильный порядок.  
  
3.  Оператор относится к значению выражения, как и ожидалось.  
  
### Вызов процедуры оператора преобразования  
  
1.  Используйте `CType` внутри выражения.  
  
2.  Убедитесь, что типы данных операндов соответствуют преобразованию и указаны в правильном порядке.  
  
3.  `CType` вызывает процедуру оператора преобразования и возвращает преобразованное значение.  
  
## Пример  
 В приведенном ниже примере создаются две структуры <xref:System.TimeSpan>, складываются друг с другом и результат сохраняется в третьей структуре <xref:System.TimeSpan>.  В структуре <xref:System.TimeSpan> определяются процедуры оператора для перегрузки нескольких стандартных операторов.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Поскольку <xref:System.TimeSpan> перегружает стандартный оператор `+`, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.  
  
 Пример вызова процедуры оператора преобразования см. в разделе [Практическое руководство. Использование класса, в котором определяются операторы](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md).  
  
## Компиляция кода  
 Убедитесь, что используемый класс или структура определяет оператор, который нужно использовать.  
  
## См. также  
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Практическое руководство. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)