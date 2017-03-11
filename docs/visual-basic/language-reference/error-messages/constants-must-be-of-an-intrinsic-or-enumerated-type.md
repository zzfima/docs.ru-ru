---
title: "Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30424"
  - "bc30424"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30424"
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предпринята попытка объявить константу в качестве класса, структуры или массива или параметра типа, определенного содержащим базовым типом.  
  
 Константы должны быть встроенного типа \(`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong` или `UShort`\) или типа `Enum`\>, основанного на одном из целых типов.  
  
 **Идентификатор ошибки**: BC30424  
  
### Чтобы исправить эту ошибку  
  
1.  Укажите в объявлении константы встроенный тип или тип `Enum`.  
  
2.  Константа может иметь специальное значение, например, `True`, `False` или `Nothing`.  Компилятор рассматривает эти стандартные предопределенные значения как значения соответствующего внутреннего типа.  
  
## См. также  
 [Константы и перечисления](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Типы данных](../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)