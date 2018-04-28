---
title: Символьные типы данных (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: afd368c00444f136c6d69b02a733c82f0c8eafe0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="character-data-types-visual-basic"></a>Символьные типы данных (Visual Basic)
Visual Basic предоставляет *символьные типы данных* работать с печатными отображаемую символами и. Оба они работают с символами Юникода, `Char` содержит один символ, в то время как `String` содержит неопределенное число символов.  
  
 Таблицу, которая показывает сравнение типов данных Visual Basic, см. [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="char-type"></a>Char-тип  
 `Char` Тип данных — это отдельный символ Юникода (16-разрядная версия) 2 байта. Если переменная всегда хранит ровно один символ, он объявляется как `Char`. Пример:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Каждое возможное значение в `Char` или `String` переменная *кодовой*, или код символа в кодировке Юникод. Символы Юникода включают базовый набор символов ASCII, различные другие буквы алфавита, диакритические знаки, символы валют, дроби, диакритические знаки и математические и технические символы.  
  
> [!NOTE]
>  Набор символов Юникода резервирует кодовые точки от D800 до DFFF (55296 до 55551) для *суррогатной парой*, которых требуется два 16-разрядных значения и представляют одну кодовую точку. Объект `Char` переменная не может содержать суррогатную пару и `String` использует две позиции для хранения таких пар.  
  
 Дополнительные сведения см. в разделе [тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Тип String  
 `String` Тип данных представляет собой последовательность ноль или более символов Юникода (16-разрядная версия) 2 байта. Если переменная может содержать неограниченное число знаков, объявите его как `String`. Пример:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Дополнительные сведения см. в разделе [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>См. также  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
