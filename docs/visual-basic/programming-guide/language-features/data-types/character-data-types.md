---
title: Символьные типы данных (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
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
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dca9cde0af08c4113ea9a4644efa40a721b4d9b1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="character-data-types-visual-basic"></a>Символьные типы данных (Visual Basic)
Visual Basic предоставляет *символьные типы данных* работать с печатными отображаемую символами и. Оба они работают с символами Юникода, `Char` содержит один символ, в то время как `String` содержит неопределенное число символов.  
  
 Таблицу, которая показывает сравнение типов данных Visual Basic, см. [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="char-type"></a>Char-тип  
 `Char` Тип данных — это отдельный символ Юникода (16-разрядная версия) 2 байта. Если переменная всегда хранит ровно один символ, он объявляется как `Char`. Пример:  
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 Каждое возможное значение в `Char` или `String` переменная *кодовой*, или код символа в кодировке Юникод. Символы Юникода включают базовый набор символов ASCII, различные другие буквы алфавита, диакритические знаки, символы валют, дроби, диакритические знаки и математические и технические символы.  
  
> [!NOTE]
>  Набор символов Юникода резервирует кодовые точки от D800 до DFFF (55296 до 55551) для *суррогатной парой*, которых требуется два 16-разрядных значения и представляют одну кодовую точку. Объект `Char` переменная не может содержать суррогатную пару и `String` использует две позиции для хранения таких пар.  
  
 Дополнительные сведения см. в разделе [тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Тип String  
 `String` Тип данных представляет собой последовательность ноль или более символов Юникода (16-разрядная версия) 2 байта. Если переменная может содержать неограниченное число знаков, объявите его как `String`. Пример:  
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 Дополнительные сведения см. в разделе [строкового типа данных](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>См. также  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
