---
title: "MustOverride (Visual Basic) | Microsoft Docs"
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
  - "vb.MustOverride"
  - "MustOverride"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "элементы, чистые виртуальные"
  - "MustOverride - ключевое слово"
  - "переопределение, MustOverride - ключевое слово"
  - "процедуры, переопределение"
  - "процедуры, переопределение"
  - "свойства [Visual Basic], переопределение"
  - "свойства [Visual Basic], переопределение"
  - "чистые виртуальные элементы"
  - "виртуальные элементы, чистые"
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# MustOverride (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что свойство или процедура не реализована в этом классе и должна быть переопределена в производном классе, прежде чем ее можно будет использовать.  
  
## Заметки  
 Можно использовать `MustOverride` только в операторе объявления свойства или процедуры.  Свойство или процедура, определяющая `MustOverride`, должна быть членом класса, причем класс должен быть помечен как [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## Правила  
  
-   **Неполное объявление.** Когда указывается `MustOverride`, не требуется писать дополнительные строки кода для свойства или процедуры, даже для операторов `End Function`, `End Property` или `End Sub`.  
  
-   **Комбинированные модификаторы.** `MustOverride` Нельзя указывать в одном и том же объявлении `NotOverridable` вместе с `Overridable` или `Shared`.  
  
-   **Затенение и переопределение.** Затенение и переопределение заново реализуют наследуемый элемент, но существуют значительные различия между двумя способами.  Дополнительные сведения см. в разделе [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
-   **Альтернативные условия.** Элемент, который не может использоваться иначе,чем в переопределении, иногда называется элементом *чисто виртуальным*.  
  
 Модификатор `MustOverride` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)