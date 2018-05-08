---
title: Практическое руководство. Перебор элементов перечисления в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 06609d38c805e5f073a2f3a299ecc3aa7cf7be01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Практическое руководство. Перебор элементов перечисления в Visual Basic
Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами. Для перебора элементов перечисления, его можно переместить в массив с помощью <xref:System.Enum.GetValues%2A> метод. Вы также можно просмотреть элементы перечисления с помощью `For...Each` инструкции, с помощью <xref:System.Enum.GetNames%2A> или <xref:System.Enum.GetValues%2A> метод для извлечения строковое или числовое значение.  
  
### <a name="to-iterate-through-an-enumeration"></a>Для перебора элементов перечисления  
  
-   Объявите массив и преобразуйте перечисление к нему с <xref:System.Enum.GetValues%2A> метод перед передачей массива, как вы бы любую другую переменную. В следующем примере отображается каждый член перечисления <xref:Microsoft.VisualBasic.FirstDayOfWeek> как в нем производится итерация по перечислению.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
