---
title: "Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "перечисления [Visual Basic]"
  - "строки [Visual Basic], значения перечисления"
  - "значения, члены перечисления"
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Методы <xref:System.Enum.GetValues%2A> и <xref:System.Enum.GetNames%2A> позволяют определить строки и значения, связанные с членами перечисления.  
  
### Определение строки, связанной с перечислением  
  
-   Используйте метод <xref:System.Enum.GetNames%2A> для получения строк, связанных с членами перечисления.  В этом примере объявляется перечисление, `flavorEnum`, затем используется метод <xref:System.Enum.GetNames%2A> для отображения строк, связанных с каждым членом.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## См. также  
 <xref:System.Enum.GetValues%2A>   
 <xref:System.Enum.GetNames%2A>   
 <xref:System.Enum>   
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)