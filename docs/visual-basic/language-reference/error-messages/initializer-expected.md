---
title: "Ожидается инициализатор | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30996"
  - "bc30996"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30996"
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Ожидается инициализатор
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предпринята попытка объявить экземпляр класса с помощью инициализатора объектов, в котором список инициализации пуст, как показано в следующем примере:  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 По меньшей мере одно поле или свойство необходимо инициализировать в списке инициализаторов, как показано в следующем примере.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Идентификатор ошибки:** BC30996  
  
### Чтобы исправить эту ошибку  
  
1.  Инициализируйте хотя бы одно поле или свойство в инициализаторе или не используйте инициализатор объектов.  
  
## См. также  
 [Инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)