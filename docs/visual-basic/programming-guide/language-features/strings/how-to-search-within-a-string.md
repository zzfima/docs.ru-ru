---
title: Практическое руководство. Поиск в строке (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: b690aa78a2cf07b0db5bdd28d7d71ed4a79fbf61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032088"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Практическое руководство. Поиск в строке (Visual Basic)
В этом примере вызывается <xref:System.String.IndexOf%2A> метод <xref:System.String> объекта для отображения индекса первого вхождения подстроки.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- `Imports` Инструкция <xref:System> пространства имен. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 <xref:System.String.IndexOf%2A> Метод сообщает расположение первого символа первого вхождения подстроки. Индекс отсчитывается от 0, это означает, что первый символ строки имеет индекс 0.  
  
 Если <xref:System.String.IndexOf%2A> не удается найти подстроку, возвращается значение -1.  
  
 <xref:System.String.IndexOf%2A> Метод учитывает регистр и использует текущего языка и региональных параметров.  
  
 Для лучшей защиты от ошибок может потребоваться заключить строку поиска в `Try` блока [попробуйте... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) конструкции.  
  
## <a name="see-also"></a>См. также

- <xref:System.String.IndexOf%2A>
- [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)
