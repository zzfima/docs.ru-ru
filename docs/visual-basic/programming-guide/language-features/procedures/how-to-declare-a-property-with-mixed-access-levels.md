---
title: "Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic) | Microsoft Docs"
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
  - "уровни доступа, свойства"
  - "смешанные уровни доступа"
  - "процедуры, определение"
  - "свойства [Visual Basic], уровни доступа"
  - "Property - оператор, объявление смешанных уровней доступа"
  - "код Visual Basic, процедуры"
  - "код Visual Basic, свойства"
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если процедуры свойства `Get` и `Set` должны иметь различные уровни доступа, можно использовать менее строгий уровень в операторе `Property` и более строгий уровень в операторе `Get` или `Set`.  Чтобы определенные части кода могли получить значение свойства, а другие части кода имели возможность изменить значение свойства, необходимо использовать смешанный доступ для свойства.  
  
 Дополнительные сведения по уровням доступа содержатся в разделе [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### Для объявления свойства со смешанным уровнем доступа  
  
1.  Объявите свойство обычным способом и укажите менее строгий уровень доступа \(например `Public`\) в операторе `Property`.  
  
2.  Объявите процедуру `Get` или `Set`, указав более строгий уровень доступа \(например `Friend`\).  
  
3.  Не указывайте уровень доступа для другой процедуры свойства.  Предполагается, что уровень доступа объявлен в операторе `Property`.  Можно ограничить доступ только одной процедуре свойства.  
  
     [!code-vb[VbVbcnProcedures#10](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-declare-a-propert_1.vb)]  
  
     В предыдущем примере процедура `Get` имеет такой же уровень доступа `Protected`, как и само свойство, в то время как процедура `Set` имеет уровень доступа `Private`.  Класс, производный от `employee`, может получить значение `salary`, но только класс `employee` может установить его.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Практическое руководство. Создание свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Практическое руководство. Вызов процедуры свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство. Запись значения в свойство](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Практическое руководство. Получение значения из свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)