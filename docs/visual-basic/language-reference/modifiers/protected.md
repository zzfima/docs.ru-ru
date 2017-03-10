---
title: "Protected (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Protected"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Protected - модификатор доступа"
  - "сочетание ключевых слов Protected Friend"
  - "Protected - ключевое слово"
  - "Protected - ключевое слово, и Friend"
  - "Protected - ключевое слово, синтаксис"
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Protected (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что один или несколько объявленных элементов программирования доступны только из своего собственного класса или из производного класса.  
  
## Заметки  
 В некоторых случаях элемент программирования, объявленный в классе, содержит конфиденциальные данные или ограниченный код, и поэтому к нему необходимо ограничить доступ.  Однако, если класс является наследуемым и предполагается в иерархии производных классов, то может потребоваться доступ к данным или коду для этих производных классов.  В таком случае необходимо, чтобы элемент был доступен как из базового класса, так и из всех производных классов.  Для ограничения доступа к элементу таким способом можно объявить его как `Protected`.  
  
## Правила  
  
-   **Контекст объявления.** Можно использовать `Protected` только на уровне класса.  Это означает, что контекст объявления для элемента `Protected` должен быть классом и не может быть исходным файлом, пространством имен, структурой, модулем или процедурой.  
  
-   **Комбинированные модификаторы.** Можно использовать модификатор `Protected` вместе с модификатором [Friend](../../../visual-basic/language-reference/modifiers/friend.md) в одном и том же объявлении.  Эта комбинация делает объявленные элементы доступными из любого места сборки, из собственного класса и из производных классов.  Можно указать `Protected Friend` только для элементов классов.  
  
## Поведение  
  
-   **Уровень доступа.** Весь код класса имеет доступ к элементам класса.  Код в любом классе, производном от базового класса, имеет доступ ко всем `Protected` элементам базового класса.  Это справедливо для всех поколений наследования.  Это означает, что класс может получить доступ к элементам `Protected` базового класса базового класса и т.д.  
  
     Защищенный доступ не является надмножеством или подмножеством дружественного доступа.  
  
-   **Модификаторы доступа..** Ключевые слова, указывающие уровень доступа, называются *access modifiers*.  Для получения сведений о сравнении модификаторов доступа см. раздел [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Protected` можно использовать в следующих контекстах:  
  
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
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)