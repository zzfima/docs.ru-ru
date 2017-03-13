---
title: "Практическое руководство. Вызов процедуры свойства (Visual Basic) | Microsoft Docs"
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
  - "вызовы процедур, процедуры свойств"
  - "процедуры, вызов"
  - "свойства [Visual Basic], процедуры свойств"
  - "код Visual Basic, процедуры"
  - "код Visual Basic, свойства"
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Вызов процедуры свойства (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Вызов свойства процедуры посредством хранения значения свойства или его извлечения.  Доступ к свойству такой же, как и доступ к переменной.  
  
 Процедура свойства `Set` сохраняет значение, а его процедура `Get` извлекает значение.  Однако по имени данные процедуры не вызываются явным образом.   Свойство в операторе присваивания или выражении используется так же, как при сохранении или извлечении значения переменной.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] осуществляет вызовы процедур свойств.  
  
### Вызов процедуры Get свойства  
  
1.  Используйте имя свойства в выражении так же, как используется имя переменной.  Можно использовать свойство везде, где можно использовать переменную или константу.  
  
     \-или\-  
  
     Используйте имя свойства после знака равенства \(`=`\) в операторе присваивания.  
  
     В следующем примере считывается значение свойства <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>, при этом происходит неявный вызов процедуры `Get`.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства должен в скобках указываться список аргументов.  Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.  Убедитесь что аргументы предоставляются в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение свойства входит в выражение так же, как переменная или константа, либо оно хранится в переменной или свойстве в левой части оператора присваивания.  
  
### Вызов процедуры Set свойства  
  
1.  Записывайте имя свойства слева от оператора присваивания.  
  
     В следующем примере задается значение свойства <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>, при этом происходит неявный вызов процедуры `Set`.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства должен в скобках указываться список аргументов.  Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.  Убедитесь что аргументы предоставляются в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение, созданное в правой части оператора присваивания, сохранится в свойстве.  
  
## См. также  
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Практическое руководство. Создание свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство. Запись значения в свойство](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Практическое руководство. Получение значения из свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)   
 [Оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)   
 [Оператор Set](../../../../visual-basic/language-reference/statements/set-statement.md)