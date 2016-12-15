---
title: "Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "события [C#], хранение экземпляров в словаре"
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Одно из применений `accessor-declarations` заключается в предоставлении доступа к большому числу событий без выделения поля для каждого события, но с использованием словаря для хранения экземпляров событий.  Это полезно только в том случае, когда имеется много событий, но ожидается, что большинство из них не будут реализованы.  
  
## Пример  
 [!code-cs[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)