---
title: "Практическое руководство. Перебор элементов перечисления в Visual Basic | Microsoft Docs"
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
  - "массивы [Visual Basic], итерация"
  - "перечисления [Visual Basic], итерация"
  - "ListBox - элемент управления [Windows Forms], заполнение из перечисления"
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Практическое руководство. Перебор элементов перечисления в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Перечисления предлагают удобный способ работы с наборами связанных констант и присвоения постоянным значениям имен.  Для перебора элементов перечисления можно переместить его в массив с помощью метода <xref:System.Enum.GetValues%2A>.  Также можно просмотреть элементы перечисления с помощью оператора `For...Each`, метода <xref:System.Enum.GetNames%2A> или <xref:System.Enum.GetValues%2A> для извлечения строкового или числового значения.  
  
### Для просмотра элементов перечисления  
  
-   Объявите массив и преобразуйте перечисление к нему с помощью метода <xref:System.Enum.GetValues%2A> перед передачей массива так же, как и любую другую переменную.  В следующем примере по мере просмотра элементов перечисления <xref:Microsoft.VisualBasic.FirstDayOfWeek> отображается каждый его элемент.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#7)]  
  
## См. также  
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)