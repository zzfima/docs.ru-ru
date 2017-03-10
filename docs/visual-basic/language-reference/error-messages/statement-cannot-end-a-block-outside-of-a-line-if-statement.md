---
title: "Оператор не может завершить блок за пределами однострочной инструкции If | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32005"
  - "bc32005"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32005"
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Оператор не может завершить блок за пределами однострочной инструкции If
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Однострочный оператор `If` содержит несколько операторов, разделенных двоеточием \(:\), одним из которых является оператор `End` для управляющего блока, располагающегося за пределами однострочного оператора `If`.  Однострочный оператор `If` не использует оператор `End If`.  
  
 **Идентификатор ошибки**: BC32005  
  
### Чтобы исправить эту ошибку  
  
-   Переместите однострочный оператор `If` за пределы управляющего блока, содержащего оператор `End If`.  
  
## См. также  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)