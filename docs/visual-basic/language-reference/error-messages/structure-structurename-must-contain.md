---
title: "Структура &lt;имяСтруктуры&gt; должна содержать по крайней мере один экземпляр переменной члена или экземпляр объявления события, не помеченный как Custom | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30941"
  - "vbc30941"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30941"
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Структура &lt;имяСтруктуры&gt; должна содержать по крайней мере один экземпляр переменной члена или экземпляр объявления события, не помеченный как Custom
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Определение структуры не включает неиспользуемые совместно переменные или обычные события.  
  
 Каждая структура должна иметь переменную либо событие, которое применяется к каждому определенному экземпляру \(неиспользуемому совместно\), а не ко всем экземплярам совокупности \([Shared](../../../visual-basic/language-reference/modifiers/shared.md)\).  Неиспользуемые совместно константы, свойства и процедуры не удовлетворяют этим требованиям.  Кроме того, если нет неиспользуемых совместно переменных и существует только одно событие, не являющееся общим, то оно не может быть событием `Custom`.  
  
 **Идентификатор ошибки**: BC30941  
  
### Чтобы исправить эту ошибку  
  
-   Определите, по крайней мере, одну переменную или событие, которое не является `Shared`.  Если определить только одно событие, то оно не должно быть типа Custom или совместно используемым.  
  
## См. также  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Практическое руководство. Объявление структуры](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)