---
title: "ByVal (Visual Basic) | Microsoft Docs"
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
  - "vb.ByVal"
  - "ByVal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByVal - ключевое слово"
  - "ByVal - ключевое слово, контексты"
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ByVal (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает способ передачи аргумента, при котором вызванная процедура может изменить значение переменной, содержащейся в аргументе вызывающего кода.  
  
## Заметки  
 Модификатор `ByVal` можно использовать в следующих контекстах:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Пример  
 В следующем примере иллюстрируется использование механизма передачи параметров `ByVal` с аргументом ссылочного типа.  В этом примере аргумент `c1` является экземпляром класса `Class1`.  `ByVal` не позволяет коду в процедурах изменить основное значение ссылочного аргумента `c1`, но не защищает доступные поля и свойства `c1`.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)