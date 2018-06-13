---
title: Практическое руководство. Поиск в строке (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 08a005f2927a76c9b29c1ff0092ea8282188b2b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647687"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Практическое руководство. Поиск в строке (Visual Basic)
В этом примере вызывается <xref:System.String.IndexOf%2A> метод <xref:System.String> объекта для отображения индекса первого вхождения подстроки.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   `Imports` Указание инструкции <xref:System> пространства имен. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 <xref:System.String.IndexOf%2A> Метод сообщает номер первого символа первого вхождения подстроки. Индекс отсчитывается от 0, что означает, что первый символ строки имеет индекс 0.  
  
 Если <xref:System.String.IndexOf%2A> не удается найти подстроку, возвращается значение -1.  
  
 <xref:System.String.IndexOf%2A> Метод учитывает регистр и использует текущего языка и региональных параметров.  
  
 Для оптимального управления ошибками можно заключить строку поиска в `Try` блока [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) построения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.String.IndexOf%2A>  
 [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
