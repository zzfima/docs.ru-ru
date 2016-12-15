---
title: "&lt;ключевоеСлово&gt; разрешено использовать только в методе экземпляра | Microsoft Docs"
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
  - "bc30043"
  - "vbc30043"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30043"
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;ключевоеСлово&gt; разрешено использовать только в методе экземпляра
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевые слова `Me`, `MyClass` и `MyBase` ссылаются на конкретные экземпляры класса.  Их нельзя использовать в общих процедурах `Function` или `Sub`.  
  
 **Идентификатор ошибки**: BC30043  
  
### Чтобы исправить эту ошибку  
  
-   Удалите ключевое слово из процедуры или удалите ключевое слово `Shared` из объявления процедуры.  
  
## См. также  
 [Присваивание объектных переменных](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)