---
title: Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c14ea61feba7d7d85f9a4fc377aefdd8fa240c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651704"
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
