---
title: "Overridable (Visual Basic) | Microsoft Docs"
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
  - "Overridable"
  - "vb.Overridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "конкретные элементы"
  - "элементы, конкретные"
  - "элементы, виртуальные"
  - "Overridable - ключевое слово"
  - "переопределение, Overridable - ключевое слово"
  - "процедуры, переопределение"
  - "процедуры, переопределение"
  - "свойства [Visual Basic], переопределение"
  - "свойства [Visual Basic], переопределение"
  - "виртуальные элементы"
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Overridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что свойство или процедура могут быть переопределены свойством или процедурой с теми же именами в производном классе.  
  
## Заметки  
 `Overridable` модификатор позволяет свойство или метод в классе, который должен быть переопределен в производном классе.  [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) модификатор предотвращает свойство или метод из переопределения в производном классе.  Дополнительные сведения см. в разделе [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Если `Overridable` OR  `NotOverridable` не указан модификатор, зависит от параметра по умолчанию переопределяют ли свойство или метод свойство или метод базового класса.  Если свойство или метод переопределяет свойство или метод базового класса, то параметр по умолчанию `Overridable`; в противном случае он  `NotOverridable`.  
  
 Для переопределения наследуемого элемента можно использовать затенение или переопределение, но существуют значительные различия между двумя способами.  Дополнительные сведения см. в разделе [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Элемент, который может быть переопределен, иногда называют *виртуальным* элементом.  Если он может быть переопределен, но это делать необязательно, то он иногда называется *устойчивым* элементом.  
  
 Можно использовать `Overridable` только в операторе объявления свойства или процедуры.  
  
## Общая модификаторы  
 Нельзя задавать `Overridable` OR  `NotOverridable` для a  `Private` метод.  
  
 Нельзя указывать в одном объявлении `Overridable` вместе с `MustOverride`, `NotOverridable` или `Shared`.  
  
 Поскольку переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.  
  
## Использование  
 Модификатор `Overridable` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Модификаторы](../../../visual-basic/language-reference/modifiers/index.md)   
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)