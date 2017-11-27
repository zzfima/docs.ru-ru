---
title: "Практическое руководство. Преобразование строки в массив байтов в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6d527434dc0a61c9c771b42d05c1ee316094e7fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
