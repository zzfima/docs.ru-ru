---
title: "Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01e2b0cfa6b1e426b38198581c7d493c8907b79b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)
<xref:System.Enum.GetValues%2A> И <xref:System.Enum.GetNames%2A> методы позволяют определить строки и значения, связанные с членами перечисления.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Чтобы определить строку, связанную с перечислением  
  
-   Используйте <xref:System.Enum.GetNames%2A> метод для извлечения строки, связанные с членами перечисления. В этом примере объявляется перечисление, `flavorEnum`, затем использует <xref:System.Enum.GetNames%2A> метод для отображения строк, связанных с каждым элементом.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [Как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Как: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
