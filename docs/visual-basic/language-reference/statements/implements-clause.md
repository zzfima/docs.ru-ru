---
title: "Предложение Implements (Visual Basic) | Microsoft Docs"
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
  - "vb.ImplementsClause"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Implements - ключевое слово"
  - "Implements - оператор, сведения об Implements"
  - "реализация интерфейсов, Implements - ключевое слово"
  - "реализация интерфейсов, повторная реализация"
  - "члены интерфейса"
  - "члены интерфейса, реализация"
  - "члены интерфейса, Implements - ключевое слово"
  - "члены интерфейса, повторная реализация"
  - "члены, реализация"
  - "члены, Implements - ключевое слово"
  - "члены, повторная реализация"
  - "повторная реализация"
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Implements (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что член класса или структуры содержит реализацию члена, определенного в интерфейсе.  
  
## Заметки  
 Ключевое слово `Implements` отличается от [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md).  `Implements` указывает, что класс или структура реализует один или несколько интерфейсов, затем `Implements` используется для каждого элемента, чтобы указать, какой интерфейса и какой член реализуется.  
  
 Если класс или структура реализуют интерфейс, то они должны содержать оператор `Implements` сразу после оператора [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) или [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md), и этот оператор должен реализовывать все определенные в интерфейсе члены.  
  
## Повторная реализация  
 В производном классе можно повторно реализовать член интерфейса, который уже реализован в базовом классе.  Это отличается от переопределения члена базового класса в следующих отношениях.  
  
-   Базовый член класса не должен быть [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), чтобы быть повторно реализованным.  
  
-   Можно повторно реализовать элемент с другим именем.  
  
 Ключевое слово `Implements` можно использовать в следующих контекстах:  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)