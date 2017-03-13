---
title: "Символьные типы данных (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Char - тип данных, символьные типы данных"
  - "символьные типы данных [Visual Basic]"
  - "типы данных [Visual Basic], знак"
  - "типы данных [Visual Basic], выбор"
  - "String - тип данных, символьные типы данных"
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Символьные типы данных (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет *символ типов данных* для работы с печатными символами и символами для визуализации.  Тип `Char` может содержать единственный символ, в то время как тип `String` может содержать неограниченное количество символов, но оба типа работают с символами юникода.  
  
 Сведения о таблице, в которой отображается одновременное сравнения типов данных [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] содержатся в разделе [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Тип Char  
 Тип данных `Char` является одиночным двухбайтовым \(16\-битным\) знаком Юникода.  Если переменная всегда хранит ровно один знак, объявите ее в качестве `Char`.  Примеры.  
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 Каждое возможное значение в `Char` или `String` является *кодовой точкой* или кодом символа в кодировке Юникод.  Символы Юникода включают базовую кодировку ASCII, различные другие буквы алфавита, знаки ударения, символы денежных единиц, дроби, диакритические знаки, математические и технические символы.  
  
> [!NOTE]
>  Кодировка Юникода резервирует кодовые точки от D800 до DFFF \(десятичные — от 55296 до 55551\) для *пар символов\-заместителей*, которые требуют два 16\-разрядных значения и представляют одну кодовую точку.  Переменная `Char` не может хранить пары символов\-заместителей, и `String` использует две позиции для хранения таких пар.  
  
 Дополнительные сведения см. в разделе [Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## Тип String  
 Тип данных `String` — это последовательность, содержащая ни одного или любое число двухбайтовых \(16\-битных\) знаков Юникода.  Если переменная может содержать неограниченное число знаков, объявите ее в качестве `String`.  Примеры.  
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 Дополнительные сведения см. в разделе [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## См. также  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)