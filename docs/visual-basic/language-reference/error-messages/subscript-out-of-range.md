---
title: "Индекс вне диапазона (Visual Basic) | Microsoft Docs"
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
  - "vbrID9"
dev_langs: 
  - "VB"
ms.assetid: d0344a65-ec02-4caf-8d3c-9977392ca353
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Индекс вне диапазона (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Индекс массива является недопустимым, т.к. не попадает в разрешенный диапазон.  Нижний индекс измерения всегда равен 0, а верхний индекс возвращается методом `GetUpperBound` для этого измерения.  
  
### Чтобы исправить эту ошибку  
  
-   Измените индекс таким образом, чтобы он попадал в допустимый диапазон.  
  
## См. также  
 <xref:System.Array.GetUpperBound%2A?displayProperty=fullName>   
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)