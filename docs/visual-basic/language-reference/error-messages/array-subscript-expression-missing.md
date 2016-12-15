---
title: "Отсутствует выражение с индексами для массива | Microsoft Docs"
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
  - "bc30306"
  - "vbc30306"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30306"
ms.assetid: 3c0d9732-ee37-436f-a1df-29d65712f48a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Отсутствует выражение с индексами для массива
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В инициализации массива пропущен один или несколько индексов, определяющих границы массива.  Например, инструкция может содержать выражение `myArray (5,5,,10)`, в котором пропущен третий индекс.  
  
 **Идентификатор ошибки:** BC30306  
  
### Чтобы исправить эту ошибку  
  
-   Укажите недостающий индекс.  
  
## См. также  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)