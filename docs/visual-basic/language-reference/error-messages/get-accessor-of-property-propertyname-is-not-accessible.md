---
title: "Метод доступа Get свойства &lt;имяСвойства&gt; недоступен | Microsoft Docs"
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
  - "vbc31103"
  - "bc31103"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31103"
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Метод доступа Get свойства &lt;имяСвойства&gt; недоступен
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Инструкция пытается извлечь значение свойства, если у нее нет доступа к процедуре `Get` данного свойства.  
  
 Если [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md) имеет более ограниченный уровень доступа, чем [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md), то попытка прочитать значение свойства может завершиться ошибкой в следующих случаях:  
  
-   Инструкция `Get` помечена как [Private](../../../visual-basic/language-reference/modifiers/private.md), а вызывающий код находится вне класса или структуры, в которой определено свойство.  
  
-   Инструкция `Get` помечена как [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код находится ни в классе или структуры, в которой определено свойство, ни в производном классе.  
  
-   Инструкция `Get` помечена как [Friend](../../../visual-basic/language-reference/modifiers/friend.md), и вызывающий код находится в сборке, отличной от той, в которой определено свойство.  
  
 **Идентификатор ошибки:** BC31103  
  
### Чтобы исправить эту ошибку  
  
-   Если есть возможность изменения исходного кода, определяющего свойство, рассмотрите возможность объявления процедуры `Get` с таким же уровнем доступа как само свойство.  
  
-   Если нет такой возможности либо необходимо установить уровень доступа процедуры `Get` больше, чем у самого свойства, то попробуйте переместить инструкцию, которая считывает значение свойства в область кода, имеющего лучший доступ к свойству.  
  
## См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)