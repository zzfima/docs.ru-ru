---
title: "При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения &lt;имяТипа&gt; | Microsoft Docs"
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
  - "bc30020"
  - "vbc30020"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30020"
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения &lt;имяТипа&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор сравнения `Is` определяет, ссылаются ли две объектные переменные на один экземпляр.  Это сравнение не определяется для типов значений.  
  
 **Идентификатор ошибки**: BC30020  
  
### Чтобы исправить эту ошибку  
  
-   Для сравнения двух типов значений используйте соответствующий арифметический оператор сравнения или оператор `Like`.  
  
## См. также  
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор Like](../../../visual-basic/language-reference/operators/like-operator.md)   
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)