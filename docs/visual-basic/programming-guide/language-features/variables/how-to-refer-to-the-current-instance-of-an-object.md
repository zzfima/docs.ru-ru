---
title: "Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "текущий экземпляр"
  - "экземпляры, ссылка на текущий"
  - "объектные переменные"
  - "объекты [Visual Basic], ссылка на текущий экземпляр"
  - "переменные [Visual Basic], объект"
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Текущим экземпляром* объекта называется экземпляр, в котором выполняется код в данный момент времени.  
  
 Ключевое слово `Me` используется для ссылки на текущий экземпляр.  
  
### Чтобы сослаться на текущий объект  
  
-   Используйте ключевое слово `Me` там, где обычно использовалось бы имя переменной объекта.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Хотя `Me` ведет себя подобно объектной переменной, его нельзя объявить или присвоить ему какое\-либо значение.  `Me` всегда ссылается на текущий экземпляр.  
  
## См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)