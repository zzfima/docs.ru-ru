---
title: Практическое руководство. Преобразовать массив байтов в строку в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: cd091d743b04ef9d9709bde2b5a1205f3d7ae292
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979517"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Практическое руководство. Преобразовать массив байтов в строку в Visual Basic
В этом разделе показано, как преобразовать байты из массива байтов в строку.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Text.Encoding.GetString%2A> метод <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> кодирование класса, чтобы преобразовать все байты из массива байтов в строку.  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 Можно выбрать из нескольких параметров кодирования для преобразования массива байтов в строку:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Получает кодировку для набора символов ASCII (7-разрядных).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-16 с обратным порядком байтов.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Получает кодировку для текущей кодовой страницы ANSI системы.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-16 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-32 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-8.  
  
## <a name="see-also"></a>См. также
- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [Практическое руководство. Преобразование строки в массив байтов в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
