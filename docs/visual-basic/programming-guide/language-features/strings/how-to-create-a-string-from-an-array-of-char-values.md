---
title: Практическое руководство. Создать строку из массива значений типа Char (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 1f72cb86ffa38dc929062fab2f5592a781f2de27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831830"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Практическое руководство. Создать строку из массива значений типа Char (Visual Basic)
Этот пример создает строки «abcd» из отдельных символов.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Этот метод не имеет специальных требований.  
  
 Синтаксис `"a"c`, когда одному `c` соответствует отдельный символ в кавычки, используется для создания символьного литерала.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Символы NULL (эквивалентно `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании этой строки. Нуль-символ будет включен в строку, но символы, следующие нуль-символ будет отображаться в некоторых ситуациях.  
  
## <a name="see-also"></a>См. также

- <xref:System.String>
- [Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
