---
title: "VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrArgument_StrConvSCandTC"
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `SimplifiedChinese` и `TraditionalChinese`, являющиеся членами перечисления `VbStrConv`.  
  
### Исправление ошибки  
  
-   Удалите  `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.  
  
## См. также  
 <xref:System.Globalization>   
 [НЕ В СБОРКЕ. Перечисление VbStrConv](http://msdn.microsoft.com/ru-ru/59f83dd9-6361-47df-a836-02ba9d4cb936)   
 [Знакомство с международными приложениями на платформе .NET Framework](/visual-studio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)