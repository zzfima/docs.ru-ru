---
title: "Практическое руководство. Ссылка на член перечисления (Visual Basic) | Microsoft Docs"
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
  - "константы, перечисленные"
  - "члены перечисления"
  - "перечисления [Visual Basic], ссылка на"
  - "значения, связывание значений константы с именами"
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Практическое руководство. Ссылка на член перечисления (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Перечисления являются удобным способом работы с наборами связанных констант и сопоставления постоянных значений с именами.  Например, можно объявить перечисление для набора целочисленных констант, связанных с днями недели, а затем использовать в коде названия дней недели, а не числа.  
  
 Избежать использования полных имен можно с помощью оператора `Imports`.  Дополнительные сведения см. в разделе [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### Для ссылки на элемент перечисления выполните следующие действия:  
  
-   Квалифицируйте имя члена с перечислением.  Например, в следующем примере член `Saturday` перечисления `FirstDayOfWeek` назначается переменной `DayValue`.  
  
     [!code-vb[VbEnumsTask#19](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#19)]  
  
## См. также  
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)