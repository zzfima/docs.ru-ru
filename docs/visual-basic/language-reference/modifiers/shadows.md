---
title: "Shadows (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shadows"
  - "shadows"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "повторяющиеся имена"
  - "имена, затенение"
  - "область действия, затенение"
  - "затенение"
  - "Shadows - ключевое слово"
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shadows (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что данный делегат повторно объявляет и скрывает идентично именованный элемент или набор перегружаемых элементов в базовом классе.  
  
## Заметки  
 Основным предназначением затенения является сохранение определения членов класса \(который также называют *hiding by name*\).  Базовый класс может подвергнуться изменениям, при которых будет создан элемент, имя которого совпадает с ранее определенным элементом.  Если это так, то при применении модификатора `Shadows` в классе используются ссылки на ранее определенный, а не на новый член базового класса.  
  
 Затенение и переопределение заново реализуют наследуемый элемент, но существуют значительные различия между двумя способами.  Дополнительные сведения см. в разделе [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## Правила  
  
-   **Контекст объявления.** Можно использовать `Shadows` только на уровне класса.  Это означает, что контекст объявления для элемента `Shadows` должен быть классом и не может быть исходным файлом, пространством имен, структурой, модулем или процедурой.  
  
     Можно объявить только один затененный элемент в одном операторе объявлений.  
  
-   **Комбинированные модификаторы.** `Shadows` Нельзя указывать в одном и том же объявлении `Overloads` вместе с `Overrides` или `Static`.  
  
-   **Типы элементов**. Можно скрыть любой тип объявленного элемента с помощью любого другого типа.  При скрытии свойства или процедуры с другим свойством или процедурой параметры и возвращаемый тип не совпадают с соответствующими в свойстве или процедуре базового класса.  
  
-   **Доступ.** Затененный элемент в базовом классе обычно недоступен из производного класса, который его скрывает.  Однако следует принять во внимание следующее.  
  
    -   Если переопределяющий элемент недоступен из кода, который на него ссылается, то при разрешении ссылки используется переопределяемый элемент.  Например, если элемент `Private` скрывает элемент базового класса, код, который не имеет разрешение на доступ к элементу `Private`, обращается к элементу базового класса.  
  
    -   Даже если элемент скрыт, к нему можно получить доступ с помощью объекта, объявленного с помощью типа базового класса.  Можно получить доступ к нему через `MyBase`.  
  
 Модификатор `Shadows` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)