---
title: "Оператор Erase (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Erase"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Erase - ключевое слово"
  - "Erase - оператор"
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Оператор Erase (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Используется для удаления переменных типа массив и высвобождения памяти, отведенной под их элементы.  
  
## Синтаксис  
  
```  
Erase arraylist  
```  
  
## Части  
 `arraylist`  
 Обязательный.  Список удаляемых переменных типа массив.  Несколько переменных разделяются запятыми.  
  
## Заметки  
 Оператор `Erase` может применяться только на уровне процедур.  Это означает, что удалять переменные типа массив можно внутри процедуры, но не на уровне класса или модуля.  
  
 Оператор `Erase` эквивалентен по своему действию присваиванию значения `Nothing` каждой переменной массива.  
  
## Пример  
 В этом примере показано использование оператора `Erase` для удаления двух массивов и высвобождения использовавшейся ими памяти \(1000 и 100 элементов, соответственно\).  Затем с помощью оператора `ReDim` трехмерному массиву присваивается новый экземпляр массива.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## См. также  
 [Nothing](../../../visual-basic/language-reference/nothing.md)   
 [Оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)