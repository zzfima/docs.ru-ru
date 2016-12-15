---
title: "Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером | Microsoft Docs"
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
  - "vbc32039"
  - "bc32039"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32039"
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Цикл `For Each` использует массив в качестве переменной *элемента* итерации, но инициализирует этот массив.  
  
 Следующие операторы показывают возникновение этой ошибки.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Первый оператор `For Each` представляет допустимый способ доступа к элементам `arrayList`.  Второй оператор `For Each` вызывает эту ошибку.  
  
 **Идентификатор ошибки**: BC32039  
  
### Чтобы исправить эту ошибку  
  
-   Удалите инициализацию из объявления переменной *элемента* итерации.  
  
## См. также  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)