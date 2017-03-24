---
title: "Отсутствует выражение с индексами для массива | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30306"
  - "vbc30306"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30306"
ms.assetid: 3c0d9732-ee37-436f-a1df-29d65712f48a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Отсутствует выражение с индексами для массива
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В инициализации массива пропущен один или несколько индексов, определяющих границы массива.  Например, инструкция может содержать выражение `myArray (5,5,,10)`, в котором пропущен третий индекс.  
  
 **Идентификатор ошибки:** BC30306  
  
### Чтобы исправить эту ошибку  
  
-   Укажите недостающий индекс.  
  
## См. также  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)