---
title: Практическое руководство. Создание строки из значений массива символьного типа
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: bf37ceba901e712df10ad4b39f9ad74194843136
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346772"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)
В этом примере создается строка «ABCD» из отдельных символов.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a>Компиляция кода  
 Этот метод не имеет особых требований.  
  
 Синтаксис `"a"c`, где один `c` следует за одиночным символом в кавычках, используется для создания символьного литерала.  
  
## <a name="robust-programming"></a>Надежное программирование  
 Символы NULL (эквивалентные `Chr(0)`) в строке могут привести к непредвиденным результатам при использовании строки. Символ null будет включаться в строку, но символы, следующие за символом NULL, не будут отображаться в некоторых ситуациях.  
  
## <a name="see-also"></a>См. также:

- <xref:System.String>
- [Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
