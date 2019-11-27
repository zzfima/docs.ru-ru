---
title: Практическое руководство. Преобразование строки в массив символов
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352447"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic
Иногда бывает полезно иметь данные о символах в строке и позициях этих символов в строке, например при анализе строки. В этом примере показано, как можно получить массив символов в строке, вызвав метод <xref:System.String.ToCharArray%2A> строки.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как разделить строку на `Char` массив и как разбить строку на `String` массив символов Юникода. Это различие состоит в том, что текстовые символы Юникода могут состоять из двух или более `Char` символов (например, суррогатной пары или последовательности присоединяемых символов). Дополнительные сведения см. в разделе <xref:System.Globalization.TextElementEnumerator> и [стандарт Unicode](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Пример  
 Сложнее разбить строку на символы в Юникоде, но это необходимо, если требуются сведения о визуальном представлении строки. В этом примере используется метод <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> для получения сведений о символах текста Юникода, составляющих строку.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>См. также

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Практическое руководство. Доступ к символам в строках](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [Преобразование между строками и другими типами данных в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
