---
title: "Директива #Const | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.#Const"
  - "#vb.Const"
  - "#Const"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#Const - директива"
  - "условная компиляция, директивы"
  - "Const - директива (#Const)"
  - "Const - оператор [Visual Basic], директива (#Const)"
  - "константы, Const - директива"
  - "константы, объявление"
  - "объявление констант, #const - директива"
  - "компилятор Visual Basic, директивы компилятора"
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Директива #Const
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объявляет константы условной компиляции для Visual Basic.  
  
## Синтаксис  
  
```  
#Const constname = expression  
```  
  
## Части  
 `constname`  
 Обязательный.  Имя определяемой константы.  
  
 `expression`  
 Обязательный.  Литерал, другая константа условной компиляции, или любое другое выражение, включающее любые или все арифметические или логические операторы, кроме `Is`.  
  
## Заметки  
 Константы условной компиляции действительны только внутри файла, в котором они объявлены.  Невозможно создать открытые константы компилятора с помощью директивы `#Const`; можно создавать их только в пользовательском интерфейсе или с помощью параметра компилятора `/define`.  
  
 В `expression` можно использовать только константы условной компиляции и литералы.  Использование стандартных констант в определении `Const` вызывает ошибку.  Можно использовать константы, определенные с помощью ключевого слова `#Const` только для условной компиляции.  Константы также могут быть неопределенными, при этом их значение равно `Nothing`.  
  
## Пример  
 В следующем примере используется директива `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## См. также  
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)