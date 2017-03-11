---
title: "Практическое руководство. Хранение нескольких значений в переменной (Visual Basic) | Microsoft Docs"
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
  - "массивы [Visual Basic], ошибки компиляции"
  - "массивы [Visual Basic], составные типы данных"
  - "классы [Visual Basic], составные типы данных"
  - "составные типы данных"
  - "составные типы"
  - "типы данных [Visual Basic], составной"
  - "структуры, составные типы данных"
  - "типы [Visual Basic], составной"
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если переменная объявлена как имеющая *составной тип данных*, то она может содержать более одного значения.  
  
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) включают структуры, массивы и классы.  Переменная составного типа данных может содержать сочетание простейших типов данных и других составных типов.  Структуры и классы могут содержать и код, и данные.  
  
### Хранение нескольких значений в переменной  
  
1.  Определите, какой именно составной тип данных требуется использовать для переменной.  
  
2.  Если составной тип данных еще не определен, определите его, для того чтобы переменная могла его использовать.  
  
    -   Определите структуру при помощи [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).  
  
    -   Определите массив при помощи [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
    -   Определите класс при помощи [Оператор Class](../../../../visual-basic/language-reference/statements/class-statement.md).  
  
3.  Объявите переменную при помощи оператора `Dim`.  
  
4.  После имени переменной укажите предложение `As`.  
  
5.  После ключевого слова `As` укажите имя соответствующего составного типа.  
  
## См. также  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)