---
title: Практическое руководство. Определение строки, связанной со значением из перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c396a4e2ebe973f5be65c3fab5f22cdedb29be1a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351135"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)
Методы <xref:System.Enum.GetValues%2A> и <xref:System.Enum.GetNames%2A> позволяют определить строки и значения, связанные с элементами перечисления.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Определение строки, связанной с перечислением  
  
- Используйте метод <xref:System.Enum.GetNames%2A> для получения строк, связанных с элементами перечисления. В этом примере объявляется перечисление `flavorEnum`, а затем используется метод <xref:System.Enum.GetNames%2A> для вывода строк, связанных с каждым элементом.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Инструкции. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Пошаговое руководство. перебор перечислений в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
