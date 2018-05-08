---
title: Практическое руководство. Преобразование строки в массив байтов в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: da4a47b955b91f4bb39ecd7832da30d76e75d553
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Практическое руководство. Преобразование строки в массив байтов в Visual Basic
В этом разделе показано, как преобразовать строку в массив байтов.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Text.Encoding.GetBytes%2A> метод <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> кодирование класса для преобразования строки в массив байтов.  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-strings-into-an-array-of-bytes_1.vb)]  
  
 Можно выбрать из нескольких параметров кодирования для преобразования строки в массив байтов:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Возвращает кодировку для символов ASCII (7-разрядных) в наборе.  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-16 с обратным порядком байтов.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Возвращает кодировку для текущей кодовой страницы ANSI системы.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-16 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-32 с прямым порядком байтов.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-8.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetBytes%2A>  
 [Как: преобразование массива байтов в строку в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
