---
title: Как выполнить Создать строку из массива значений типа Char (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: a067474d6b32589a34b031d5c3ea4e5a4be55834
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611466"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Как выполнить Создать строку из массива значений типа Char (Visual Basic)
Этот пример создает строки «abcd» из отдельных символов.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Этот метод не имеет специальных требований.  
  
 Синтаксис `"a"c`, когда одному `c` соответствует отдельный символ в кавычки, используется для создания символьного литерала.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Символы NULL (эквивалентно `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании этой строки. Нуль-символ будет включен в строку, но символы, следующие нуль-символ будет отображаться в некоторых ситуациях.  
  
## <a name="see-also"></a>См. также
- <xref:System.String>
- [Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
