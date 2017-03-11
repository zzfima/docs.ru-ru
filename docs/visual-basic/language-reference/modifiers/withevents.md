---
title: "WithEvents (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.WithEvents"
  - "WithEvents"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "WithEvents - ключевое слово"
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# WithEvents (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что одна или несколько переменных объявленного члена относится к экземпляру класса, который может порождать события.  
  
## Заметки  
 Если переменная определена с помощью `WithEvents`, можно декларативно указать, что метод обрабатывает события переменной с помощью ключевого слова `Handles`.  
  
 Можно использовать `WithEvents` только на уровне модуля или процедуры.  Это означает, что контекст объявления для переменной `WithEvents` должен быть классом или модулем и не может быть исходным файлом, пространством имен, структурой или процедурой.  
  
 Нельзя использовать `WithEvents` для членов структуры.  
  
 С помощью `WithEvents` можно объявлять только отдельные переменные \(не массивы\).  
  
## Правила  
  
-   **Типы элементов**. Необходимо объявлять переменные `WithEvents` объектными, что позволяет им принимать экземпляры класса.  Однако нельзя объявлять их как `Object`.  Такие переменные должны быть объявлены как определенный класс, который способен создавать события.  
  
 Модификатор `WithEvents` можно использовать в следующем контексте: [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## См. также  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)