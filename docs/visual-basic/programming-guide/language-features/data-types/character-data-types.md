---
title: "Символьные типы данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7ce600fe188c94593e4c07e37883ca11f90d9ae5
ms.lasthandoff: 03/13/2017

---
# <a name="character-data-types-visual-basic"></a>Символьные типы данных (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет *символьные типы данных* для работы с символами, печати и отображения. Хотя оба они работают с символами Юникода, `Char` содержит один символ, тогда как `String` содержит неопределенное число символов.  
  
 Для таблицы, которая отображает сравнение side-by-side [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] типы данных в разделе [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="char-type"></a>Тип char  
 `Char` Тип данных является символ Юникода (16-разрядная версия)&2; байта. Если переменная всегда хранит ровно один знак, объявите ее в качестве `Char`. Например:  
  
 [!code-vb[VbVbalrCharTypes&#1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 Каждое возможное значение в `Char` или `String` переменная *кодовой*, или код символа в кодировке Юникод. Символы Юникода включают базовый набор символов ASCII, различные другие буквы алфавита, знаки ударения, символы валют, дроби, диакритические знаки и математические и технические символы.  
  
> [!NOTE]
>  Набор символов Юникода резервирует кодовые точки от D800 до DFFF (55296 до 55551) для *суррогатные пары*, который требуется два 16-разрядных значения и представляют одну кодовую точку. Объект `Char` переменная не может содержать суррогатную пару и `String` использует две позиции для хранения таких пар.  
  
 Дополнительные сведения см. в разделе [тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Тип строки  
 `String` Тип данных представляет собой последовательность из нуля или более символов Юникода (16-разрядная версия)&2; байта. Если переменная может содержать неограниченное количество символов, он объявляется как `String`. Пример:  
  
 [!code-vb[VbVbalrCharTypes&#2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 Дополнительные сведения см. в разделе [строковый тип данных](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>См. также  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
