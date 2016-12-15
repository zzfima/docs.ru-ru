---
title: "Вложенная функция не имеет сигнатуры, совместимой с делегатом &quot;&lt;имя_делегата&gt;&quot; | Microsoft Docs"
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
  - "vbc36532"
  - "bc36532"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36532"
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Вложенная функция не имеет сигнатуры, совместимой с делегатом &quot;&lt;имя_делегата&gt;&quot;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Лямбда\-выражение, присвоенное делегату, имеет несовместимую сигнатуру.  Например, в следующем коде делегат `Del` имеет два параметра целого типа.  
  
```vb#  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Ошибка возникает, если лямбда\-выражения с одним аргументом объявляется как тип `Del`:  
  
```vb#  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Идентификатор ошибки:** BC36532  
  
### Чтобы исправить эту ошибку  
  
-   Измените определение делегата или назначенное лямбда\-выражение таким образом, чтобы сигнатуры были совместимы.  
  
## См. также  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)