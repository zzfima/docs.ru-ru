---
title: Практическое руководство. Доступа к символам строк в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 840a769b0bb322ef7b878a312437c5ec200ab074
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834495"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Практическое руководство. Доступа к символам строк в Visual Basic
В этом примере демонстрируется использование <xref:System.String.Chars%2A> свойство для доступа к знаку в указанном расположении в строке.  
  
## <a name="example"></a>Пример  
 Иногда бывает удобно иметь данные о символов в строки и позиции этих символов. Можно считать строки массив символов (`Char` экземпляров); можно получить определенный символ, ссылаясь на индекс символа с помощью <xref:System.String.Chars%2A> свойство.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 `index` Параметр <xref:System.String.Chars%2A> свойство отсчитывается от нуля.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 <xref:System.String.Chars%2A> Свойство возвращает символ в указанной позиции. Тем не менее некоторые символы Юникода могут быть представлены более одного символа. Дополнительные сведения о том, как работать с символами Юникода, см. в разделе [как: Преобразует строку в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 <xref:System.String.Chars%2A> Свойство выдает исключение <xref:System.IndexOutOfRangeException> исключения Если `index` параметр больше или равен длине строки, или если он меньше нуля  
  
## <a name="see-also"></a>См. также

- <xref:System.String.Chars%2A>
- [Практическое руководство. Преобразует строку в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Преобразование между строками и другими типами данных в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
