---
title: Символьные типы данных (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: d29e8771d61c04cf35aa71b5ba7fbba0d308c730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965679"
---
# <a name="character-data-types-visual-basic"></a>Символьные типы данных (Visual Basic)
Visual Basic предоставляет *символьные типы данных* для работы с печатными и отображаемыми символами. Несмотря на то, что они работают с `Char` символами Юникода, содержит один `String` символ, тогда как содержит неопределенное число символов.  
  
 Для таблицы, отображающей параллельное сравнение типов данных Visual Basic, см. в разделе [типы данных](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Тип char  
 Тип `Char` данных — это один двухбайтовый (16-разрядный) символ Юникода. Если переменная всегда хранит ровно один символ, объявите ее как `Char`. Например:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Каждое возможное значение в `Char` переменной или `String` является кодовой *точкой*или кодом символа в кодировке Юникода. Символы Юникода включают в себя основную кодировку ASCII, различные буквы, цифры, символы валют, дроби, диакритические знаки, математические и технические символы.  
  
> [!NOTE]
> Набор символов Юникода резервирует кодовые точки D800 до DFFF (от 55296 до 55551 десятичного) для *пар символов*-заместителей, для которых требуются 2 16-разрядные значения для представления одной кодовой точки. Переменная не может содержать суррогатную пару, `String` а для хранения такой пары используется две позиции. `Char`  
  
 Дополнительные сведения см. в разделе [тип данных char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Тип строки  
 Тип `String` данных — это последовательность из нуля или более двухбайтовых (16-разрядных) символов Юникода. Если переменная может содержать неопределенное число символов, объявите ее как `String`. Например:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Дополнительные сведения см. в разделе [тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>См. также

- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
