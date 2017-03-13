---
title: "Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic) | Microsoft Docs"
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
  - "примеры [Visual Basic], массивы"
  - "примеры [Visual Basic], Char - тип данных"
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Этот пример создает строку "abcd" из отдельных символов.  
  
## Пример  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## Компиляция кода  
 У этого метода нет особых требований.  
  
 Синтаксис `"a"c`, где одному `c` соответствует отдельный символ в кавычках, используется для создания символьного литерала.  
  
## Отказоустойчивость  
 Пустые символы \(эквивалентные `Chr(0)`\) в строке могут привести к непредсказуемым результатам при использовании этой строки.  Символ NULL будет включен в строку, но следующие за ним символы в некоторых ситуациях могут не отображаться.  
  
## См. также  
 <xref:System.String>   
 [Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)