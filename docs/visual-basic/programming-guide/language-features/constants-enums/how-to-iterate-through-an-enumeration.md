---
title: Практическое руководство. Перебор элементов перечисления в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: dd7a540839fd833d3a316506e433c576edae5384
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979090"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Практическое руководство. Перебор элементов перечисления в Visual Basic
Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами. Для перебора элементов перечисления, его можно переместить в массив с помощью <xref:System.Enum.GetValues%2A> метод. Также можно последовательно пройти по перечисления с помощью `For...Each` инструкции, с помощью <xref:System.Enum.GetNames%2A> или <xref:System.Enum.GetValues%2A> метод, чтобы извлечь строковое или числовое значение.  
  
### <a name="to-iterate-through-an-enumeration"></a>Для выполнения итерации по перечисления  
  
-   Чтобы объявить массив и преобразуйте перечисление к нему с помощью <xref:System.Enum.GetValues%2A> метод перед передачей массива, как вы бы любая другая переменная. В следующем примере отображается каждый член перечисления <xref:Microsoft.VisualBasic.FirstDayOfWeek> мере перечисления.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Практическое руководство. Объявления перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
