---
title: Практическое руководство. Доступ к символам в строках
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352463"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Практическое руководство. Доступ к символам строк в Visual Basic
В этом примере показано, как использовать свойство <xref:System.String.Chars%2A> для доступа к символу в указанном месте в строке.  
  
## <a name="example"></a>Пример  
 Иногда бывает полезно иметь данные о символах в строке и позициях этих символов в строке. Строку можно представить как массив символов (`Char` экземпляров); Вы можете получить определенный символ, обратившись к индексу этого символа через свойство <xref:System.String.Chars%2A>.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 Параметр `index` свойства <xref:System.String.Chars%2A> отсчитывается от нуля.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Свойство <xref:System.String.Chars%2A> возвращает символ в указанной позиции. Однако некоторые символы Юникода могут быть представлены более чем одним символом. Дополнительные сведения о работе с символами Юникода см. в разделе [инструкции. Преобразование строки в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Свойство <xref:System.String.Chars%2A> вызывает исключение <xref:System.IndexOutOfRangeException>, если параметр `index` больше или равен длине строки или если он меньше нуля.  
  
## <a name="see-also"></a>См. также

- <xref:System.String.Chars%2A>
- [Практическое руководство. Преобразование строки в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Преобразование между строками и другими типами данных в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
