---
title: "NotOverridable (Visual Basic) | Microsoft Docs"
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
  - "vb.NotOverridable"
  - "NotOverridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "элементы, запечатанные"
  - "методы [Visual Basic], запечатанные"
  - "NotOverridable - ключевое слово"
  - "переопределение"
  - "процедуры, переопределение"
  - "процедуры, переопределение"
  - "свойства [Visual Basic], переопределение"
  - "свойства [Visual Basic], переопределение"
  - "запечатанные элементы"
  - "запечатанные методы"
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# NotOverridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что свойство или процедура не может быть переопределена в производном классе.  
  
## Заметки  
 `NotOverridable` модификатор предотвращает свойство или метод из переопределения в производном классе.  [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) модификатор позволяет свойство или метод в классе, который должен быть переопределен в производном классе.  Дополнительные сведения см. в разделе [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Если `Overridable` OR  `NotOverridable` не указан модификатор, зависит от параметра по умолчанию переопределяют ли свойство или метод свойство или метод базового класса.  Если свойство или метод переопределяет свойство или метод базового класса, то параметр по умолчанию `Overridable`; в противном случае он  `NotOverridable`.  
  
 Элемент, который не может быть переопределен, иногда называется *запечатанным* элементом.  
  
 Можно использовать `NotOverridable` только в операторе объявления свойства или процедуры.  Можно указать `NotOverridable` только для свойства или процедуры, которая переопределяет другое свойство или процедуру, то есть только в сочетании с `Overrides`.  
  
## Общая модификаторы  
 Нельзя задавать `Overridable` OR  `NotOverridable` для a  `Private` метод.  
  
 `NotOverridable` нельзя указывать в одном и том же объявлении `MustOverride` вместе с `Overridable` или `Shared` .  
  
## Использование  
 Модификатор `NotOverridable` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Модификаторы](../../../visual-basic/language-reference/modifiers/index.md)   
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)