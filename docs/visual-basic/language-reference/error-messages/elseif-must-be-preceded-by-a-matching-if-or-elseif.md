---
title: "Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf | Microsoft Docs"
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
  - "vbc30014"
  - "bc30014"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30014"
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#ElseIf` является директивой условной компиляции.  Предложению `#ElseIf` должно предшествовать соответствующее предложение `#If` или `#ElseIf`.  
  
 **Идентификатор ошибки:** BC30014  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте, что предыдущая директива `#If` или `#ElseIf` не отделена от `#ElseIf` промежуточным блоком условной компиляции или неправильно расположенной директивой `#End If`.  
  
2.  Если `#ElseIf` предшествует директива `#Else`, удалите `#Else` или измените ее на `#ElseIf`.  
  
3.  Если что\-нибудь еще находится по порядку, то добавьте директиву `#If` в начало блока условной компиляции.  
  
## См. также  
 [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)