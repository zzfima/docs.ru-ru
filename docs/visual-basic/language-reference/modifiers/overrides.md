---
title: "Overrides (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Overrides"
  - "vb.Overrides"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Overrides - ключевое слово"
  - "переопределение"
  - "переопределение, Overrides - ключевое слово"
  - "процедуры, переопределение"
  - "процедуры, переопределение"
  - "свойства [Visual Basic], переопределение"
  - "свойства [Visual Basic], переопределение"
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Overrides (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что свойство или процедура переопределяет свойство или процедуру с идентичным названием, унаследованную от базового класса.  
  
## Заметки  
  
## Правила  
  
-   **Контекст объявления.** `Overrides` можно использовать только в операторе объявления свойства или процедуры.  
  
-   **Комбинированные модификаторы.** Невозможно указать `Overrides` вместе с `Shadows` или `Shared` в одном объявлении.  Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.  
  
-   **Соответствие сигнатур.** Сигнатура этого объявления должна точно соответствовать *сигнатуре* переопределяемого свойства или процедуры.  Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.  
  
     Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:  
  
    -   уровень доступа;  
  
    -   тип возвращаемого значения \(если применимо\).  
  
-   **Универсальные сигнатуры.** Для универсальной процедуры сигнатура содержит число параметров типа.  Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.  
  
-   **Дополнительные соответствия.** Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:  
  
    -   модификатор уровня доступа \(например, [Public](../../../visual-basic/language-reference/modifiers/public.md)\);  
  
    -   механизм передачи каждого параметра \([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../visual-basic/language-reference/modifiers/byref.md)\);  
  
    -   списки ограничений для каждого типа параметра универсальной процедуры.  
  
-   **Сокрытие и переопределение.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.  Подробнее: [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API\-интерфейсов с библиотекой C\#.  
  
 Модификатор `Overrides` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)