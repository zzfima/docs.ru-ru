---
title: "Выведение типа Nullable не поддерживается в данном контексте | Microsoft Docs"
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
  - "vbc36629"
  - "bc36629"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36629"
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Выведение типа Nullable не поддерживается в данном контексте
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Типы значений и структуры можно объявить как обнуляемые.  
  
```vb#  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Однако нельзя использовать объявление nullable в сочетании с определением типа.  Например, следующий код вызывает эту ошибку:  
  
```vb#  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Идентификатор ошибки:** BC36629  
  
### Чтобы исправить эту ошибку  
  
-   Используйте предложение `As` для объявления переменной в качестве обнуляемой.  
  
## См. также  
 [Типы значения, допускающие Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)