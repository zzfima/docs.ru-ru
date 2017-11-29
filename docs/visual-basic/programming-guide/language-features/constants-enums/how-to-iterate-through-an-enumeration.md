---
title: "Практическое руководство. Перебор элементов перечисления в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 439e6eae7d475316625a2cc1d3a70a9e7181f68a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
