---
title: "Метод доступа Set свойства &lt;имяСвойства&gt; недоступен | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31102"
  - "bc31102"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31102"
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Метод доступа Set свойства &lt;имяСвойства&gt; недоступен
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор пытается сохранить значение свойства, если у него нет доступа к процедуре `Set` данного свойства.  
  
 Если [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md) имеет более ограниченный уровень доступа, чем [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md), то попытка записать значение свойства может завершиться ошибкой в следующих случаях:  
  
-   Оператор `Set` помечен как [Private](../../../visual-basic/language-reference/modifiers/private.md), а вызывающий код находится вне класса или структуры, в которой определено свойство.  
  
-   Оператор `Set` помечен как [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код не находится ни в классе или структуре, в которой определено свойство, ни в производном классе.  
  
-   Оператор `Set` помечен как [Friend](../../../visual-basic/language-reference/modifiers/friend.md), и вызывающий код находится в сборке, отличной от той, в которой определено свойство.  
  
 **Идентификатор ошибки:** BC31102  
  
### Чтобы исправить эту ошибку  
  
-   Если есть возможность изменения исходного кода, определяющего свойство, рассмотрите возможность объявления процедуры `Set` с таким же уровнем доступа как само свойство.  
  
-   Если такой возможности нет либо необходимо установить уровень доступа процедуры `Set` более высокий, чем у самого свойства, то попробуйте переместить инструкцию, которая записывает значение свойства, в область кода, имеющего лучший доступ к свойству.  
  
## См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)